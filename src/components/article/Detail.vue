<template>
    <div class="article-detail">
        <div class="article-detail-inner">
            <h1 class="detail-title">{{articleDetail.title}}</h1>
            <div class="detail-info">
              <p class="detail-category" v-if="articleDetail.category_detail">
              {{articleDetail.category_detail.name}}
              </p>
              <p class="detail-author">{{articleDetail.author}}</p>
              <p class="detail-browse">{{articleDetail.browse}}</p>
              <p class="detail-browse">{{articleDetail.comments_list.data.length}}</p>
              <p class="detail-create-at">{{articleDetail.created_at}}</p>
            </div>
            <div class="detail-content">
              <mavon-editor
                style="height: 100%"
                :ishljs="true"
                v-model="articleDetail.content"
                :defaultOpen="'preview'"
                :editable="false"
                :subfield="false"
                :toolbarsFlag="false">
              </mavon-editor>
              <div class="detail-comment">
                <VComment></VComment>
              </div>
            </div>
        </div>
    </div>
</template>
<script>
import {mapState, mapActions} from 'vuex'
import VComment from './Comment.vue'
export default {
  data () {
    return {
      id: this.$route.params.id
      // articleDetail: null
    }
  },
  created () {
    this.getDetail()
    console.log('id是' + this.id)
  },
  methods: {
    ...mapActions({
      getArticleDetail: 'article/getArticleDetail'
    }),
    async getDetail () {
      await this.getArticleDetail(this.id)
    }
  },
  computed: {
    ...mapState({
      articleDetail: state => state.article.articleDetail
    })
  },
  components: {
    VComment
  }
}
</script>
<style scoped>
    .article-detail{
        width: 100%;
        background-color: #f8f8f8;
        display: flex;
        justify-content: center;
        padding-top: 1.5rem;
    }
    .article-detail-inner {
        width: 70%;
        background-color: #fff;
        height: auto;
        box-sizing: border-box;
    }
    .detail-title {
      font-size: 2.5rem;
      display: flex;
      margin-left: 2rem;
      line-height: 5rem;
    }
    .detail-info {
      display:flex;
    }
    .detail-info p {
      margin: 1rem 2rem;
    }

</style>
