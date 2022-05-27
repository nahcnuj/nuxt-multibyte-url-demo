<template>
  <div>
    <h1>Test page</h1>
    <ul>
      <li>
        <NuxtLink to="/hoge/日本語/">Go to <code>/hoge/日本語/</code></NuxtLink>
      </li>
      <li>
        <NuxtLink to="/hoge/english/">Go to <code>/hoge/english/</code></NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage'
})
</script>
