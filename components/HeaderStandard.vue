<template>
  <fragment>
    <h1>I'm the test header</h1>
    <p>Number from data: {{ number }}</p>
  </fragment>
</template>

<script>
const number = 5
export default {
  data() {
    return {
      foo: 'bar',
      number
    }
  }
}
</script>
