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
    <div>單位轉換器</div>
    <div id = "computed_props">
      公里 : <input type = "text" v-model = "kilometers">
      公尺: <input type = "text" v-model = "meters">
    </div>
    <div id="info"></div>
    <div>意見回饋表</div>
    <form>
      <div>
        使用者名稱：
        <input v-model="user_name" placeholder="請輸入使用者名稱"/>
      </div>
      <div>
        使用者性別：
        <select v-model="gender" name="gender">
          <option value="男">男</option>
          <option value="女">女</option>
          <option value="保密">保密</option>
        </select>
      </div>
      <div>
        使用者興趣：
        <input type="checkbox" value="看書" v-model="interest">
        <label>看書</label>
        <input type="checkbox" value="旅遊" v-model="interest">
        <label>旅遊</label>
        <input type="checkbox" value="喝咖啡" v-model="interest">
        <label>喝咖啡</label>
      </div>
      <div>
        使用者意見：
        <textarea v-model="feedback" placeholder="請輸入您的意見"></textarea>
      </div>
      <input type="radio" value="同意" v-model="accept">
      <label>同意</label>
      <br/>
      <input type="radio" value="不同意" v-model="accept">
      <label>不同意</label>
      <br/>
      <button v-on:click="SendFeedBack">送出</button>
    </form>

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
      ],
      kilometers: 0,
      meters: 0,
      user_name: "",
      gender: "保密",
      interest: [],
      feedback: "",
      accept: "同意"
    };
  },
  methods: {
    showUserInput: function() {
      alert(this.msg);
    },
    SendFeedBack: function() {
      if (this.accept == "同意") {
        alert(
          "送出表單，內容：\n名稱" +
            this.user_name +
            "\n" +
            "性別" +
            this.gender +
            "\n" +
            "興趣" +
            this.interest +
            "\n" +
            "意見" +
            this.feedback
        );
      } else {
        alert('請先勾選同意')
      }
    }
  },
  computed: {
    reversedMsg: function() {
      //反轉文字
      return this.msg
        .split("")
        .reverse()
        .join("");
    }
  },
  watch: {
    meters: function(val, oldVal) {
      this.kilometers = val / 1000;
      this.meters = val;
    },
    kilometers: function(val, oldVal) {
      this.kilometers = val;
      this.meters = val * 1000;
      console.log(
        "先前的kilometers值" + oldVal + "更改之後的kilometers值" + val
      );
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
