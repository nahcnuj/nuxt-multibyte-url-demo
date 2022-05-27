<template>
  <div>
    <h1>Demo</h1>
    <h2>{{ data.title }}</h2>
    <p>{{ data.body }}</p>
    <nav>
      <NuxtLink to="/">Go back</NuxtLink>
    </nav>
    <div v-if="$route.params.id === '日本語'">
      <p>以下のように表示されて欲しい。</p>
      <div>
        <h2>ハローワールド</h2>
        <p>payload.js の読み込みに失敗する</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

type DataType = { title: string; body: string }
type PayloadType = { data: DataType }

export default Vue.extend({

  // acutually set through payload
  asyncData: ({ payload }: { payload: PayloadType }) => payload,

  // set dummy data for type inference 
  data: () => ({ data: {} as DataType })
})
</script>

