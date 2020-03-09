<template>
  <div class="search-table-wrapper">
    <div class="search-table-inner">
      <div
        class="search-table-message"
        v-for="(message, index) in data"
        :key="index"
      >
           <div class="message-info-wrapper">
          <div class="message-title">{{message.title}}</div>
          <div class="message-author">{{message.role}}</div>
          <div class="message-category">{{message.date}}</div>
            </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
    },
    data () {
      return {
        data: [
          {date: '2020-12-12',
            title: '放假通知',
            role: '行政处'
          },
          {date: '2020-12-12',
            title: '放假通知',
            role: '行政处'
          },
          {date: '2020-12-12',
            title: '放假通知',
            role: '行政处'
          }
        ]
      }
    },
    methods: {
      onClick (message) {
        this.$router.push({
          path: '/pages/detail/main',
          query: {
            fileName: message.fileName
          }
        })
        this.$emit('onClick', message)
      }
    }
  }
</script>

<style lang="scss" scoped>
  .search-table-wrapper {
    padding: 0 16px;

    .search-table-inner {
      .search-table-message {
        margin: 14.5px 0;
        box-sizing: border-box;
        padding: 10px 0;
        border-radius: 10px;
        background-color: #fff;
        display: flex;
        align-items: center;
        border: 3px solid #30D9C4;

        .message-info-wrapper {
          width: 80%;
          margin-left: 15.5px;
          

          .message-title {
            width: 100%;
            color: #333;
            font-size: 16px;
            line-height: 22.5px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            font-weight: 500;
          }

          .message-author {
            color: rgba(0, 0, 0, .65);
            font-size: 13px;
            line-height: 18px;
            margin-top: 5px;
          }

          .message-category {
            color: rgba(0, 0, 0, .45);
            font-size: 13px;
            line-height: 18px;
          }
        }
      }
    }
  }
</style>
