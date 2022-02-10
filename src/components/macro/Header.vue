<template>

  <header class="main-nav">
      
      <div class="container">

          <div class="site-logo">
            <img :src="logourl" alt="">
          </div>

          <nav>
              <ul>
                <li v-for="(item,index) in menu_entries" :key="index" :class="[item.class, {'active': index == activeIndex}]" @click.prevent="setActive(index)">
                  <a href="item.url">{{item.name}}</a>
                </li>
              </ul>
          </nav>
      </div>
  </header>
</template>

<script>

    import menu_entriesJSON from "../../data/menu.json";

    export default {
      name: 'Header',

      components: {
      },
      props: {
        msg: String,
        logourl: String,
      },
      data() {
        return {
            activeIndex: 0,
            menu_entries: menu_entriesJSON,
        }
      },
      methods: {

        setActive(index){
          this.activeIndex = index;
        }
      }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  header {

    background-color: white;
    height: 100px;
    border-bottom: 2px solid black;

    .container {
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 10px;
    }


    .site-logo {
      height: 100%;
      padding: 15px 0 30px 0;


      img {
        height: 100%;
      }
    }

    nav {
      text-transform: uppercase;
      font-size: 0.8rem;
      width: 45%;
      

      
      ul { 
        list-style: none;
        padding: 0;
        display: flex;
        justify-content: space-between;
        align-items: center;

        li {
            position: relative;

            &.btn {
              background-color: #fed03d;
                a {
                  display: block;
                  padding: 10px 20px;
                }
            }

            &:not(.btn).active {

                &::after {
                  content: "";
                  display: block;
                  position: absolute;
                  top: calc(400% - 5px);
                  left: 50%;
                  transform: translateX(-50%);
                  width: 0;
                  height: 0;
                  line-height: 0px;
                  border-top: 15px solid white;
                  border-left: 15px solid transparent;
                  border-right: 15px solid transparent;
                  z-index: 10;
                }

                a {
                  color: #fed75b;
                  font-weight: 400;
                  display: block;
                  height: 100%;
                }
            }


        }
      }
    }

  }


  h3 {
    margin: 40px 0 0;
  }

  a {
    color: #555;
    text-decoration: none;
    font-weight: 100;
  }
</style>
