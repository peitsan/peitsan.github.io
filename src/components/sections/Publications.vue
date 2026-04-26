<template>
  <section class="publications">
    <h2>📚 Publications</h2>

    <!-- Under Review -->
    <div v-if="underReviewPapers.length" class="subsection">
      <h3 class="subsection-title">Under Review</h3>
      <div v-for="paper in underReviewPapers" :key="paper.title" class="paper-item">
        <div class="paper-title">
          🔥 {{ paper.title }}
          <el-tag type="warning" size="small" effect="plain" style="margin-left:8px">Under Review</el-tag>
        </div>
        <div class="paper-authors">
          <span v-for="(author, i) in paper.authors" :key="i">
            <span :class="{ me: author.me }">{{ author.name }}</span>
            <span v-if="i < paper.authors.length - 1">, </span>
          </span>
        </div>
        <div class="paper-meta">
          <span class="venue-badge">arXiv</span> ·
          arXiv: {{ paper.arxiv }} ·
          {{ paper.comments }}
        </div>
        <div class="paper-abstract">{{ paper.abstract }}</div>
        <div class="paper-links">
          <el-tag type="primary" effect="dark" @click="openLink(paper.arxivUrl)" round>
            📄 arXiv
          </el-tag>
          <el-tag type="success" effect="dark" @click="openLink(paper.pdfUrl)" round>
            📃 PDF
          </el-tag>
          <el-tag v-if="paper.codeUrl" type="info" effect="dark" @click="openLink(paper.codeUrl)" round>
            ⌨️ Code
          </el-tag>
        </div>
      </div>
    </div>

    <!-- Conference Papers -->
    <div v-if="conferencePapers.length" class="subsection">
      <h3 class="subsection-title">Conference Papers</h3>
      <div v-for="paper in conferencePapers" :key="paper.title" class="paper-item">
        <div class="paper-title">{{ paper.title }}</div>
        <div class="paper-authors">
          <span v-for="(author, i) in paper.authors" :key="i">
            <span :class="{ me: author.me }">{{ author.name }}</span>
            <span v-if="i < paper.authors.length - 1">, </span>
          </span>
        </div>
        <div class="paper-meta">
          <span class="venue-badge emnlp">{{ paper.venue }}</span> ·
          {{ paper.pages }} ·
          {{ paper.location }}
        </div>
        <div class="paper-abstract">{{ paper.abstract }}</div>
        <div class="paper-links">
          <el-tag type="primary" effect="dark" @click="openLink(paper.url)" round>
            📄 Paper
          </el-tag>
          <el-tag type="success" effect="dark" @click="openLink(paper.pdfUrl)" round>
            📃 PDF
          </el-tag>
          <el-tag v-if="paper.codeUrl" type="info" effect="dark" @click="openLink(paper.codeUrl)" round>
            ⌨️ Code
          </el-tag>
          <el-tag type="warning" effect="dark" @click="copyBibtex(paper.bibtex)" round>
            📋 BibTeX
          </el-tag>
        </div>
      </div>
    </div>

    <!-- Extended Abstracts -->
    <div v-if="extendedAbstracts.length" class="subsection">
      <h3 class="subsection-title">Extended Abstracts</h3>
      <div v-for="paper in extendedAbstracts" :key="paper.title" class="paper-item">
        <div class="paper-title">{{ paper.title }}</div>
        <div class="paper-authors">
          <span v-for="(author, i) in paper.authors" :key="i">
            <span :class="{ me: author.me }">{{ author.name }}</span>
            <span v-if="i < paper.authors.length - 1">, </span>
          </span>
        </div>
        <div class="paper-meta">
          <span class="venue-badge icais">{{ paper.venue }}</span> ·
          {{ paper.conference }}
        </div>
        <div class="paper-links">
          <el-tag v-if="paper.pdfUrl" type="success" effect="dark" @click="openLink(paper.pdfUrl)" round>
            📃 PDF
          </el-tag>
          <el-tag type="warning" effect="dark" @click="copyBibtex(paper.bibtex)" round>
            📋 BibTeX
          </el-tag>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ElMessage } from 'element-plus'
const underReviewPapers = [
{
  "title": "Fed3D: Federated 3D Object Detection",
  "authors": [
    { "name": "Suyan Dai", "me": false },
    { "name": "Chenxi Liu", "me": false },
    { "name": "Fazeng Li", "me": false },
    { "name": "Peican Lin", "me": true }
  ],
  "arxiv": "2604.15795",
  "arxivUrl": "https://arxiv.org/abs/2604.15795",
  "pdfUrl": "https://arxiv.org/pdf/2604.15795.pdf",
  "codeUrl": "",
  "comments": "",
  "abstract": "3D object detection models trained in one server plays an important role in autonomous driving, robotics manipulation, and augmented reality scenarios. However, most existing methods face severe privacy concern when deployed on a multi-robot perception network to explore large-scale 3D scene. Meanwhile, it is highly challenging to employ conventional federated learning methods on 3D object detection scenes, due to the 3D data heterogeneity and limited communication bandwidth. In this paper, we take the first attempt to propose a novel Federated 3D object detection framework (i.e., Fed3D), to enable distributed learning for 3D object detection with privacy preservation. Specifically, considering the irregular input 3D object in local robot and various category distribution between robots could cause local heterogeneity and global heterogeneity, respectively. We then propose a local-global class-aware loss for the 3D data heterogeneity issue, which could balance gradient back-propagation rate of different 3D categories from local and global aspects. To reduce communication cost on each round, we develop a federated 3D prompt module, which could only learn and communicate the prompts with few learnable parameters. To the end, several extensive experiments on federated 3D object detection show that our Fed3D model significantly outperforms state-of-the-art algorithms with lower communication cost when providing the limited local training data."
},
  {
    title: 'OpenVLN: Open-world Aerial Vision-Language Navigation',
    authors: [
      { name: 'Peican Lin', me: true },
      { name: 'Gan Sun' },
      { name: 'Chenxi Liu' },
      { name: 'Fazeng Li' },
      { name: 'Weihong Ren' },
      { name: 'Yang Cong' },
    ],
    arxiv: '2511.06182',
    arxivUrl: 'https://arxiv.org/abs/2511.06182',
    pdfUrl: 'https://arxiv.org/pdf/2511.06182',
    codeUrl: '',
    comments: '8 pages, 4 figures, under review',
    abstract:
      'Vision-language models (VLMs) have been widely applied in ground-based vision-language navigation (VLN). However, the vast complexity of outdoor aerial environments compounds data acquisition challenges and imposes long-horizon trajectory planning requirements on Unmanned Aerial Vehicles (UAVs), introducing novel complexities for aerial VLN. We propose OpenVLN, a data-efficient open-world aerial vision-language navigation framework that executes language-guided flight with limited data constraints and enhances long-horizon trajectory planning in complex aerial environments. We reconfigure a reinforcement learning framework to optimize the VLM for UAV navigation tasks, efficiently fine-tuning VLM via rule-based policies under limited training data. We introduce a long-horizon planner for trajectory synthesis that dynamically generates precise UAV actions via value-based rewards. Experiments on TravelUAV benchmark demonstrate consistent performance gains of up to 4.34% in Success Rate, 6.19% in Oracle Success Rate, and 4.07% in SPL over baseline methods.',
  },
]

