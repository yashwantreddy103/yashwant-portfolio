<template>
  <section class="contact-section">
    <h2>Contact</h2>
    <form @submit.prevent="submitForm" class="contact-form">
      <input v-model="form.name" type="text" placeholder="Your Name" required />
      <input v-model="form.email" type="email" placeholder="Your Email" required />
      <textarea v-model="form.message" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
      <p v-if="successMsg" class="success-msg">{{ successMsg }}</p>
    </form>
    <div class="contact-info">
      <p>
        <strong>Email:</strong>
        <a href="mailto:yashwantreddy65@gmail.com">yashwantreddy65@gmail.com</a>
      </p>
    </div>
    <div class="social-links">
      <a href="https://github.com/yashwantreddy103" target="_blank">GitHub</a>
      <a href="https://www.linkedin.com/in/yashwant-reddy-" target="_blank">LinkedIn</a>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
const form = ref({ name: '', email: '', message: '' })
const successMsg = ref('')

function submitForm() {
  successMsg.value = "Thank you for reaching out! I'll get back to you soon."
  form.value = { name: '', email: '', message: '' }
}
</script>

<style scoped>
.contact-section {
  padding: 2rem 0;
  text-align: center;
}
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 0.7rem;
  max-width: 400px;
  margin: auto;
}
.contact-form input,
.contact-form textarea {
  border: 1px solid #ffd6e0;
  border-radius: 8px;
  padding: 0.7rem;
  font-size: 1rem;
  width: 100%;
  outline: none;
}
.contact-form button {
  background: #ff6f91;
  color: #fff;
  border: none;
  border-radius: 8px;
  padding: 0.7rem;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  transition: background 0.2s;
}
.contact-form button:hover {
  background: #ffb7b2;
}
.success-msg {
  color: #27ae60;
  font-weight: bold;
}
.contact-info {
  margin-top: 1.2rem;
  font-size: 1.05rem;
}
.contact-info a {
  color: #ff6f91;
  text-decoration: none;
  font-weight: bold;
}
.contact-info a:hover {
  text-decoration: underline;
}
.social-links {
  margin-top: 1.5rem;
  display: flex;
  gap: 1.2rem;
  justify-content: center;
}
.social-links a {
  color: #ff6f91;
  font-weight: bold;
  text-decoration: none;
  transition: color 0.2s;
}
.social-links a:hover {
  color: #222;
}
</style>
