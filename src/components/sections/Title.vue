<template>
  <div class="title-section">
    <div class="title-header">
      <div class="avatar-wrapper">
        <img
          src="https://avatars.githubusercontent.com/u/85779787?v=4"
          alt="Peican Lin"
          class="avatar"
        />
      </div>
      <div class="title-info">
        <h1 class="name">Peican Lin</h1>
        <p class="affiliation">
          <span class="university">华南理工大学 (SCUT)</span>
          <span class="separator">·</span>
          <span class="lab">Machine Intelligence Lab (MILab)</span>
        </p>
        <p class="role">Ph.D. Candidate</p>
        <div class="research-tags">
          <el-tag v-for="tag in researchTags" :key="tag" size="small" effect="plain">{{ tag }}</el-tag>
        </div>
      </div>
    </div>

    <div class="about-me">
      <p>
        I am a Ph.D. candidate at the
        <a href="https://www2.scut.edu.cn/MachineIntelligenceLab" target="_blank">Machine Intelligence Lab (MILab)</a>.
        <a href="https://www.scut.edu.cn" target="_blank">South China University of Technology</a>
      </p>
      <p>
        My research focuses on <strong>Aerial Vision-Language Navigation</strong>,
        <strong>UAV Systems</strong>, and <strong>vSLAM</strong>.
        I am particularly interested in enabling UAVs to understand natural language instructions
        and navigate in complex aerial environments.
      </p>
    </div>

    <div class="profile-links">
      <a v-for="link in profileLinks" :key="link.label"
        :href="link.url" target="_blank" class="profile-link">
        <el-tag :type="link.type || 'primary'" effect="plain" round>
          <span class="link-icon">{{ link.icon }}</span>
          {{ link.label }}
        </el-tag>
      </a>
    </div>
  </div>
</template>

<script setup>
const researchTags = [
  'Vision-Language Navigation (VLN)',
  'Aerial VLN (AerialVLN)',
  'Unmanned Aerial Vehicles (UAV)',
  'vSLAM',
  'Embodied AI',
  'VLM Fine-tuning',
]

const profileLinks = [
  { label: 'GitHub', icon: '⌨', url: 'https://github.com/peitsan', type: 'primary' },
  { label: 'ResearchGate', icon: '📄', url: 'https://www.researchgate.net/profile/Peican-Lin', type: 'success' },
  { label: 'Email', icon: '✉', url: 'mailto:paxon.lam@gmail.com', type: 'warning' },
  { label: 'Twitter', icon: '🐦', url: 'https://twitter.com/reality3iiru', type: 'info' },
]
</script>

<style scoped>
.title-section {
  text-align: center;
  padding: 40px 20px;
}

.title-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 32px;
  margin-bottom: 28px;
  flex-wrap: wrap;
}

.avatar-wrapper {
  flex-shrink: 0;
}

.avatar {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid #42B883;
  box-shadow: 0 4px 16px rgba(66, 184, 131, 0.3);
}

.title-info {
  text-align: left;
}

.name {
  font-size: 2.2rem;
  font-weight: 700;
  color: #222;
  margin-bottom: 6px;
  letter-spacing: 0.5px;
}

.affiliation {
  font-size: 1rem;
  color: #555;
  margin-bottom: 4px;
}

.affiliation a {
  color: #42B883;
  text-decoration: none;
}

.affiliation a:hover {
  text-decoration: underline;
}

.affiliation .separator {
  margin: 0 6px;
  color: #aaa;
}

.role {
  font-size: 0.9rem;
  color: #888;
  margin-bottom: 10px;
}

.research-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.about-me {
  max-width: 700px;
  margin: 0 auto 28px;
  text-align: left;
  background: #fff;
  border-radius: 12px;
  padding: 24px 28px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.06);
}

.about-me p {
  font-size: 0.95rem;
  color: #444;
  margin-bottom: 10px;
  line-height: 1.65;
}

.about-me p:last-child {
  margin-bottom: 0;
}

.about-me a {
  color: #42B883;
  text-decoration: none;
  font-weight: 500;
}

.about-me a:hover {
  text-decoration: underline;
}

.profile-links {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
}

.profile-link {
  text-decoration: none;
}

.link-icon {
  margin-right: 4px;
}

@media (max-width: 600px) {
  .title-header {
    flex-direction: column;
    text-align: center;
  }
  .title-info {
    text-align: center;
  }
  .name {
    font-size: 1.8rem;
  }
}
</style>
