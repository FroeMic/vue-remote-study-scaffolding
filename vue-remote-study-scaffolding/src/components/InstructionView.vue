<template>
  <div class="instruction-view">
    <div class="resize-bar" @click="resizeBarClicked">
      <span class="symbol"></span>
    </div>
    <div class="instruction-content">
    </div>
  </div>
</template>

<script>
export default {
  name: 'InstructonView',
  methods: {
    resizeBarClicked() {
      this.$emit('toggleInstructionViewRequested')
    }
  }

}
</script>

<style>
  .instruction-view {
    height: 100vh;
    width: 100vw;
    overflow: scroll;
    background: whitesmoke;
  }
  .desktop.instruction-view {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    overflow-y: scroll;
    overflow-x: hidden;
    z-index: 10;
    -webkit-box-shadow: 4px 4px 15px 5px rgba(0,0,0,0.15); 
    box-shadow: 4px 4px 15px 5px rgba(0,0,0,0.15);
  }
  .desktop.instruction-view .resize-bar {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    width: 22px;
    height: 100vh;
    vertical-align: middle;
    -webkit-box-shadow: -6px 4px 5px 5px rgba(0,0,0,0.1); 
    box-shadow: -6px 4px 5px 5px rgba(0,0,0,0.231);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8em;
    font-weight: 800;
    color: dimgrey;
  }
  .desktop.instruction-view .resize-bar:hover {
    border: 1px solid lightskyblue;
    cursor: pointer;
  }
  .desktop.instruction-view .resize-bar .symbol:after{
    content: ">";
  }
  .desktop.instruction-view.instruction-hidden .resize-bar .symbol:after{
    content: "<";
  }
</style>
