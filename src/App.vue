<template>
  <div class="academic-homepage">
    <Title />
    <Research />
    <Publications />
    <Contact />
  </div>
</template>

<script setup>
import Title from './components/sections/Title.vue'
import Publications from './components/sections/Publications.vue'
import Research from './components/sections/Research.vue'
import Contact from './components/sections/Contact.vue'
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.6;
  color: #333;
  background: #fafafa;
}

.academic-homepage {
  max-width: 900px;
  margin: 0 auto;
  padding: 40px 20px;
}

section {
  margin-bottom: 60px;
}

section h2 {
  font-size: 1.4rem;
  font-weight: 600;
  color: #222;
  border-bottom: 2px solid #42B883;
  padding-bottom: 8px;
  margin-bottom: 24px;
}

.paper-item {
  background: #fff;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 16px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  transition: box-shadow 0.2s;
}

.paper-item:hover {
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
}

.paper-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: #1a1a1a;
  margin-bottom: 8px;
}

.paper-authors {
  font-size: 0.9rem;
  color: #555;
  margin-bottom: 6px;
}

.paper-authors .me {
  color: #42B883;
  font-weight: 600;
}

.paper-meta {
  font-size: 0.85rem;
  color: #888;
  margin-bottom: 10px;
}

.paper-abstract {
  font-size: 0.9rem;
  color: #444;
  margin-bottom: 12px;
  line-height: 1.5;
}

.paper-links {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.paper-links .el-tag {
  cursor: pointer;
  font-size: 0.8rem;
}

.res-card {
  background: #fff;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 16px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  display: flex;
  gap: 20px;
  align-items: flex-start;
}

.res-icon {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  flex-shrink: 0;
}

.res-title {
  font-size: 1rem;
  font-weight: 600;
  color: #222;
  margin-bottom: 6px;
}

.res-desc {
  font-size: 0.88rem;
  color: #555;
  line-height: 1.5;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 16px;
}

.contact-item {
  background: #fff;
  border-radius: 8px;
  padding: 16px;
  display: flex;
  align-items: center;
  gap: 12px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  text-decoration: none;
  color: inherit;
  transition: box-shadow 0.2s;
}

.contact-item:hover {
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
}

.contact-item .el-icon {
  font-size: 1.4rem;
  color: #42B883;
}

.contact-item span {
  font-size: 0.9rem;
  color: #333;
}

@media (max-width: 600px) {
  .res-card {
    flex-direction: column;
  }
  .academic-homepage {
    padding: 20px 12px;
  }
}
</style>
