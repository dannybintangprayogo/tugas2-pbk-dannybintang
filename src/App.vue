<template>
  <div>
    <h1>{{ greeting }}</h1>
    <p>{{ message }}</p>
    <input type="text" v-model="inputText">
    <div :class="{ active: isActive }" :style="{ color: textColor }">Elemen dengan class dan style bindings</div>
    <button @click="changeMessage">Ubah Pesan</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      greeting: 'Halo!',
      message: 'Ini adalah pesan default.',
      isActive: true,
      textColor: 'black',
      inputText: ''
    }
  },
  methods: {
    changeMessage() {
      this.message = this.inputText; // Mengubah pesan sesuai dengan input teks
      this.isActive = !this.isActive; // Toggle class active
      this.textColor = this.isActive ? 'black' : 'red'; // Ganti warna teks
    }
  }
}
</script>

<style scoped>
.active {
  font-weight: bold;
}
</style>
