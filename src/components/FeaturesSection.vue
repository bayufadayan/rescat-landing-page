<template>
  <section class="features" id="features">
    <div class="container">
      <div
        v-motion
        :initial="{ opacity: 0, y: 30 }"
        :visible="{ opacity: 1, y: 0, transition: { duration: 600 } }"
        class="section-header"
      >
        <div class="section-badge">Fitur Unggulan</div>
        <h2 class="section-title">Teknologi AI untuk Kesehatan Kucing Anda</h2>
        <p class="section-description">
          Sistem deteksi penyakit kulit yang komprehensif dengan teknologi machine learning terkini
        </p>
      </div>
      
      <div class="features-grid">
        <div
          v-for="(feature, index) in features"
          :key="index"
          v-motion
          :initial="{ opacity: 0, y: 50 }"
          :visible="{ 
            opacity: 1, 
            y: 0, 
            transition: { 
              duration: 600, 
              delay: index * 100 
            } 
          }"
          class="feature-card"
        >
          <div class="feature-icon" :style="{ background: feature.color }">
            {{ feature.icon }}
          </div>
          <h3 class="feature-title">{{ feature.title }}</h3>
          <p class="feature-description">{{ feature.description }}</p>
          <ul class="feature-list">
            <li v-for="(item, i) in feature.points" :key="i">
              <span class="check-icon">✓</span>
              {{ item }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const features = [
  {
    icon: '🔍',
    title: 'Scan & Deteksi AI',
    description: 'Upload foto kucing dan dapatkan analisis komprehensif menggunakan computer vision',
    color: 'linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%)',
    points: [
      'Deteksi 6 area wajah (mata, telinga, mulut)',
      'Background removal otomatis',
      'Akurasi tinggi dengan EfficientNetB1',
      'Hasil dalam hitungan detik'
    ]
  },
  {
    icon: '📊',
    title: 'Manajemen Profil',
    description: 'Kelola data kucing Anda dan tracking riwayat kesehatan secara lengkap',
    color: 'linear-gradient(135deg, #EC4899 0%, #F59E0B 100%)',
    points: [
      'Multiple cats per user',
      'Riwayat scan lengkap',
      'Data breed & tanggal lahir',
      'Avatar custom untuk tiap kucing'
    ]
  },
  {
    icon: '🏥',
    title: 'Pet Care Finder',
    description: 'Temukan klinik dan pet care terdekat dengan informasi lengkap',
    color: 'linear-gradient(135deg, #10B981 0%, #3B82F6 100%)',
    points: [
      'Database klinik lengkap',
      'Jam operasional real-time',
      'Navigasi GPS terintegrasi',
      'Kontak langsung tersedia'
    ]
  },
  {
    icon: '📚',
    title: 'Artikel Edukatif',
    description: 'Pelajari cara merawat kucing dengan artikel dari ahli veteriner',
    color: 'linear-gradient(135deg, #8B5CF6 0%, #EC4899 100%)',
    points: [
      'Tips kesehatan kucing',
      'Panduan perawatan harian',
      'Pencegahan penyakit',
      'Update artikel berkala'
    ]
  },
  {
    icon: '🔐',
    title: 'Keamanan Data',
    description: 'Data Anda aman dengan enkripsi dan sistem autentikasi modern',
    color: 'linear-gradient(135deg, #F59E0B 0%, #EF4444 100%)',
    points: [
      'Login dengan Google OAuth',
      'Data terenkripsi',
      'Privacy terjamin',
      'Backup otomatis'
    ]
  },
  {
    icon: '⚡',
    title: 'Performa Tinggi',
    description: 'Infrastruktur cloud yang cepat dan reliable untuk pengalaman terbaik',
    color: 'linear-gradient(135deg, #3B82F6 0%, #10B981 100%)',
    points: [
      'Response time &lt;5 detik',
      'Cloud storage scalable',
      'ML inference optimized',
      'Uptime 99.9%'
    ]
  }
]
</script>

<style scoped>
.features {
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

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: white;
  border-radius: 24px;
  padding: 2.5rem;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  border: 1px solid #E2E8F0;
  transition: all 0.3s;
}

.feature-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
}

.feature-icon {
  width: 70px;
  height: 70px;
  border-radius: 18px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  margin-bottom: 1.5rem;
}

.feature-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #2D3748;
  margin-bottom: 0.75rem;
}

.feature-description {
  font-size: 1rem;
  color: #718096;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.feature-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.feature-list li {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.5rem 0;
  color: #4A5568;
  font-size: 0.9375rem;
}

.check-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 20px;
  height: 20px;
  background: rgba(16, 185, 129, 0.1);
  color: #10B981;
  border-radius: 50%;
  font-size: 0.75rem;
  font-weight: 700;
  flex-shrink: 0;
}

@media (max-width: 768px) {
  .features-grid {
    grid-template-columns: 1fr;
  }
  
  .section-title {
    font-size: 2rem;
  }
}
</style>
