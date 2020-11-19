<template>
  <div class="container">
    <p>{{message}}</p>
    <hr>
    <router-link to="/mypage">My Page</router-link>
  </div>
</template>

<script>
export default {
  data(){
    return {
      message: 'Top Page'
    }
  }
}
</script>
