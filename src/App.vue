<script>
export default{
  data() {
    return {
      mode: 'light'
    }
  },
  methods: {
    handleClick() {
      return this.mode == 'light' ? this.mode = 'dark' : this.mode = 'light'
    }
  }
}
</script>

<template>
  <div id="app">
    <div class="box" :color-mode="mode">
      <button  @click="handleClick">toggle</button>
      <div class="container">
        <div class="item item1"></div>
        <div class="item item2"></div>
        <div class="item item3"></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.box {
  background-color: var(--surface3);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5em;
  height: 50em;
  transition: 0.3s;
}
/* Light Mode */
.box[color-mode="light"] {
  --surface1: #e6e6e6;
  --surface2: #f2f2f2;
  --surface3: #ffffff;
  --element1: #111111;
  --element2: #222222;
  --element3: #333333;
  --elementInverse: #eee;
  --primary: #01408e;
  --secondary: #3c5d5c;
  --tertiary: #fff7d6;
}

/* Dark Mode */
.box[color-mode="dark"] {
  --surface1: #262626;
  --surface2: #333333;
  --surface3: #404040;
  --element1: #eeeeee;
  --element2: #dddddd;
  --element3: #cccccc;
  --elementInverse: #111;
  --primary: #8fceff;
  --secondary: #72faca;
  --tertiary: #eee8a9;
}
.container {
  display: flex;
  gap: 4em;
}
.item {
  border-radius: 50%;
  width: 100px;
  height: 100px;
}
.item1 {
  background-color: var(--primary);
}
.item2 {
  background-color: var(--secondary);
}
.item3 {
  background-color: var(--tertiary);
}
button {
  background-color: var(--element1);
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 0.6em 1.2em;
  font-size: 1em;
  font-weight: 500;
  color: var(--surface3);
  transition: 0.2s;
  cursor: pointer;
}
button:hover {
  background-color: var(--element3);
  color: var(--surface1);
}
</style>
