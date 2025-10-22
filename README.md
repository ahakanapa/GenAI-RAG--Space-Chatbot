<<<<<<< HEAD
# GenAI-RAG--Space-Chatbot
RAG Tabanlı Chatbot Projesi

🌌 🤖 Akbank GenAI Giriş Bootcamp RAG Space Chatbot

Bu proje, Generative AI Giriş Bootcamp kapsamında geliştirilmiş Türkçe bir RAG (Retrieval-Augmented Generation) tabanlı bilgi asistanıdır.
Chatbot, verilen bir metin dosyasındaki (TXT) bilgileri kullanarak, kullanıcı sorularına Gemini 2.5 Flash modeliyle yanıt verir.
Uygulama Streamlit tabanlı bir web arayüzü üzerinden çalışır.

📋 Proje Hakkında

Bu proje, Google Gemini API, ChromaDB, ve LangChain benzeri RAG pipeline yapısı kullanarak geliştirilmiştir.
Kullanıcıdan alınan bir soru, vektör veritabanı (ChromaDB) üzerinden en alakalı metin parçalarıyla eşleştirilir.
Sonrasında, bu bilgiler Gemini LLM modeli tarafından işlenerek doğal Türkçe bir yanıt üretilir.

Proje, veri kaynağı olarak bilgi_kaynagi.txt adlı bir uzay, bilim veya genel bilgi metin dosyasını kullanır.
Böylece, kullanıcı “Dünyanın yüzde kaçı sudur?”, “Kara delik nedir?”, “Yapay zekanın bankacılıktaki uygulamaları nelerdir?” gibi sorulara anlamlı yanıtlar alabilir.

🧠 Kullanılan Teknolojiler
Google Gemini API	(Embedding ve metin üretimi)
ChromaDB	(Vektör tabanlı belge arama)
Streamlit	(Web arayüzü)
dotenv	(API anahtarı yönetimi)
tiktoken	(Metin tokenizasyonu ve parçalama)
Python (typing, os)	(Uygulama mantığı ve sistem yönetimi)
⚙️ Proje Yapısı
.
├── app.py                 # Streamlit tabanlı web arayüzü
├── rag_functions.py       # RAG pipeline ve embedding fonksiyonları
├── bilgi_kaynagi.txt      # Bilgi kaynağı (uzay veya konuya özel metin)
├── requirements.txt       # Python bağımlılıkları
├── .env                   # API KEY
└── README.md              # Bu dosya

🚀 Kurulum
1. Sanal Ortam Oluşturun (Opsiyonel ama önerilir)
python3 -m venv venv
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate   # Windows

2. Gerekli Paketleri Yükleyin
pip install -r requirements.txt

3. API KEY'inizi Ayarlayın

Proje kök dizinine .env adlı bir dosya oluşturun ve aşağıdaki satırı ekleyin:

GEMINI_API_KEY=your_google_api_key_here


🔑 Google API Key: Google AI Studio
 üzerinden alınabilir.

4. Bilgi Kaynağını Ekleyin

Kök dizine bilgi_kaynagi.txt adlı bir dosya oluşturun.
Bu dosya, chatbot’un yanıt vereceği metin bilgisini içermelidir (örnek: uzay, bilim, teknoloji konuları).

5. Uygulamayı Çalıştırın
streamlit run app.py


Uygulama tarayıcınızda otomatik olarak açılacaktır:
👉 http://localhost:8501

💡 Nasıl Çalışır?

Veri Okuma: bilgi_kaynagi.txt dosyası okunur.

Parçalama: Metin tiktoken ile 1000 token’lık bölümlere ayrılır.

Embedding: Her parça, Gemini text-embedding-004 modeliyle vektöre dönüştürülür.

Vektör Veritabanı: Embedding’ler ChromaDB koleksiyonunda saklanır.

Sorgu: Kullanıcının sorusu embedding’e çevrilir ve en benzer 3 metin parçası bulunur.

