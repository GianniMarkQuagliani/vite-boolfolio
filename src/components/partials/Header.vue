<script>
  export default {
    name: 'Header',
    data() {
      return {}
    },
    computed: {},
    mounted() {},
    methods: {}
  }
</script>

<template>
  <header>
    <nav>
        <ul>
            <li>
                <router-link :to="{ name: 'home' }">Home</router-link>
            </li>
            <li>
                <router-link :to="{ name: 'about' }">About</router-link>
            </li>
            <li>
                <router-link :to="{ name: 'projects' }">Projects</router-link>
            </li>
            <li>
                <router-link :to="{ name: 'contacts' }">Contacts</router-link>
            </li>
        </ul>
    </nav>
  </header>
</template>

<style lang="scss" scoped>

header{
    position: fixed;
    width: 100%;
    text-align: center;
    padding: 20px;
    ul{
        list-style: none;
        li{
            margin: 0 10px;
            display: inline-block;
            a{
                color: white;
                text-decoration: none;
                text-transform: uppercase;
                &.active{
                    font-weight: bold;
                    color: yellow;
                }
                &:hover{
                    text-decoration: underline;
                }
            }

        }
    }
}

</style>
