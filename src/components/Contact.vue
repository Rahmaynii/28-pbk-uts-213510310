<template>
  <div class="contact-container">
    <h1>Hubungi Kami</h1>
    <p>Jika Anda memiliki pertanyaan atau masalah, silakan hubungi kami melalui formulir di bawah ini.</p>
    <form>
      <div class="form-group">
        <label for="name">Nama</label>
        <input type="text" id="name" name="name" placeholder="Masukkan nama Anda" required>
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" name="email" placeholder="Masukkan alamat email Anda" required>
      </div>
      <div class="form-group">
        <label for="message">Pesan</label>
        <textarea id="message" name="message" placeholder="Masukkan pesan Anda" required></textarea>
      </div>
      <button type="submit">Kirim Pesan</button>
    </form>
  </div>
</template>

<style>
.contact-container {
  margin: 50px auto;
  text-align: center;
  max-width: 800px;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

form {
  display: inline-block;
  text-align: left;
}

.form-group {
  margin-bottom: 20px;
}

label {
  font-size: 1.2rem;
  display: block;
  margin-bottom: 5px;
  text-align: left;
}

input[type="text"],
input[type="email"],
textarea {
  padding: 10px;
  font-size: 1.2rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 100%;
  box-sizing: border-box;
}

button[type="submit"] {
  background-color: #007bff;
  border: none;
  color: #fff;
  padding: 10px 20px;
  font-size: 1.2rem;
  border-radius: 4px;
  cursor: pointer;
}
</style>
