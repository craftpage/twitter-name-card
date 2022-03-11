<template>
  <div id="setting">
    <h1>Twitter名刺(大学生用)</h1>
    <p>Twitterのユーザ名@<input v-model="twitter_id" /></p>
    <p>本名 <input v-model="name" /></p>
    <p>コメント <input v-model="comment"></p>
    <p>学科 <input v-model="course"></p>
    <button v-on:click="onClick">生成</button><br /><br />
  </div>

  <div id="card">
    <p>名前:{{card_name}}  学科:{{card_course}}</p>
    <p>Twitterのユーザ名{{card_twitter_id}}</p>
    <p>{{card_comment}}</p>
    <img :src=twitter_url />
  </div> 

  <div id="card">
    <p>名前:{{card_name}} 学科:{{card_course}}</p>
    <p>Twitterのユーザ名{{card_twitter_id}}</p>
    <p>{{card_comment}}</p>
    <img :src=twitter_url />
  </div> 

  <div id="card">
    <p>名前:{{card_name}} 学科:{{card_course}}</p>
    <p>Twitterのユーザ名{{card_twitter_id}}</p>
    <p>{{card_comment}}</p>
    <img :src=twitter_url />
  </div> 
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      name:"",
      course:"",
      twitter_id:"",
      twitter_url:"",
      comment:"",
      card_name:"",
      card_twitter_id:"",
      card_course:"",
      card_comment:""
    }
  },
  methods: {
    onClick() {
      this.twitter_url = "https://chart.googleapis.com/chart?cht=qr&chs=125x125&chl=https://www.twitter.com/" + this.twitter_id
      this.card_name = this.name
      this.card_twitter_id = "@" + this.twitter_id
      this.card_course = this.course
      this.card_comment = this.comment
    }
  }
}
</script>
