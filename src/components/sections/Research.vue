<template>
  <section class="research">
    <h2>🔬 Research</h2>

    <div v-for="topic in researchTopics" :key="topic.title" class="res-card">
      <div class="res-icon" :style="{ background: topic.bg }">{{ topic.icon }}</div>
      <div class="res-content">
        <div class="res-title">{{ topic.title }}</div>
        <div class="res-desc">{{ topic.desc }}</div>
        <div v-if="topic.papers" class="res-papers">
          <span v-for="p in topic.papers" :key="p" class="res-paper-tag">{{ p }}</span>
        </div>
      </div>
    </div>

    <div class="tools-section">
      <h3 class="subsection-title">🛠️ Tools & Platforms</h3>
      <div class="tools-grid">
        <div v-for="tool in tools" :key="tool.name" class="tool-card">
          <span class="tool-icon">{{ tool.icon }}</span>
          <span class="tool-name">{{ tool.name }}</span>
          <span class="tool-desc">{{ tool.desc }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const researchTopics = [
  {
    icon: '🚁',
    bg: '#e8f5e9',
    title: 'Aerial Vision-Language Navigation (AerialVLN)',
    desc: 'Enabling UAVs to understand natural language instructions and navigate in complex aerial environments. My work focuses on data-efficient fine-tuning of VLMs for UAV tasks and long-horizon trajectory planning.',
    papers: ['OpenVLN (Under Review)'],
  },
  {
    icon: '📡',
    bg: '#e3f2fd',
    title: 'Lightweight vSLAM',
    desc: 'Developing efficient simultaneous localization and mapping algorithms for UAV systems, with a focus on magnetic-field based SLAM for robust indoor/outdoor navigation.',
    papers: ['Magnetic-Field SLAM (ICAIS-ISAS 2025)'],
  },
  {
    icon: '🧠',
    bg: '#fff3e0',
    title: 'Vision-Language Models (VLM)',
    desc: 'Fine-tuning VLMs for embodied AI tasks, particularly navigation and instruction following. Interested in reinforcement learning guided VLM optimization under data constraints.',
    papers: ['OpenVLN (Under Review)', 'PathwiseRAG (EMNLP 2025)'],
  },
  {
    icon: '🤖',
    bg: '#f3e5f5',
    title: 'Embodied AI & Agent Systems',
    desc: 'Building intelligent agents that can perceive, reason, and act in 3D environments. Exploring the intersection of VLMs and reinforcement learning for embodied navigation.',
  },
]

const tools = [
  { icon: '🐍', name: 'Python', desc: 'PyTorch, NumPy' },
  { icon: '🌀', name: 'ROS/ROS2', desc: 'UAV control' },
  { icon: '🎮', name: 'Gazebo', desc: 'Simulator' },
  { icon: '☁️', name: 'AirSim', desc: 'UAV simulation' },
  { icon: '🏠', name: 'Habitat', desc: 'VLN simulation' },
  { icon: '📊', name: 'Git', desc: 'Version control' },
]
</script>

<style scoped>
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

.res-content {
  flex: 1;
}

.res-title {
  font-size: 1.05rem;
  font-weight: 600;
  color: #222;
  margin-bottom: 8px;
}

.res-desc {
  font-size: 0.88rem;
  color: #555;
  line-height: 1.6;
  margin-bottom: 8px;
}

.res-papers {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.res-paper-tag {
  background: #e8f5e9;
  color: #2e7d32;
  padding: 2px 10px;
  border-radius: 12px;
  font-size: 0.78rem;
  font-weight: 500;
}

.tools-section {
  margin-top: 32px;
}

.subsection-title {
  font-size: 1rem;
  font-weight: 600;
  color: #666;
  margin-bottom: 16px;
  padding-left: 8px;
  border-left: 3px solid #42B883;
}

.tools-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 12px;
}

.tool-card {
  background: #fff;
  border-radius: 8px;
  padding: 14px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 4px;
  transition: box-shadow 0.2s;
}

.tool-card:hover {
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
}

.tool-icon {
  font-size: 1.4rem;
  margin-bottom: 4px;
}

.tool-name {
  font-size: 0.9rem;
  font-weight: 600;
  color: #333;
}

.tool-desc {
  font-size: 0.75rem;
  color: #888;
}

@media (max-width: 600px) {
  .res-card {
    flex-direction: column;
  }
}
</style>
