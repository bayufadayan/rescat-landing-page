<template>
  <section class="services" id="services">
    <div class="container">
      <div
        v-motion
        :initial="{ opacity: 0, y: 30 }"
        :visible="{ opacity: 1, y: 0, transition: { duration: 600 } }"
        class="section-header"
      >
        <div class="section-badge">Ekosistem ResCat</div>
        <h2 class="section-title">Platform Terintegrasi untuk Kesehatan Kucing</h2>
        <p class="section-description">
          Berbagai layanan yang saling terhubung untuk memberikan pengalaman terbaik
        </p>
      </div>
      
      <div class="services-grid">
        <div
          v-for="(service, index) in services"
          :key="index"
          v-motion
          :initial="{ opacity: 0, scale: 0.9 }"
          :visible="{ 
            opacity: 1, 
            scale: 1, 
            transition: { 
              duration: 600, 
              delay: index * 100 
            } 
          }"
          class="service-card"
          :class="{ featured: service.featured }"
        >
          <div class="service-header" :style="{ background: service.color }">
            <div class="service-icon">{{ service.icon }}</div>
            <div class="service-badge" v-if="service.badge">{{ service.badge }}</div>
          </div>
          
          <div class="service-body">
            <h3 class="service-title">{{ service.title }}</h3>
            <p class="service-description">{{ service.description }}</p>
            
            <div class="service-features">
              <div v-for="(feature, i) in service.features" :key="i" class="feature-item">
                <span class="feature-icon">{{ feature.icon }}</span>
                <span>{{ feature.text }}</span>
              </div>
            </div>
            
            <a 
              :href="service.url" 
              class="service-link"
              :target="service.external ? '_blank' : '_self'"
            >
              <span>{{ service.linkText }}</span>
              <span class="link-arrow">→</span>
            </a>
          </div>
        </div>
      </div>
      
      <div
        v-motion
        :initial="{ opacity: 0, y: 30 }"
        :visible="{ opacity: 1, y: 0, transition: { duration: 600, delay: 500 } }"
        class="architecture-box"
      >
        <h3 class="architecture-title">🏗️ Arsitektur Microservices</h3>
        <p class="architecture-description">
          ResCat dibangun dengan arsitektur modern yang scalable dan reliable
        </p>
        <div class="tech-stack">
          <div class="tech-item">
            <span class="tech-icon">⚡</span>
            <span>Laravel 11</span>
          </div>
          <div class="tech-item">
            <span class="tech-icon">🐍</span>
            <span>Flask ML</span>
          </div>
          <div class="tech-item">
            <span class="tech-icon">🟢</span>
            <span>Node.js</span>
          </div>
          <div class="tech-item">
            <span class="tech-icon">🎨</span>
            <span>Vue.js</span>
          </div>
          <div class="tech-item">
            <span class="tech-icon">🤖</span>
            <span>TensorFlow</span>
          </div>
          <div class="tech-item">
            <span class="tech-icon">☁️</span>
            <span>Cloud Storage</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    icon: '🌐',
    title: 'Landing Page',
    description: 'Portal utama untuk mengenal ResCat dan fitur-fiturnya',
    url: 'https://rescat.life',
    linkText: 'Kunjungi Website',
    external: true,
    color: 'linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%)',
    badge: 'Anda di sini',
    features: [
      { icon: '📱', text: 'Responsive Design' },
      { icon: '✨', text: 'Modern Animations' },
      { icon: '🚀', text: 'Fast Loading' }
    ]
  },
  {
    icon: '🐱',
    title: 'Aplikasi Utama',
    description: 'Platform deteksi penyakit kucing dengan AI dan manajemen profil lengkap',
    url: 'https://app.rescat.life',
    linkText: 'Buka Aplikasi',
    external: true,
    featured: true,
    color: 'linear-gradient(135deg, #EC4899 0%, #F59E0B 100%)',
    badge: 'Main App',
    features: [
      { icon: '🔍', text: 'AI Detection' },
      { icon: '📊', text: 'Health Tracking' },
      { icon: '🏥', text: 'Pet Care Finder' }
    ]
  },
  {
    icon: '🤖',
    title: 'ML Service',
    description: 'Layanan machine learning untuk analisis gambar dan deteksi penyakit',
    url: 'https://ml.rescat.life',
    linkText: 'API Documentation',
    external: true,
    color: 'linear-gradient(135deg, #10B981 0%, #3B82F6 100%)',
    badge: 'API',
    features: [
      { icon: '🧠', text: 'Deep Learning' },
      { icon: '⚡', text: 'Fast Inference' },
      { icon: '📈', text: '95%+ Accuracy' }
    ]
  },
  {
    icon: '💾',
    title: 'Storage Service',
    description: 'Layanan penyimpanan file dengan sistem bucket terorganisir',
    url: 'https://storage.rescat.life',
    linkText: 'Storage API',
    external: true,
    color: 'linear-gradient(135deg, #8B5CF6 0%, #EC4899 100%)',
    badge: 'Storage',
    features: [
      { icon: '📦', text: 'Bucket System' },
      { icon: '🔒', text: 'Secure Storage' },
      { icon: '🚀', text: 'CDN Ready' }
    ]
  },
  {
    icon: '📚',
    title: 'Dokumentasi',
    description: 'Dokumentasi lengkap API, panduan integrasi, dan tutorial',
    url: 'https://docs.rescat.life',
    linkText: 'Lihat Docs',
    external: true,
    color: 'linear-gradient(135deg, #F59E0B 0%, #EF4444 100%)',
    badge: 'Coming Soon',
    features: [
      { icon: '📖', text: 'API Reference' },
      { icon: '🎓', text: 'Tutorials' },
      { icon: '💡', text: 'Best Practices' }
    ]
  }
]
</script>

