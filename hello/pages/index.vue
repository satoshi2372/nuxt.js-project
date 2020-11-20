<template>
  <div class="container">
    <div>
      <!-- 単一のdataを表示 -->
      {{ users[0].id }},{{ users[0].name }}
      <hr>
      <ul>
        <li v-for="user in users" :key="user.id">
          {{ user.id }},{{ user.name }},{{ user.company.name }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
// axsionからdata取得するための構文
const axios = require('axios')
let url = 'https://jsonplaceholder.typicode.com/users'
export default {
  //asyncData nuxtメソッド コンポーネント初期化前に非同期の処理を行えるようにするためのメソッド
  asyncData({ params,error }){
    //指定アドレスからのAPIデータ取得、取得後に前メソッド呼ぶ
    return axios.get(url)
    //resにはサーバーからのレスポンスデータが入っている
    .then((res)=> {
      //res.dataにはjsonデータが入っている。
      return {users: res.data}
    })
    //エラーハンドリング eはエラー情報 response.statusでエラー内容を表示できる
    .cach((e) => {
      console.log(e.response.status)
      // エラーページの表示には下記をセットで記述 message:の後に文章を入力する事で好きな文章に指定できる。
      error({users: e.response.status, message:e.message});
      // error({users: e.response.status, message: 'Error!!!!' });
    })
  }
}
</script>
