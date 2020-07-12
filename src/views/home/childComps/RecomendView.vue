<template>
    <div class="recomend">
      <div v-for="item in recommends" class="recomend-item">
        <a :href="item.link">
          <img :src="item.image" alt="">
          <div>{{item.title}}</div>
        </a>
      </div>
    </div>
</template>

<script>
    export default {
      name: "RecomendView",
      props: {
        recommends: {
          type: Array,
          default(){
            return []
          }
        }
      }
    }
</script>

<style scoped>

  .recomend{
    display: flex;
    text-align: center;
    font-size: 12px;
    padding: 10px 0px 20px;
    border-bottom: 8px solid #eee;
  }
  .recomend-item{
    flex: 1;
  }
  .recomend-item img{
    height: 80px;
    width: 80px;
    margin-bottom: 5px;
  }
</style>
