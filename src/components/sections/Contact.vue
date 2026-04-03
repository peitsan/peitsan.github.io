<template>
  <section class="contact">
    <h2>📬 Contact</h2>

    <div class="contact-intro">
      <p>
        I am always open to collaborations, research discussions, and opportunities.
        Feel free to reach out!
      </p>
    </div>

    <div class="contact-grid">
      <a href="mailto:paxon.lam@gmail.com" class="contact-item">
        <el-icon><Message /></el-icon>
        <div>
          <div class="contact-label">Email</div>
          <div class="contact-value">paxon.lam@gmail.com</div>
        </div>
      </a>

      <a href="https://github.com/peitsan" target="_blank" class="contact-item">
        <el-icon><Link /></el-icon>
        <div>
          <div class="contact-label">GitHub</div>
          <div class="contact-value">github.com/peitsan</div>
        </div>
      </a>

      <a href="https://www.researchgate.net/profile/Peican-Lin" target="_blank" class="contact-item">
        <el-icon><Document /></el-icon>
        <div>
          <div class="contact-label">ResearchGate</div>
          <div class="contact-value">Peican Lin</div>
        </div>
      </a>

      <a href="https://twitter.com/reality3iiru" target="_blank" class="contact-item">
        <div style="font-size:1.5rem; color:#42B883;">𝕏</div>
        <div>
          <div class="contact-label">Twitter / X</div>
          <div class="contact-value">@reality3iiru</div>
        </div>
      </a>
    </div>

    <div class="address-card">
      <h3 class="address-title">📍 Office Address</h3>
      <p>
        Machine Intelligence Lab (MILab)<br />
        School of Computer Science and Engineering<br />
        South China University of Technology<br />
        Guangzhou, Guangdong, China
      </p>
      <a href="https://www2.scut.edu.cn/MachineIntelligenceLab" target="_blank" class="lab-link">
        Visit MILab Website →
      </a>
    </div>

    <div class="footer">
      <p>
        Last updated: {{ currentDate }} · Built with Vue 3 + Element Plus
      </p>
    </div>
  </section>
</template>

<script setup>
import { Message, Document, Link } from '@element-plus/icons-vue'
import { computed } from 'vue'

const currentDate = computed(() => {
  return new Date().toLocaleDateString('en-US', { year: 'numeric', month: 'long' })
})
</script>

<style scoped>
.contact-intro {
  background: #fff;
  border-radius: 8px;
  padding: 20px 24px;
  margin-bottom: 20px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);
}

.contact-intro p {
  font-size: 0.95rem;
  color: #555;
  line-height: 1.6;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 16px;
  margin-bottom: 24px;
}

.contact-item {
  background: #fff;
  border-radius: 8px;
  padding: 16px;
  display: flex;
  align-items: center;
  gap: 14px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  text-decoration: none;
  color: inherit;
  transition: box-shadow 0.2s, transform 0.2s;
}

.contact-item:hover {
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
  transform: translateY(-2px);
}

.contact-item .el-icon {
  font-size: 1.5rem;
  color: #42B883;
  flex-shrink: 0;
}

.contact-label {
  font-size: 0.75rem;
  color: #aaa;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: 2px;
}

.contact-value {
  font-size: 0.9rem;
  color: #333;
  font-weight: 500;
}

.address-card {
  background: #fff;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  margin-bottom: 32px;
}

.address-title {
  font-size: 1rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 12px;
}

.address-card p {
  font-size: 0.9rem;
  color: #555;
  line-height: 1.7;
  margin-bottom: 12px;
}

.lab-link {
  color: #42B883;
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
}

.lab-link:hover {
  text-decoration: underline;
}

.footer {
  text-align: center;
  padding-top: 20px;
  border-top: 1px solid #eee;
}

.footer p {
  font-size: 0.8rem;
  color: #bbb;
}
</style>