Yanıt Üretimi: Gemini 2.5 Flash modeli, bu bağlamı kullanarak doğal bir yanıt oluşturur.
=======
🌌 Uzay Bilgi Chatbotu

Generative AI 101 Bootcamp kapsamında hazırlanmış Türkçe RAG (Retrieval-Augmented Generation) tabanlı uzay bilgi asistanı.

📋 Proje Hakkında

Bu proje, uzay ve astronomi konularında sorular sorabileceğiniz bir yapay zekâ destekli bilgi asistanıdır.
Kullanıcı, “Güneş sistemi nasıl oluştu?”, “Işık yılı nedir?”, “Evrende en sıcak gezegen hangisidir?” gibi sorular sorarak anında yanıt alabilir.
Chatbot, önceden işlenmiş uzay temalı bir metin koleksiyonundan (NASA, ESA, bilimsel makaleler, ansiklopedik bilgiler vb.) ilgili bölümleri vektör tabanlı arama ile bulur ve Gemini modeliyle doğal bir Türkçe yanıt üretir.

🛠️ Kullanılan Teknolojiler

LangChain / Haystack → RAG (Retrieval-Augmented Generation) pipeline framework

Streamlit → Web arayüzü

Sentence Transformers → Türkçe embedding modeli (örnek: paraphrase-multilingual-MiniLM-L12-v2)

Google Gemini → Text generation modeli

ChromaDB → Vektör veritabanı

Hugging Face Datasets → Veri yönetimi ve uzay verileri

🚀 Kurulum
1. Gerekli Paketleri Yükleyin
# Virtual environment oluşturun (opsiyonel ama önerilir)
python3 -m venv spacebot-env
source spacebot-env/bin/activate  # macOS/Linux
# spacebot-env\Scripts\activate  # Windows

# Paketleri yükleyin
pip install -r requirements.txt

2. API Anahtarlarını Ayarlayın

Proje kök dizininde .env dosyası oluşturun ve içine aşağıdakileri yazın:

GOOGLE_API_KEY=your_google_api_key_here


🔑 Google API Key: Google AI Studio
 üzerinden alabilirsiniz.

3. Uygulamayı Çalıştırın
streamlit run app.py


