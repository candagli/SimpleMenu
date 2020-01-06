<template>
  <div id="app">

    <header class="header">
    <h1>Simple menu </h1>
    </header>

    <nav>

      <transition name="fade">
        <ul v-if="show">
          <li  v-for="item in items" v-bind:key="item.id">
            {{ item }}
          </li>
        </ul>
      </transition>

      <transition mode="out-in" name="fade">
        <i class="material-icons menu" v-if="!show" @click="show = !show" key="menu">
          menu
        </i>
        <i class="material-icons clear" v-else @click="show = !show" key="clear">
          clear
        </i>
      </transition>

    </nav>

    <div class="abschnitt"></div>
    <div class="abschnitt"></div>

    <nav>

      <transition name="fade">
        <ul v-if="show">
          <li  v-for="item in items" v-bind:key="item.id">
            {{ item }}
          </li>
        </ul>
      </transition>

      <transition mode="out-in" name="fade">
        <i class="material-icons menu" v-if="!show" @click="show = !show" key="menu">
          menu
        </i>
        <i class="material-icons clear" v-else @click="show = !show" key="clear">
          clear
        </i>
      </transition>

    </nav>





  </div>
</template>

<script>

export default {
  name: 'app',
  data(){
    return {
      items: [
        'List 1',
        'List 2',
        'List 3',
        'List 4',
        'List 5'],

      show: false
    }
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/icon?family=Material+Icons');

  .fade-enter-active,
  .fade-leave-active {
    transition: opacity .3s ease;
  }

  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
  .header {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px;
    width: 800px;
  }
  .header a {
    color: #fff;
    padding-right: 5px;
    text-decoration: none;
  }
  body {
    display: flex;
    font-family: 'Calibri Light';
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  nav {
    background-color: #455679;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    width: 100%;
    height: 60px;
  }

  ul {
    align-self: flex-start;
    background-color: #455679;
    border-top: solid 3px #a0cff0;
    margin: 0;
    padding: 0;
    position: absolute;
    top: 60px;
    width: 100%;
  }

  li {
    align-items: center;
    color: #a0cff0;
    cursor: pointer;
    display: flex;
    font-size: 1.5em;
    height: 2em;
    justify-content: center;
    list-style-type: none;
    text-transform: uppercase;
    transition: all .3s ease;
    &:hover {
      background-color: #455679;
      color: #a9f0d6;
    }
  }

  #app {
    align-items: center;
    background-color: #a0cff0;
    display: flex;
    flex-direction: column;
    width: 500px;
    height: 850px;
  }

  @media (max-width: 1024px) {
    #app {
      width: 100vw;
      height: 100vh;
    }
  }

  .menu,
  .clear {
    cursor: pointer;
    padding-left: 350px;
    font-size: 3em;
    transition: all .3s ease;
    width: 1.5px;
  }

  .menu {
    color: #455679;
    &:hover,
    &:active {
      color: #a0cff0;
    }
  }

  .clear {
    color: #a0cff0;
    &:hover,
    &:active {
      color: #455679;
    }
  }

  .abschnitt {
    background-color: #455679;
    margin-bottom: 5%;
    width: 90%;
    height: 26%;
    &:first-of-type {
      margin-top: 5%;
    }
  }
</style>
