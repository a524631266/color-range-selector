<template>
  <div id="app">
    <g>
      <rect ></rect>
    </g>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import ColorInterploater from '@/util/colorinterpolater';
@Component({
  components: {
  },
})
export default class App extends Vue {
  @Prop() public data!: Array<[number,string]>;
  private mounted() {
    const data = [[-10, '#3060cf'],
            [0, '#fffbbc'],
            [10, '#c4463a']];
    const colorinter = new ColorInterploater(data as any);
    (window as any).colorinter = colorinter;
  }

}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
