# Anime ID Converter

**Anime ID Converter – A lightweight microservice for mapping MyAnimeList IDs to AniList IDs, fast and cache‑friendly.**

---

## 🔖 Overview
In the anime developer community, one common challenge is dealing with **different ID systems** across platforms.  
MyAnimeList (MAL) and AniList both provide rich APIs, but their identifiers are not interchangeable.  

**Ani ID Converter** solves this problem with a simple, cache‑friendly microservice.  
It focuses on one job only: mapping IDs quickly and reliably.

---

## ✨ Features
- 🔄 **MAL → AniList ID conversion**
- ⚡ **Fast lookups** using JSON cache
- 📂 **Split cache files** per 100k MAL IDs for scalability
- 🛠️ **Developer‑friendly JSON response** with `status` and `source` fields
- 🧩 **Fallback logic** using Jikan API if AniList direct lookup fails

---

## 🚀 Live Demo
👉 [Try the Demo Here](https://www.nontongo.win/anime/converter.html)  
Enter a MAL or AniList ID, select the type, and see the JSON response instantly.

---

## 📌 Example Usage

### Request
```
/converter?id=59062&type=MAL_ID
```

### Response
```json
{
  "mal_id": "59062",
  "ani_id": "178025",
  "status": "success",
  "source": "cache"
}
```

---

### Direct AniList ID
```
/converter?id=161645&type=ANI_ID
```

Response:
```json
{
  "mal_id": null,
  "ani_id": "161645",
  "status": "success",
  "source": "direct"
}
```

---

## 🐘 PHP Client Example
```php
<?php
$apiUrl = "https://nontongo.win/converter?id=59062&type=MAL_ID";
$response = file_get_contents($apiUrl);
$data = json_decode($response, true);
print_r($data);
?>
```

---

## 📖 Why Keep It Simple?
Anime ID Converter focuses on **one job only**: mapping IDs.  
If developers need more details (titles, descriptions, genres), they can query AniList or Jikan directly.  
This keeps the converter **lightweight and efficient**, making it ideal as a **microservice** in larger projects.

---

## 🛠️ Installation
1. Clone the repo:
   ```bash
   git clone https://github.com/ancoknamhay/anime-id-converter.git
   ```
2. Configure your server (PHP + JSON cache directory).
3. Deploy and test using the demo page.

---

## 📜 License
MIT License – free to use, modify, and share.

---

## 🎯 Conclusion
Anime ID Converter is a **small but powerful tool** for anime developers.  
By bridging MAL and AniList IDs, it saves time, reduces API calls, and provides a clean foundation for building richer anime portals, apps, or integrations.
```
