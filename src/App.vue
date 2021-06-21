<template>
  <div id="app">
    <el-container>
      <el-header>
        <el-menu
          :default-active="activeIndex2"
          class="el-menu-demo"
          mode="horizontal"
          background-color="#545c64"
          text-color="#fff"
          active-text-color="#ffd04b">
          <el-menu-item index="1" ><a href='/'>Home</a></el-menu-item>
          <el-menu-item index="2" ><a href="/cats">Cats</a></el-menu-item>
          <el-menu-item index="3"><a href="/dogs">Dogs</a></el-menu-item>
        </el-menu>
      </el-header>
      <el-main>
        <!-- <div class="block">
          <el-date-picker
            v-model="value1"
            type="daterange"
            range-separator="To"
            start-placeholder="Start date"
            end-placeholder="End date">
          </el-date-picker>
        </div> -->
        <router-view/>
      </el-main> 
    </el-container>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      activeIndex: '1',
      activeIndex2: '1'
    };
  },
  methods: {
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
