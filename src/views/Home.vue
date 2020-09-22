<template>
  <div class="home">
    <div v-for="i in 50" :key="i">
      <header>Title {{ i }}</header>

      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Veritatis dicta alias autem cum maiores mollitia deserunt iure hic culpa inventore, molestias quisquam impedit perferendis atque dolore ad assumenda ratione perspiciatis?
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style lang="scss" scoped>
header {
  font-size: 1.25rem;
  font-weight: bold;
  margin-bottom: .5rem;
}
</style>