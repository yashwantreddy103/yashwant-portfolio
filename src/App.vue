<template>
  <div>
    <header class="header">
      <nav>
        <ul>
          <li v-for="section in sections" :key="section.id">
            <a :href="'#' + section.id">{{ section.name }}</a>
          </li>
        </ul>
      </nav>
    </header>
    <main>
      <AboutMe id="about" />
      <Projects id="projects" />
      <Skills id="skills" />
      <Resume id="resume" />
      <Contact id="contact" />
    </main>
    <footer class="footer">
      <p>© 2025 Yashwant Reddy. All rights reserved.</p>
    </footer>
  </div>
</template>

<script setup>
import AboutMe from './components/AboutMe.vue'
import Projects from './components/Projects.vue'
import Skills from './components/Skills.vue'
import Resume from './components/Resume.vue'
import Contact from './components/Contact.vue'

const sections = [
  { id: "about", name: "About Me" },
  { id: "projects", name: "Projects" },
  { id: "skills", name: "Skills" },
  { id: "resume", name: "Resume" },
  { id: "contact", name: "Contact" },
];
</script>

<style>
/* Basic creative styling, you can improve or use Tailwind */
body {
  font-family: 'Montserrat', sans-serif;
  background: linear-gradient(135deg, #d8e2dc, #ffcad4);
  margin: 0;
}
.header {
  background: #fff;
  box-shadow: 0 2px 8px rgba(0,0,0,0.05);
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  z-index: 100;
}
.header nav ul {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}
.header nav a {
  text-decoration: none;
  color: #222;
  font-weight: 600;
  transition: color 0.2s;
}
.header nav a:hover {
  color: #ff6f91;
}
main {
  padding: 2rem;
}
.footer {
  text-align: center;
  padding: 2rem 0;
  background: #fff;
  margin-top: 2rem;
  color: #888;
  font-size: 0.9rem;
}
@media (max-width: 600px) {
  .header nav ul {
    gap: 1rem;
    font-size: 0.9rem;
  }
  main {
    padding: 1rem;
  }
}
</style>
