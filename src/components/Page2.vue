<template>
  Page2
  <hr>
  <div class="font-bold">v-on:{событие}</div>
  <div>
    <button @click="counter++">+</button>
    <span>{{ counter }}</span>
    <button v-on:click="counter > 0 ? counter-- : false">-</button>
  </div>

  <div>
    <button @click="increase()">+2</button>
    <span>{{ counter }}</span>
    <button v-on:click="decrease()">-2</button>
  </div>

  <div>
    <button @click="increase(4)">+4</button>
    <span>{{ counter }}</span>
    <button v-on:click="decrease(3)">-3</button>
  </div>

  <hr>
  <div>
    <button @click="logEvent($event)">event</button>
  </div>

</template>

<script>
export default {
  name: "Page2",

  data() {
    return {
      name: 'Tom',
      counter: 0
    }
  },

  methods: {
    increase(num = 2) {
      this.counter += num
      console.log(this.counter)
    },

    decrease(num = 2) {
      if (this.counter > 0) {
        this.counter -= num
      }
    },

    logEvent(ev) {
      console.log(ev)
    }
  }
}
</script>