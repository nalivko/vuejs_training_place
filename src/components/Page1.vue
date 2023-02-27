<template>
  Page1
  <hr>
  <div class="font-bold">Интерполяция переменных - {{'\{\{ var \}\}'}}</div>
  <div>Имя: {{ name }}</div>
  <div>Возраст: {{ age > 20 ? 'больше 20 лет' : 'меньше 20 лет' }}</div>
  <hr>
  <div class="font-bold">Значение возвращаеи метод объекта</div>
  <div>{{ sayHai() }}</div>
  <div>12 часов {{ welcome(12) }}</div>
  <div>22 часа {{ welcome(22) }}</div>
  <hr>
  <div class="font-bold">v-text</div>
  <div v-text="name"></div>
  <div v-text="age"></div>
  <hr>
  <div class="font-bold">Привязка к атрибутам v-bind:href="" v-bind:title=""</div>
  <a v-bind:href="link" v-bind:title="title">{{ text }}</a>
  <div>Сокращённая форма :href="" :title=""</div>
  <a :href="link" :title="title">{{ text }}</a>
  <hr>
  <div class="font-bold">Однократная привязка v-once</div>
  <div v-once>{{ message }}</div>
  <hr>
  <div class="font-bold">Привязка к коду html v-html</div>
  <div v-html="html_message"></div>
  <div>{{ html_message }}</div>
</template>

<script>
export default {
  name: "Page1",

  data() {
    return {
      name: 'Tom',
      age: 25,
      text: 'Google',
      title: 'google.com',
      link:'https://google.com',
      message: 'Hello !',
      html_message: '<h2>Hello !</h2>',
    }
  },

  methods: {
    sayHai() {
      return `Привет, меня зовут ${this.name}`
    },

    welcome(hour) {
      if(hour > 21) {
        return 'Доброй ночи'
      } else if(hour > 16) {
        return 'Добрый вечер'
      } else if(hour > 11) {
        return 'Добрый день'
      } else {
        return 'Доброе утро'
      }
    },
  }
}

</script>

<style>
.font-bold {
  font-weight: bold;
}
</style>