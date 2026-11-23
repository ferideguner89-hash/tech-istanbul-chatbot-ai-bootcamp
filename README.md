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
