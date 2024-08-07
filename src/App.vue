<template>
  <header>
    <nav>
      <RouterLink to="/">
        <img src="/youtube.png" alt="Youtube logo">
      </RouterLink>
      <form>
        <input type="text" placeholder="Search...">
      </form>
      <font-awesome-icon icon="magnifying-glass" />
    </nav>
  </header>
  <RouterView />
</template>

<script>
export default {
  name: 'App',
}
</script>
