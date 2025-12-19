<template>
  <section class="hero" id="hero">
    <div class="hero-bg">
      <div class="gradient-orb orb-1"></div>
      <div class="gradient-orb orb-2"></div>
      <div class="gradient-orb orb-3"></div>
    </div>
    
    <div class="container">
      <div class="hero-content">
        <div
          v-motion
          :initial="{ opacity: 0, y: 50 }"
          :visible="{ opacity: 1, y: 0, transition: { duration: 800 } }"
          class="hero-text"
        >
          <div class="badge">
            <span class="badge-icon">✨</span>
            <span>Teknologi AI untuk Kesehatan Kucing</span>
          </div>
          
          <h1 class="hero-title">
            Deteksi Penyakit Kucing dengan
            <span class="gradient-text"> AI & Computer Vision</span>
          </h1>
          
          <p class="hero-description">
            ResCat menggunakan machine learning untuk mendeteksi penyakit kulit pada kucing Anda.
            Cukup ambil foto, dan dapatkan diagnosis awal dalam hitungan detik.
          </p>
          
          <div class="hero-actions">
            <a href="https://app.rescat.life" class="btn btn-primary btn-lg" target="_blank">
              <span>Mulai Scan Gratis</span>
              <span class="btn-icon">→</span>
            </a>
            <a href="#how-it-works" class="btn btn-secondary btn-lg">
              <span>Pelajari Lebih Lanjut</span>
            </a>
          </div>
          
          <div class="hero-stats">
            <div class="stat">
              <div class="stat-value">95%+</div>
              <div class="stat-label">Akurasi Deteksi</div>
            </div>
            <div class="stat">
              <div class="stat-value">&lt;5s</div>
              <div class="stat-label">Waktu Analisis</div>
            </div>
            <div class="stat">
              <div class="stat-value">6+</div>
              <div class="stat-label">Area Deteksi</div>
            </div>
          </div>
        </div>
        
        <div
          v-motion
          :initial="{ opacity: 0, scale: 0.8 }"
          :visible="{ opacity: 1, scale: 1, transition: { duration: 1000, delay: 200 } }"
          class="hero-image"
        >
          <div class="phone-mockup">
            <div class="phone-screen">
              <div class="app-preview">
                <div class="preview-header">
                  <div class="preview-dot"></div>
                  <div class="preview-dot"></div>
                  <div class="preview-dot"></div>
                </div>
                <div class="preview-content">
                  <div class="preview-icon">🐱</div>
                  <div class="preview-title">Scan Kucing Anda</div>
                  <div class="preview-button">Mulai Deteksi</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 8rem 0 4rem;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: -1;
}

.gradient-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.5;
  animation: float 20s ease-in-out infinite;
}

.orb-1 {
  width: 500px;
  height: 500px;
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
  top: -200px;
  left: -200px;
}

.orb-2 {
  width: 400px;
  height: 400px;
  background: linear-gradient(135deg, #EC4899 0%, #F59E0B 100%);
  bottom: -150px;
  right: -150px;
  animation-delay: -7s;
}

.orb-3 {
  width: 350px;
  height: 350px;
  background: linear-gradient(135deg, #10B981 0%, #3B82F6 100%);
  top: 50%;
  right: 10%;
  animation-delay: -14s;
}

@keyframes float {
  0%, 100% {
    transform: translate(0, 0) scale(1);
  }
  33% {
    transform: translate(50px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-50px, 50px) scale(0.9);
  }
}

.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 2rem;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.2);
  border-radius: 50px;
  color: #6366F1;
  font-size: 0.875rem;
  font-weight: 600;
  margin-bottom: 2rem;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1.2;
  color: #1A202C;
  margin-bottom: 1.5rem;
}

.gradient-text {
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 50%, #EC4899 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-description {
  font-size: 1.25rem;
  line-height: 1.8;
  color: #4A5568;
  margin-bottom: 2.5rem;
  max-width: 540px;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  margin-bottom: 3rem;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.5rem;
  border-radius: 12px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s;
  border: none;
  cursor: pointer;
}

.btn-lg {
  padding: 1rem 2rem;
  font-size: 1.125rem;
}

.btn-primary {
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
  color: white;
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.3);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 40px rgba(99, 102, 241, 0.4);
}

.btn-secondary {
  background: white;
  color: #6366F1;
  border: 2px solid #6366F1;
}

.btn-secondary:hover {
  background: #6366F1;
  color: white;
}

.btn-icon {
  font-size: 1.25rem;
  transition: transform 0.3s;
}

.btn-primary:hover .btn-icon {
  transform: translateX(5px);
}

.hero-stats {
  display: flex;
  gap: 3rem;
}

.stat {
  text-align: center;
}

.stat-value {
  font-size: 2rem;
  font-weight: 800;
  color: #6366F1;
  margin-bottom: 0.25rem;
}

.stat-label {
  font-size: 0.875rem;
  color: #718096;
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.phone-mockup {
  position: relative;
  width: 320px;
  height: 640px;
  background: linear-gradient(145deg, #1A202C 0%, #2D3748 100%);
  border-radius: 40px;
  padding: 15px;
  box-shadow: 0 50px 100px rgba(0, 0, 0, 0.3);
}

.phone-screen {
  width: 100%;
  height: 100%;
  background: white;
  border-radius: 30px;
  overflow: hidden;
}

.app-preview {
  height: 100%;
  display: flex;
  flex-direction: column;
  background: linear-gradient(180deg, #F7FAFC 0%, #EDF2F7 100%);
}

.preview-header {
  display: flex;
  gap: 0.5rem;
  padding: 1.5rem;
  background: white;
}

.preview-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #E2E8F0;
}

.preview-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 2rem;
}

.preview-icon {
  font-size: 5rem;
  margin-bottom: 1rem;
}

.preview-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #2D3748;
  margin-bottom: 2rem;
}

.preview-button {
  padding: 1rem 2rem;
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
  color: white;
  border-radius: 12px;
  font-weight: 600;
}

@media (max-width: 968px) {
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-actions {
    justify-content: center;
  }
  
  .hero-stats {
    justify-content: center;
  }
  
  .phone-mockup {
    transform: scale(0.8);
  }
}
</style>
