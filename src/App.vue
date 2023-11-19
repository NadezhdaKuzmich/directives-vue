<template>
  <div class="container">
    <h1 class="hello">Hello, {{ name }}</h1>
    <h2>Directives:</h2>
    <div class="example">
      <h3>@click, v-if, v-else</h3>
      <button @click="flag = !flag" class="btn">Click!</button>
      <h4 v-if="flag">Hello!</h4>
      <h4 v-else>Bye, bue!</h4>
    </div>
    <div class="example">
      <h3>@click</h3>
      <div class="calculator">
        <button @click="count = count + 1" class="btn">+</button>
        <p>{{ count }}</p>
        <button @click="count = count - 1" class="btn">-</button>
      </div>
    </div>
    <div class="example">
      <div class="model">
        <h3>v-model</h3>
        <input type="text" v-model="text" />
        <p class="input-data"><span class="bold">Input:</span> {{ text }}</p>
      </div>
    </div>
    <div class="example-list">
      <h3>v-for="card in arrayCard"</h3>
      <Cards />
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import Cards from "./components/Cards";

export default defineComponent({
  name: "App",
  components: {
    Cards,
  },
  setup() {
    const name = "Nadiia";
    const flag = ref(true);
    const count = ref(0);
    const text = ref("");

    return {
      name,
      flag,
      count,
      text,
    };
  },
});
</script>

<style>
* {
  box-sizing: border-box;
}

ul {
  list-style: none;
  padding: 0;
}

img {
  width: 100%;
  object-fit: cover;
}

.container {
  max-width: 1000px;
  color: #383853;
  text-align: center;
  padding: 20px;
  margin: auto;
}

.example {
  background: #e1e3f1;
  border-radius: 8px;
  text-align: center;
  padding: 20px;
  margin: 20px 0;
}

.calculator {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
}

.btn {
  font-size: 18px;
  font-weight: bold;
  color: #fff;
  background: #9b9be0;
  border-radius: 8px;
  border: none;
  padding: 6px 12px;
  cursor: pointer;
  transition: all 0.5s ease-in-out;
}

.btn:hover {
  color: #9b9be0;
  background: #fff;
}

.model {
  max-width: 400px;
  margin: auto;
}

input {
  width: 100%;
  font-size: 18px;
  color: #343536;
  border: 1px solid #9b9be0;
  border-radius: 8px;
  padding: 8px;
}

.input-data {
  text-align: left;
}

.bold {
  font-weight: bold;
}

.example-list {
  padding: 20px 0;
}
</style>