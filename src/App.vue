<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  box-sizing: border-box;
}

#nav {
  padding: 30px 5px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.list-group {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding-inline-start: 0;
  }
  
  .list-group-item {
    width: 75%;
    border: 1px solid #ccc;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    padding: .5rem 1rem;
    margin-bottom: 1rem;
  }

  .list-group-item-text {
    font-size: 1.3rem;
    margin-bottom: 1rem;
    color:#42b983;
  }

  .list-group-item-time, .list-group-item-text, .btn-group {
    grid-column: span 4;
  }

  .list-group-item-time {
    margin-bottom: .5rem;
    font-style: italic;
  }

  .btn {
    margin-right: 1rem;
  }
  .btn-remove {
    border-radius: 50%;
    border: none;
    color: #fff;
    background: red;
  }

  .archived {
    display: none;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 13px;
    margin-right: 1rem;
  }
</style>
