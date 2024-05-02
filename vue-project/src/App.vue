<template>
    <div>
      <p v-bind:class="titleclass">
      Hallo Saya Agung Lexsi Kurniawan.
      </p>
      <h3 v-bind:class="titleclass">
      I'm Human.  </h3>
  
      <h1>Event Listener</h1>
      <button @click="changeColor">Change Color Here</button>
      <div :style="{ backgroundColor: bgColor, padding: '25px' }">{{ message }}</div>
  
    </div>

    

  <div class="page-container">
    <!-- Form dan judul diletakkan di div container -->
    <div class="content-container">
      <!-- Judul -->
      <div class="header">
        <h1>Selamat datang</h1>
        <p>Silakan masukkan nama Anda di bawah:</p>
      </div>

      <!-- Form yang berisi input nama dan tombol submit -->
      <form @submit.prevent="handleSubmit">
        <!-- Input nama -->
        <div>
          <label for="name">Nama:</label>
          <input type="text" id="name" v-model="name" placeholder="Masukkan nama" />
        </div>

        <!-- Tombol submit -->
        <button type="submit">Submit</button>
      </form>

      <!-- Menampilkan nama yang dimasukkan setelah submit -->
      <div v-if="submitted">
        <p>Nama yang Anda masukkan adalah: {{ name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '', // Variabel untuk menyimpan input nama
      submitted: false, // Variabel untuk melacak apakah form disubmit
    };
  },
  methods: {
    handleSubmit() {
      // Mengatur flag submitted menjadi true
      this.submitted = true;
      console.log(`Nama yang dimasukkan adalah: ${this.name}`);
    },
  },
};
</script>

<style>
/* Gaya CSS untuk mengatur posisi form dan judul ke bagian bawah halaman */
.page-container {
  /* Mengatur tinggi penuh halaman */
  height: 10vh;

  /* Mengatur tampilan flex */
  display: flex-end;

  /* Memusatkan konten secara vertikal dan horizontal */
  justify-content: center;
  align-items: flex-end; /* Untuk memindahkan konten ke bagian bawah */
}

.content-container {
  /* Anda dapat menambahkan gaya tambahan untuk container di sini */
  width: 100%; /* Menyesuaikan lebar kontainer dengan lebar halaman */
  padding: 40px; /* Menambahkan padding untuk jarak */
}

form {
  /* Gaya form */
  margin-top: 10px; /* Memberikan jarak antara form dan header */
}

input {
  margin-right: 50px;
}

button {
  /* Anda dapat menambahkan gaya tombol di sini */
}
</style>

<script setup>
import { ref, reactive } from 'vue'

const titleclass = ref("class")

const message = ref('Klik tombol di atas untuk mengubah warna!');
const bgColor = ref('black'); 

const changeColor = () => {
  bgColor.value = '#' + Math.floor(Math.random()*16777215).toString(16);
};
</script>

<style scoped>
.class {
  font-size: 25px;
  color:rgb(0, 16, 241);
}
</style>

<style>
/* Gaya CSS untuk mengatur posisi dan tata letak elemen */
.header {
  margin-bottom: 20px; /* Memberi jarak antara header dan form */
}

form {
  /* Anda dapat menambahkan gaya form di sini */
  margin-bottom: 20px;
  justify-content: flex-end;
}

input {
  margin-right: 10px;
}
</style>

<style scoped>
.class {
  font-size: 25px;
  color:blue(233, 232, 235);
}
</style>
