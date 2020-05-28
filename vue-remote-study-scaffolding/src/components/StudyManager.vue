<template>
  <div class="study-manager">
    
    <ContentView :class="styleClass"/>
    <InstructionView :class="styleClass" @toggleInstructionViewRequested="toggleInstructionView"/>

  </div>
</template>

<script>
import InstructionView from './InstructionView.vue'
import ContentView from './ContentView.vue'

export default {
  name: 'StudyManager',
  props: {
    breakpoint: {
      type: Number,
      default: 800
    }
  },
  components: {
    InstructionView,
    ContentView
  },
  data() {
    return {
      instructionViewIsVisible: true,
      window: {
          width: 0,
          height: 0
      }
   }
  },
  created() {
      window.addEventListener('resize', this.handleResize);
      this.handleResize();
  },
  destroyed() {
      window.removeEventListener('resize', this.handleResize);
  },
  computed: {
    styleClass() {
      let classes = [];
      if (this.window.width < this.breakpoint) {
        classes.push('mobile');
      } else {
        classes.push('desktop');
      }
      if (this.instructionViewIsVisible) {
        classes.push('instruction-expanded');
      } else {
        classes.push('instruction-hidden');
      }
      return classes.join(' ');
    }
  },
  methods: {
    handleResize() {
        this.window.width = window.innerWidth;
        this.window.height = window.innerHeight;
    },
    toggleInstructionView() {
      this.instructionViewIsVisible = !this.instructionViewIsVisible;
    }
  }
}
</script>

<style>
.desktop.content-view {
  width: 50vw;
}
.desktop.instruction-view {
  width: 50vw;
}
.desktop.content-view.instruction-hidden {
  width: calc(100vw - 30px);
}
.desktop.instruction-view.instruction-hidden {
  width: 30px;
}

.mobile.content-view {
  height: calc(100vh - 30px);
}


</style>