const conferencePapers = [
  {
    title: 'PathwiseRAG: Multi-Dimensional Exploration and Integration Framework',
    authors: [
      { name: 'Hengrui Zhang' },
      { name: 'Pin-Siang Huang' },
      { name: 'Zhen Zhang' },
      { name: 'Peican Lin', me: true },
      { name: 'Yao-Ching Yu' },
      { name: 'Bo Hu' },
      { name: 'Yulu Du' },
    ],
    venue: 'EMNLP 2025',
    pages: '22904–22925',
    location: 'Suzhou, China',
    url: 'https://aclanthology.org/2025.emnlp-main.1167/',
    pdfUrl: 'https://aclanthology.org/2025.emnlp-main.1167.pdf',
    codeUrl: '',
    bibtex: `@inproceedings{zhang-etal-2025-pathwiserag,
  title = {{P}athwise{RAG}: Multi-Dimensional Exploration and Integration Framework},
  author = {Hengrui Zhang and Pin-Siang Huang and Zhen Zhang and Peican Lin and Yao-Ching Yu and Bo Hu and Yulu Du},
  booktitle = {Proceedings of the 2025 Conference on Empirical Methods in Natural Language Processing},
  pages = {22904--22925},
  year = {2025},
  address = {Suzhou, China},
  publisher = {Association for Computational Linguistics},
  doi = {10.18653/v1/2025.emnlp-main.1167}
}`,
    abstract:
      'Conventional retrieval-augmented generation (RAG) systems employ rigid retrieval strategies that create knowledge blind spots across domain boundaries, reasoning fragmentation when processing interdependent concepts, and contradictions from conflicting evidence sources. We introduce PathwiseRAG, which addresses these challenges through intent-aware strategy selection to eliminate blind spots, dynamic reasoning networks that capture sub-problem interdependencies to overcome fragmentation, and parallel path exploration with adaptive refinement to resolve conflicts. Evaluation across challenging benchmarks demonstrates significant improvements over state-of-the-art RAG systems, with average accuracy gains of 4.9% and up to 6.9% on complex queries.',
  },
]

const extendedAbstracts = [
  {
    title: 'Lightweight Magnetic-Field SLAM via Action Feedback',
    authors: [
      { name: 'Peican Lin', me: true },
      { name: 'Gan Sun' },
      { name: 'Fazeng Li' },
      { name: 'Weihong Ren' },
      { name: 'Yang Cong' },
    ],
    venue: 'ICAIS-ISAS 2025',
    conference: '2025 Joint International Conference on Automation-Intelligence-Safety & International Symposium on Autonomous Systems',
    pdfUrl: '',
    bibtex: `@inproceedings{lin-etal-2025-magslam,
  title = {Lightweight Magnetic-Field SLAM via Action Feedback},
  author = {Peican Lin and Gan Sun and Fazeng Li and Weihong Ren and Yang Cong},
  booktitle = {2025 Joint International Conference on Automation-Intelligence-Safety (ICAIS) \& International Symposium on Autonomous Systems (ISAS)},
  year = {2025}
}`,
  },
]

function openLink(url) {
  if (url) window.open(url, '_blank')
}

function copyBibtex(bibtex) {
  if (!bibtex) return
  navigator.clipboard.writeText(bibtex).then(() => {
    ElMessage({ message: 'BibTeX copied!', type: 'success', duration: 2000 })
  }).catch(() => {
    ElMessage({ message: 'Copy failed, please copy manually.', type: 'error', duration: 2000 })
  })
}
</script>

<style scoped>
.subsection {
  margin-bottom: 32px;
}

.subsection-title {
  font-size: 1rem;
  font-weight: 600;
  color: #666;
  margin-bottom: 16px;
  padding-left: 8px;
  border-left: 3px solid #42B883;
}

.venue-badge {
  display: inline-block;
  background: #42B883;
  color: white;
  padding: 1px 8px;
  border-radius: 4px;
  font-size: 0.75rem;
  font-weight: 600;
}

.venue-badge.emnlp {
  background: #2b7fc9;
}

.venue-badge.icais {
  background: #e67e22;
}

.me {
  color: #42B883 !important;
  font-weight: 600;
}
</style>
