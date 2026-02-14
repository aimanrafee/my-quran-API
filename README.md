# 📖 My Quran API

Repository ini mengandungi data Al-Quran lengkap dalam format JSON yang dihoskan secara statik untuk kegunaan projek **Amalan Hidupku** dan aplikasi web Islamik yang lain. Data diambil dan diproses daripada API Quran.com (v4).

## 🚀 Struktur Folder & Endpoint
Semua data boleh diakses menggunakan URL GitHub Raw atau melalui CDN (JSDelivr).

### 1. Senarai Surah (Menu)
* **URL:** `https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/chapters/all.json`

### 2. Bacaan Mengikut Surah (114 Fail)
Setiap fail mengandungi Teks Arab Uthmani dan 4 Terjemahan/Tafsir ringkas.
* **URL:** `https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/chapters/{nombor_surah}.json`

### 3. Bacaan Mengikut Juzuk (30 Fail)
* **URL:** `https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/juz/{nombor_juz}.json`

### 4. Bacaan Mengikut Mukasurat (604 Fail)
* **URL:** `https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/pages/{nombor_mukasurat}.json`

---

## 📑 Kandungan Data (Translations & Tafsir)

Dalam setiap fail `chapters`, `juz`, dan `pages`, setiap ayat mempunyai senarai `translations` mengikut urutan ID berikut:

| Index | ID | Jenis | Nama Terjemahan / Tafsir |
|-------|----|-------|--------------------------|
| `[0]` | 39 | MS | Abdullah Basmeih (Bahasa Melayu) |
| `[1]` | 20 | EN | Saheeh International (English) |
| `[2]` | 16 | AR | Tafsir Al-Jalalayn (Arabic) |
| `[3]` | 161| AR | Tafsir Al-Muyassar (Arabic) |

---

## 📚 Tafsir Mendalam (Ibnu Kathir)
Fail tafsir diasingkan daripada fail bacaan utama untuk memastikan prestasi aplikasi yang pantas.

* **Tafsir Ibnu Kathir (Bahasa Melayu/ID):**
  `https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/tafsir/ibnu-kathir-ms/{nombor_surah}.json`
* **Tafsir Ibnu Kathir (Arabic):**
  `https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/tafsir/ibnu-kathir-ar/{nombor_surah}.json`

---

## 🛠️ Cara Penggunaan (JavaScript Fetch)
```javascript
fetch('[https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/chapters/1.json](https://cdn.jsdelivr.net/gh/aimanrafee/my-quran-API@main/chapters/1.json)')
  .then(res => res.json())
  .then(data => {
    console.log(data.verses[0].text_uthmani); // Papar teks Arab
    console.log(data.verses[0].translations[0].text); // Papar terjemahan Melayu
  });
📜 Lesen & Sumber
Data disediakan oleh Quran.com API.

Projek ini bertujuan untuk memudahkan akses data Al-Quran bagi pembangun aplikasi tempatan.


---