Tarayıcınızda otomatik olarak açılacaktır (genellikle http://localhost:8501).

📁 Proje Yapısı
.
├── app.py               # Ana uygulama dosyası
├── requirements.txt     # Python bağımlılıkları
├── .env                 # API anahtarı (git'e eklenmez)
├── README.md            # Bu dosya
└── data/                # Uzay bilgileri (metin tabanlı kaynaklar)

💡 Nasıl Çalışır?

Veri Yükleme: Uzay konulu kaynak metinler içeri aktarılır.

Belge İşleme: Metinler küçük parçalara (chunk) bölünür.

Embedding: Her parça, Türkçe destekli embedding modeliyle vektöre dönüştürülür.

Vektör Veritabanı: Vektörler ChromaDB içinde saklanır.

Sorgulama: Kullanıcının sorusu embedding’e çevrilir ve en ilgili parçalar bulunur.

Yanıt Üretimi: Gemini modeli, ilgili belgeleri kullanarak açıklayıcı bir yanıt oluşturur.
>>>>>>> 14af3931 (Initial commit - RAG Chatbot project)

🪐 Örnek Sorular

“Dünyanın yüzde kaçı sudur?”

<<<<<<< HEAD
“Kara delik nedir?”

“Işık yılı ne anlama gelir?”

“Uzayda sıcaklık neden bu kadar düşüktür?”

🧩 Çözüm Mimarisi
Kullanıcı Girdisi
      ↓
 [Embedding Model] (Gemini Embedding API)
      ↓
 [ChromaDB] → En ilgili metin parçalarını getir
      ↓
 [RAG Prompt Oluşturma]
      ↓
 [Gemini 2.5 Flash] → Nihai cevabı üret
      ↓
 Streamlit Arayüzü → Sonuç Gösterimi

🖥️ Canlı Demo (Opsiyonel)

Henüz deploy edilmediyse, aşağıdaki gibi doldurabilirsin:

🔗 Canlı Uygulamayı Aç

Alternatif:
Projeyi Streamlit Cloud
 veya Hugging Face Spaces
 üzerinde ücretsiz deploy edebilirsin.

🖼️ Ekran Görüntüleri
Arayüz	Açıklama

	Streamlit tabanlı chatbot ekranı

	Gemini modeli yanıt örneği

İpucu: Gerçek ekran görüntülerini docs/ klasörüne ekleyip buradaki bağlantıları düzenleyebilirsin.

⚠️ Önemli Notlar

.env dosyasını asla GitHub’a yüklemeyin.

İlk çalıştırmada embedding işlemi birkaç dakika sürebilir.

bilgi_kaynagi.txt dosyası çok büyükse işlemler yavaşlayabilir.

ChromaDB klasörü (chroma_db/) otomatik olarak oluşturulur.

🐛 Sorun Giderme
Sorun	Olası Çözüm
❌ GEMINI_API_KEY bulunamadı	.env dosyasını kontrol edin
ModuleNotFoundError	pip install -r requirements.txt çalıştırın
Veritabanı kurulum hatası	İnternet bağlantınızı ve API anahtarınızı doğrulayın
Streamlit çalışmıyor	streamlit run app.py komutunu doğru dizinde çalıştırın
=======
“Işık yılı ne anlama gelir?”

“En büyük yıldız hangisidir?”

“Kara delikler nasıl oluşur?”

“Mars’ta yaşam mümkün mü?”

⚠️ Önemli Notlar

İlk çalıştırmada embedding oluşturma birkaç dakika sürebilir.

.env dosyasını GitHub’a yüklemeyin.

Veri dosyaları sadece lokal veya bulut ortamda bulunmalıdır.

Streamlit cache sistemi sonraki başlatmalarda hız kazandırır.

🔧 Modüler Yapı (Opsiyonel)

Projeni daha modüler hale getirmek için aşağıdaki dosya yapısına ayırabilirsin:

config.py              # Sabitler ve ayarlar
data_processing.py     # Veri yükleme ve işleme
vector_store.py        # Vektör veritabanı yönetimi
rag_pipeline.py        # RAG pipeline oluşturma
app.py                 # Streamlit arayüzü

📚 Öğrenme & Geliştirme Önerileri

“RAG pipeline”, “embedding modeli” ve “vector database” kavramlarını derinlemesine incele.

LangChain ve Haystack dökümantasyonlarını karşılaştır.

Kendi embedding modelini eğitmeyi dene (Hugging Face Trainer modülüyle).

Uzay temalı metinleri GPT veya Gemini ile genişletip veri çeşitliliğini artır.

🐛 Sorun Giderme
Sorun	Çözüm
ModuleNotFoundError	pip install -r requirements.txt
API key invalid	.env dosyasını kontrol et
Embedding işlemi çok yavaş	Daha küçük bir model veya GPU kullan
Streamlit açılmıyor	streamlit run app.py komutunu doğru dizinde çalıştır
>>>>>>> 14af3931 (Initial commit - RAG Chatbot project)
📝 Lisans

Bu proje eğitim amaçlıdır ve ticari kullanım için tasarlanmamıştır.

🤝 Katkıda Bulunma

<<<<<<< HEAD
Öneri, hata bildirimi veya geliştirme talebiniz varsa GitHub üzerinden issue açabilirsiniz.
Yıldız 🌟 bırakmayı unutmayın!
=======
Öneri, hata raporu veya geliştirme isteği için GitHub üzerinden issue açabilirsiniz.
Yıldız 🌟 bırakmayı unutmayın!
>>>>>>> 14af3931 (Initial commit - RAG Chatbot project)
