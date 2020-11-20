<template>
  <div class="container">
    <div>
      <!-- vuexのstoreを表示クラシックモード -->
      <!-- <p> {{ $store.state.message }} </p> -->
      <!-- vuex モジュールモード -->
      <p> {{ $store.state.hello.message }} </p>

      <!-- componentからmutationを実行 -->
      <!-- <button v-on:click="$store.commit('updateMessage')">Update</button> -->

      <!-- 引数を使用しmutationを実行 -->
      <!-- <button v-on:click="$store.commit('updateMessage','Commit with payload')">Update</button> -->

      <!-- クラシックモード -->
      <!-- <button v-on:click="$store.dispatch('updateMessageAction','Dipatch with payload')">Update</button> -->

      <!-- モジュールモード -->
 <button v-on:click="$store.dispatch('hello/updateMessageAction', 'Dispatch with payload')">Dispatch</button>

      <!-- nuxt ~/でフォルダ指定 -->
      <img src="~/assets/img/woman.jpg">
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
  img {
    width: 100%;
    height: auto;
  }
</style>
