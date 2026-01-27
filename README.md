# Anime ID Converter

![Made with PHP](https://img.shields.io/badge/Made%20with-PHP-777bb3?logo=php&logoColor=white)
![Open Source](https://img.shields.io/badge/Open%20Source-Yes-brightgreen?logo=github)
![Demo Online](https://img.shields.io/badge/Demo-Available-blue?logo=google-chrome)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow)
![GitHub Repo stars](https://img.shields.io/github/stars/ancoknamhay/ani-id-converter?style=social)
![GitHub issues](https://img.shields.io/github/issues/ancoknamhay/ani-id-converter)

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
👉 [Try the Demo Here](https://ancokplayer.win/api/converter)  
Enter a MAL or AniList ID, select the type, and see the JSON response instantly.

---

## 📌 Example Usage

### Request
```
/convert?id=59062&type=MAL_ID
```

### Response
```json
{
  "mal_id": "59062",
  "ani_id": "178025",
  "title": "Gachiakuta",
  "status": "success",
  "source": "cache"
}
```

---

### Direct AniList ID
```
/convert?id=161645&type=ANI_ID
```

Response:
```json
{
  "mal_id": null,
  "ani_id": "161645",
  "title": "Gachiakuta",
  "status": "success",
  "source": "direct"
}
```

---

## 🐘 PHP Client Example
```php
<?php
$apiUrl = "https://ancokplayer.win/api/convert?id=59062&type=MAL_ID";
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
