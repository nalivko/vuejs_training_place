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
    <button @click="increase(4, $event)">+4</button>
    <span>{{ counter }}</span>
    <button v-on:click="decrease(3, $event)">-3</button>
  </div>

  <div>
    <button @click="increase(4, $event), inform()">+4</button>
    <span>{{ counter }}</span>
    <button v-on:click="decrease(3, $event), inform()">-3</button>
    <p>Status: {{ status }}</p>
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
      counter: 0,
      status: ''
    }
  },

  methods: {
    increase(num = 2, event) {
      this.counter += num
      console.log(event)
    },

    decrease(num = 2, event) {
      if (this.counter > 0) {
        this.counter -= num
      }
      console.log(event)
    },

    logEvent(ev) {
      console.log(ev)
    },

    inform() {
      this.status = "Время нажатия кнопки: " + new Date().toLocaleString();
    }
  }
}
</script>