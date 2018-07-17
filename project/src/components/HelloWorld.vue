<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <label>用戶輸入框：</label><input v-model="msg"/>
    <button v-on:click="showUserInput">點我</button>
    <div v-if="msg.length > 5" >
      你目前輸入的字大於5
    </div>
    <div v-else>
      你目前輸入不到5個字
    </div>
    <div>
      輸入文字反轉：{{reversedMsg}}
    </div>
    <h2>Essential Links</h2>
    <label>開關框框</label>
    <input type="checkbox"  v-model="box" />
    <div v-bind:class="{'box':box}" v-html="message"></div>
    <ul>
       <li v-for="item in vue_links.slice(0,4)" v-bind:key="item" >
        <a
          :href="item.name"
          target="_blank"
        >
        {{ item.name }}
        </a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li v-for="item in vue_links.slice(4,8)" v-bind:key="item" >
        <a
          :href="item.name"
          target="_blank"
        >
        {{ item.name }}
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "這是我的Vue.js練習紀錄",
      message: "<div>利用 v-html 建立一個div</div>",
      box: true,
      vue_links: [
        {
          name: "Core Docs",
          url: "https://vuejs.org"
        },
        {
          name: "Forum",
          url: "https://forum.vuejs.org"
        },
        {
          name: "Community Chat",
          url: "https://chat.vuejs.org"
        },
        {
          name: "Twitter",
          url: "http://vuejs-templates.github.io/webpack/"
        },
        {
          name: "Docs for This Template",
          url: "http://router.vuejs.org/"
        },
        {
          name: "vue-router",
          url: "http://vuex.vuejs.org/"
        },
        {
          name: "vue-loader",
          url: "http://vue-loader.vuejs.org/"
        },
        {
          name: "awesome-vue",
          url: "https://github.com/vuejs/awesome-vue"
        }
      ]
    };
  },
  methods: {
    showUserInput: function() {
      alert(this.msg);
    }
  },
  computed:{
    reversedMsg: function () {
      //反轉文字
      return this.msg.split('').reverse().join('')
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.box {
  border: #42b983 solid 1px;
}
</style>
