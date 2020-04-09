<template>
    <div class="article">
        <div class="article-nav">
            <li v-for="(item,index) in descList"
              @click="changeArticleDesc(item.desc)"
              :key="index">
              {{item.name}}
            </li>

        </div>
        <div class="article-box">
            <li v-for="(item,index) in list"
             class="article-intro"
             :key="index"
            >
             <h1 class="article-title">{{item.title}}</h1>
             <div class="article-info" @click="toArticleDetail(item.id)">
              <p class="article-category" v-if="item.category_detail">
                {{item.category_detail.name}}
              </p>
              <p class="article-author"><i class="icon el-icon-user"></i> {{item.author}}</p>
              <p class="article-browse"><i class="icon el-icon-view"></i> {{item.browse}}</p>
              <p class="article-browse"><i class="icon el-icon-chat-dot-round"></i> {{item.comments_nums}}</p>
              <p class="article-create-at"><i class="icon el-icon-time"></i> {{item.created_at}}</p>
            </div>
            </li>
        </div>
    </div>
</template>
<script>
import merge from 'merge'
import {mapState, mapActions} from 'vuex'
export default {
  data () {
    return {
      descList: [
        {name: '最新', desc: 'created_at'},
        {name: '最热', desc: 'browse'}
      ]
    }
  },
  computed: {
    ...mapState({
      list: state => state.article.articleList
    })
  },
  methods: {
    ...mapActions({
      getArticleList: 'article/getArticleList'
    }),
    async getArticle () {
      // eslint-disable-next-line camelcase
      const {page, desc, category_id, keyword} = this.$route.query
      console.log('变换后')
      console.log(this.$route.query)
      await this.getArticleList({
        page,
        desc,
        keyword,
        category_id
      })
    },
    // Uncaught (in promise)
    // 报错NavigationDuplicated
    async changeArticleDesc (desc) {
      this.$router.replace({
        query: merge(this.$route.query, {
          desc
        })
      })
      this.getArticle()
    },
    toArticleDetail (id) {
      this.$router.push('/article/detail/' + id)
    }
  },
  created () {
    this.getArticle()
  }
}
</script>
<style scoped>
    .article {
        background-color: #fff;
        width:70%;
    }
    .article-nav {
        display:flex;
        line-height: 2rem;
        border:2px solid #f8f8f8;
    }
    .article-nav li{
            width: 3rem;
            height: 2rem;
    }
    .article-intro {
        border-bottom: 2px solid #f8f8f8;
    }
    .article-info {
        display: flex;
    }
    .article-info p {
        margin: 0.5rem 1rem;
    }
</style>
