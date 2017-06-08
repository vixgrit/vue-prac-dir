<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Directives Exercise</h1>
        <!-- Exercise -->
        <!-- Build a Custom Directive which works like v-on (Listen for Events) -->
        <button v-onDir:click="logTitle" class="btn btn-primary">Test directive here!</button>
        <hr>
        <div
          v-onDir:mouseenter="mouseEnter"
          v-onDir:mouseleave="mouseLeave"
          style="width: 100px; height: 100px; background-color: lightgreen;">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    directives: {
      'onDir': {
        bind(el, binding, vnode) {
          let event = binding.arg;
          let fn = binding.value
          el.addEventListener(event, fn);
        }
      }
    },
    methods: {
      logTitle(el) {
        console.log('Logging result');
      },
      mouseEnter(el) {
        el.target.style.backgroundColor = 'purple'
      },
      mouseLeave(el) {
        el.target.style.backgroundColor = 'yellow'
      }
    }
  }
</script>

<style>
</style>
