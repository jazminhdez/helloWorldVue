<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <div v-for="(option,index) in options" :key="index" v-show="option.active">
      <h3>{{option.group}}</h3>
      <h4 v-if="option.categories.length%2!=0">Group with: {{option.categories.length}} categories is odd</h4>
      <h4 v-if="option.categories.length%2==0">Group with: {{option.categories.length}} categories is even</h4>
      <ul>
        <li v-for="(category,index) in option.categories" :key="index">
            <a :href="category.href" :title="category.title">{{category.text}}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      options: [{
        group:'Installed CLI Plugins',
        categories: [
          {
            text: 'Babel',
            href:'https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel',
            title:'Babel documentation'
          },
          {
            text: 'ESlint',
            href:'https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint',
            title:'ESlint documentation'
          }
        ],
        active:true
        },
        {
          group:'Essential Links',
          categories:[
            {
              text: 'Core Docs',
              href:'https://vuejs.org',
              title:'Vue documentation'
            },
            {
              text: 'Forum',
              href:'https://forum.vuejs.org',
              title:'Forum vue'
            },
            {
              text: 'Chat',
              href:'https://chat.vuejs.org',
              title:'Chat Vue'
            },
            {
              text: 'Twitter',
              href:'https://twitter.com/vuejs',
              title:'Twitter Vue'
            },
            {
              text: 'News',
              href:'https://news.vuejs.org',
              title:'News vue'
            },
            {
              text: '',
              href:'',
              title:''
            }
          ],
          active:false
        },
        {
          group:'Ecosystem',
          categories:[
            {
              text: 'Router',
              href:'https://router.vuejs.org',
              title:'vue Rotuer'
            },
            {
              text: 'vuex',
              href:'https://vuex.vuejs.org',
              title:'vuex'
            },
            {
              text: 'DEV tools',
              href:'https://github.com/vuejs/vue-devtools#vue-devtools',
              title:'vue dev tools'
            },
            {
              text: 'Loader',
              href:'https://vue-loader.vuejs.org',
              title:'vue loader'
            },
            {
              text: 'Awesome',
              href:'https://github.com/vuejs/awesome-vue',
              title:'vue Awesome'
            }
          ],
          active:true
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
</style>
