<template>
  <div class="home">
    <div v-for="i in 15" :key="i">
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
  color: var(--heading-text);
  font-size: 1.25rem;
  font-weight: bold;
  margin-bottom: .5rem;

  &:hover {
    color: var(--heading-text-hover);
  }
}

.home > div {
  margin-bottom: 1.5rem;
}
</style>