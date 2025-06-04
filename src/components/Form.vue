<template>
  <div>
    <h2>Form Bindings</h2>
    <input v-model="name" placeholder="Masukkan nama anda" />
    <p>{{ name }}</p>
  </div>
</template>

<script>
export default {
  name: 'Form',
  data() {
    return {
      name: ''
    }
  }
}
</script>