<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
import flexible from './components/lib/flexible'

flexible(window, window['lib'] || (window['lib'] = {}));
export default {
  name: 'app'
}
</script>

<style lang="less">
  @import './components/css/reset.less';
#app {

}
</style>