<style scoped>
.services {
  padding: 6rem 0;
  background: linear-gradient(180deg, #FFFFFF 0%, #F7FAFC 100%);
}

.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-badge {
  display: inline-block;
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.2);
  border-radius: 50px;
  color: #6366F1;
  font-size: 0.875rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 800;
  color: #1A202C;
  margin-bottom: 1rem;
}

.section-description {
  font-size: 1.125rem;
  color: #718096;
  max-width: 640px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.service-card {
  background: white;
  border-radius: 24px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  border: 1px solid #E2E8F0;
  transition: all 0.3s;
}

.service-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
}

.service-card.featured {
  border: 2px solid #EC4899;
}

.service-header {
  position: relative;
  padding: 3rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.service-icon {
  font-size: 4rem;
  margin-bottom: 0.5rem;
}

.service-badge {
  position: absolute;
  top: 1rem;
  right: 1rem;
  padding: 0.25rem 0.75rem;
  background: rgba(255, 255, 255, 0.9);
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 600;
  color: #2D3748;
}

.service-body {
  padding: 2rem;
}

.service-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #2D3748;
  margin-bottom: 0.75rem;
}

.service-description {
  font-size: 1rem;
  color: #718096;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.service-features {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  margin-bottom: 1.5rem;
  padding-bottom: 1.5rem;
  border-bottom: 1px solid #E2E8F0;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-size: 0.9375rem;
  color: #4A5568;
}

.feature-icon {
  font-size: 1.25rem;
}

.service-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  color: #6366F1;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s;
}

.service-link:hover {
  gap: 1rem;
}

.link-arrow {
  font-size: 1.25rem;
  transition: transform 0.3s;
}

.service-link:hover .link-arrow {
  transform: translateX(5px);
}

.architecture-box {
  background: linear-gradient(135deg, #1A202C 0%, #2D3748 100%);
  border-radius: 32px;
  padding: 3rem;
  text-align: center;
  color: white;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
}

.architecture-title {
  font-size: 2rem;
  font-weight: 800;
  margin-bottom: 1rem;
}

.architecture-description {
  font-size: 1.125rem;
  color: rgba(255, 255, 255, 0.8);
  margin-bottom: 2rem;
}

.tech-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}

.tech-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.25rem;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 12px;
  font-weight: 600;
  backdrop-filter: blur(10px);
}

.tech-icon {
  font-size: 1.25rem;
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .architecture-title {
    font-size: 1.5rem;
  }
}
</style>
