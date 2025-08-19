# 📚 Python 202 Library Project

Bu proje, **Python 202 Bootcamp** kapsamında geliştirilmiş bir **Kütüphane Yönetim Sistemi**dir.  
Kullanıcılar ISBN numarası girerek kitap ekleyebilir, kitapları listeleyebilir, silebilir ve arayabilir.  
Kitap bilgileri **Open Library API** üzerinden otomatik çekilmeye çalışılır, bağlantı sağlanamazsa varsayılan bilgiler ile eklenir.  
Ek olarak, proje **FastAPI** kullanılarak REST API desteği sunar ve **pytest** ile test edilmiştir.

---

## ⚙️ Kurulum

1. **Reponun klonlanması**  
   ```bash
   git clone <repo-url>
   cd <repo-folder>
   ```

2. **Sanal ortam oluşturma ve etkinleştirme**  
   ```bash
   python -m venv venv
   # Windows: venv\Scripts\activate
   # Mac/Linux: source venv/bin/activate
   ```

3. **Bağımlılıkların yüklenmesi**  
   ```bash
   pip install -r requirements.txt
   ```

---

## ▶️ Kullanım

### Aşama 1 & 2: Konsol Uygulaması
```bash
python main.py
```

**Menü üzerinden:**
- `1` → ISBN ile kitap ekle  
- `2` → Kitap sil  
- `3` → Kitapları listele  
- `4` → Kitap ara  
- `5` → Çıkış  

Kitap bilgileri **library.json** dosyasında kalıcı olarak saklanır.

---

### Aşama 3: API Sunucusu

API’yi başlatmak için:
```bash
uvicorn api:app --reload
```
---

## 🌐 API Dokümantasyonu (Aşama 3)

### Endpointler

#### 📖 Tüm kitapları listele
```
GET /books
```

#### ➕ Yeni kitap ekle
```
POST /books
```
**Body örneği:**
```json
{
  "isbn": "9780321765723"
}
```

#### ❌ Kitap sil
```
DELETE /books/{isbn}
```

---

## 🧪 Testler

Tüm testleri çalıştırmak için:
```bash
pytest -q
```
