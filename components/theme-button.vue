<template>
  <button id="theming" @click="toggleTheme">{{theme}}</button>
</template>

<script>
export default {
  name: "theme-button",
  data() {
    return {
      theme: '🌞'
    }
  },
  methods: {
    toggleTheme() {
      this.theme = this.theme === '🌛' ? '🌞' : '🌛';
      document.documentElement.setAttribute('data-theme', this.theme);
      localStorage.setItem('theme', this.theme);
    }
  }
}
</script>

<style lang="scss" scoped>
#theming {
  font-size: 30px;
  border: none;
  background: none;
}
#theming:hover {
  cursor: $cursor-pointer;
}
</style>
