<template>
  <section class="how-it-works" id="how-it-works">
    <div class="container">
      <div
        v-motion
        :initial="{ opacity: 0, y: 30 }"
        :visible="{ opacity: 1, y: 0, transition: { duration: 600 } }"
        class="section-header"
      >
        <div class="section-badge">Cara Kerja</div>
        <h2 class="section-title">Deteksi Penyakit dalam 3 Langkah Mudah</h2>
        <p class="section-description">
          Proses yang simple dan cepat untuk mendapatkan diagnosis awal kesehatan kucing Anda
        </p>
      </div>
      
      <div class="steps">
        <div
          v-for="(step, index) in steps"
          :key="index"
          v-motion
          :initial="{ opacity: 0, x: index % 2 === 0 ? -50 : 50 }"
          :visible="{ 
            opacity: 1, 
            x: 0, 
            transition: { 
              duration: 600, 
              delay: index * 150 
            } 
          }"
          class="step-card"
          :class="{ 'step-reverse': index % 2 !== 0 }"
        >
          <div class="step-number">
            <span>{{ index + 1 }}</span>
          </div>
          
          <div class="step-content">
            <div class="step-icon">{{ step.icon }}</div>
            <h3 class="step-title">{{ step.title }}</h3>
            <p class="step-description">{{ step.description }}</p>
            <div class="step-tech">
              <span v-for="(tech, i) in step.tech" :key="i" class="tech-badge">
                {{ tech }}
              </span>
            </div>
          </div>
          
          <div class="step-visual">
            <div class="visual-box" :style="{ background: step.color }">
              <span class="visual-icon">{{ step.visualIcon }}</span>
            </div>
          </div>
          
          <div v-if="index < steps.length - 1" class="step-connector">
            <div class="connector-line"></div>
            <div class="connector-arrow">↓</div>
          </div>
        </div>
      </div>
      
      <div
        v-motion
        :initial="{ opacity: 0, y: 30 }"
        :visible="{ opacity: 1, y: 0, transition: { duration: 600, delay: 600 } }"
        class="cta-box"
      >
        <h3 class="cta-title">Siap Mencoba?</h3>
        <p class="cta-description">
          Mulai scan kucing Anda sekarang dan dapatkan hasil analisis dalam hitungan detik
        </p>
        <a href="https://app.rescat.life" class="btn btn-primary btn-lg" target="_blank">
          <span>Mulai Sekarang - Gratis</span>
          <span class="btn-icon">→</span>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
const steps = [
  {
    icon: '📸',
    title: 'Upload Foto Kucing',
    description: 'Ambil atau upload foto wajah kucing Anda dengan pencahayaan yang baik. Sistem kami akan otomatis melakukan validasi dan background removal untuk hasil optimal.',
    tech: ['MobileNetV3', 'Remove.bg API'],
    visualIcon: '🖼️',
    color: 'linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%)'
  },
  {
    icon: '🤖',
    title: 'Analisis dengan AI',
    description: 'Model machine learning kami akan mendeteksi wajah kucing, menentukan landmark points (mata, telinga, mulut), dan menganalisis setiap area untuk mengidentifikasi potensi masalah kesehatan.',
    tech: ['YOLO', 'ONNX Runtime', 'EfficientNetB1'],
    visualIcon: '🧠',
    color: 'linear-gradient(135deg, #EC4899 0%, #F59E0B 100%)'
  },
  {
    icon: '📋',
    title: 'Dapatkan Hasil & Rekomendasi',
    description: 'Terima laporan lengkap dengan confidence score, visualisasi Grad-CAM, dan rekomendasi tindakan. Anda juga bisa menemukan pet care terdekat jika diperlukan pemeriksaan lebih lanjut.',
    tech: ['Grad-CAM', 'Laravel', 'Inertia.js'],
    visualIcon: '✅',
    color: 'linear-gradient(135deg, #10B981 0%, #3B82F6 100%)'
  }
]
</script>

<style scoped>
.how-it-works {
  padding: 6rem 0;
  background: linear-gradient(180deg, #F7FAFC 0%, #FFFFFF 100%);
  position: relative;
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

.steps {
  max-width: 900px;
  margin: 0 auto;
  position: relative;
}

.step-card {
  position: relative;
  display: grid;
  grid-template-columns: auto 1fr auto;
  gap: 2rem;
  align-items: center;
  margin-bottom: 4rem;
  padding: 2rem;
  background: white;
  border-radius: 24px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  border: 1px solid #E2E8F0;
}

.step-reverse {
  grid-template-columns: auto 1fr auto;
}

.step-number {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.5rem;
  font-weight: 800;
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.3);
}

.step-content {
  padding: 0 1rem;
}

.step-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.step-title {
  font-size: 1.75rem;
  font-weight: 700;
  color: #2D3748;
  margin-bottom: 0.75rem;
}

.step-description {
  font-size: 1rem;
  line-height: 1.7;
  color: #718096;
  margin-bottom: 1rem;
}

.step-tech {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.tech-badge {
  padding: 0.25rem 0.75rem;
  background: rgba(99, 102, 241, 0.1);
  color: #6366F1;
  border-radius: 6px;
  font-size: 0.75rem;
  font-weight: 600;
}

.step-visual {
  width: 120px;
  height: 120px;
}

.visual-box {
  width: 100%;
  height: 100%;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 3rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.step-connector {
  position: absolute;
  left: 30px;
  top: 100%;
  width: 2px;
  height: 4rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.connector-line {
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, #6366F1 0%, #8B5CF6 100%);
}

.connector-arrow {
  margin-top: -10px;
  color: #8B5CF6;
  font-size: 1.5rem;
  font-weight: 700;
}

.cta-box {
  text-align: center;
  padding: 4rem 2rem;
  background: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%);
  border-radius: 32px;
  margin-top: 4rem;
  box-shadow: 0 20px 60px rgba(99, 102, 241, 0.3);
}

.cta-title {
  font-size: 2.5rem;
  font-weight: 800;
  color: white;
  margin-bottom: 1rem;
}

.cta-description {
  font-size: 1.125rem;
  color: rgba(255, 255, 255, 0.9);
  margin-bottom: 2rem;
  max-width: 640px;
  margin-left: auto;
  margin-right: auto;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s;
  font-size: 1.125rem;
}

.btn-primary {
  background: white;
  color: #6366F1;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
}

.btn-icon {
  font-size: 1.25rem;
  transition: transform 0.3s;
}

.btn-primary:hover .btn-icon {
  transform: translateX(5px);
}

@media (max-width: 768px) {
  .step-card {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .step-number {
    margin: 0 auto;
  }
  
  .step-visual {
    margin: 0 auto;
  }
  
  .step-connector {
    display: none;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .cta-title {
    font-size: 2rem;
  }
}
</style>
