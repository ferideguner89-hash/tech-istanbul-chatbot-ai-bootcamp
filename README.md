# Tech Istanbul – Chatbot ve Konuşma AI Geliştirme Bootcamp

1. hafta kapsamında kendi bilgisayarım üzerinde self-hosted n8n kurulumu yaptım ve başlangıç iş akışını oluşturdum.

## 1. Hafta Bilgileri
- **Kurulum Ortamı:** Kendi bilgisayarım (lokal)
- **Kurulum Yöntemi:** Docker
- **n8n Sürümü:** 2.45.5
- **İş Akışı:** `week-01/week1-workflow.json` (`Manual Trigger` → `Edit Fields`)
2. hafta kapsamında Telegram üzerinden gelen doğal Türkçe stok ve satış mesajlarını yorumlayıp Google Sheets verilerini güncelleyen mini ERP iş akışını oluşturdum.

## 2. Hafta Bilgileri

- **Kullanılan Sistem:** Telegram Bot → n8n + LLM → Google Sheets → Telegram yanıtı
- **Desteklenen İşlemler:** Stok sorgulama, satış düşme, iade/mal girişi ekleme, doğrudan stok güncelleme, konuşma bağlamından son ürünü hatırlama ve belirsiz mesajlarda açıklama isteme
- **İş Akışı:** `week-02/workflow.json` (Telegram Trigger → If → Code → Gemini → Google Sheets → Telegram)
- **Ek Dosyalar:** `week-02/screenshots/`
- 
3. hafta kapsamında Pegasus Hava Yolları'nın kamuya açık kaynaklarını kullanarak n8n üzerinde indeksleme ve RAG (Retrieval-Augmented Generation) destekli sohbet iş akışlarını oluşturdum.

## 3. Hafta Bilgileri

* **Seçilen Şirket:** Pegasus Hava Yolları
* **Kaynaklar:** Pegasus BolBol Harca sayfası (`flypgs.com/bolbol/bolbol-harca`) ve Pegasus Uçuş Paketleri sayfası (`flypgs.com/seyahat-hizmetlerimiz/ucus-ile-ilgili-hizmetlerimiz/ucus-paketleri`)
* **Kullanılan Sistem:** n8n + Gemini Embedding (`gemini-embedding-001`, 768 boyut) + Supabase (`pgvector` / `match_documents`) + Gemini Chat LLM + n8n Chat Trigger
* **RAG Ayarları:** Chunk Size: `800` karakter, Chunk Overlap: `100` karakter, Top-K (`match_count`): `10`
* **İş Akışları:** `week-03/Pegasus - Indexleme.json`, `week-03/Pegasus RAG - İkinci Kaynak.json`, `week-03/Pegasus RAG Chatbot.json`

* 4. Hafta kapsamında n8n üzerinde Apify ve web araması ile bölgesel bağımsız işletme keşfi yapan, doğrulanan kayıtları Google Sheets müşteri havuzuna ve Supabase (`pgvector`) bilgi tabanına kaydeden araştırma akışı ile bu veritabanı üzerinden yanıt üreten RAG sohbet iş akışlarını oluşturuldu.

## 4. Hafta Bilgileri

* **Test Senaryosu:** `Levent, İstanbul` bölgesinde zincir veya franchise olmayan en fazla `3` bağımsız `pizzacı` işletmesinin bulunması ve doğrulanması
* **Kullanılan Sistem:** Apify Google Maps Scraper → Tavily Web Search → JavaScript Doğrulama ve Filtreleme → Google Sheets (`Musteri Havuzu`) + Supabase (`pgvector` / `documents`) + Gemini Embedding & Chat Model + n8n Chat Trigger
* **İş Akışları:**
  * Araştırma ve Kayıt Akışı: `week-04/Odev04 - Arastirma.json` (Manual Trigger → Edit Fields → Apify Actor → Remove Duplicates → Tavily Search → Set / Birleştir → Code in JavaScript → Filter → Limit (3) → Google Sheets Append → Supabase Vector Store)
  * Sohbet / RAG Akışı: `week-04/Sohbet _ RAG Akışı.json` (Chat Trigger → AI Agent → Google Gemini Chat Model + Supabase Vector Store Tool + Embeddings Google Gemini)
* **Test Sorusu:** `"Levent'te müşteri havuzuna eklenen bağımsız pizzacılar hangileri? Her biri hakkında bir doğrulanmış bilgi ve kaynak bağlantısı ver."`

