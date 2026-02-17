# MC Mapping Viewer / Minecraft Mapping Görüntüleyici

> **Made by 0b42** (aka **ebukeh**)

Modern, hızlı ve kullanımı kolay bir Minecraft mapping görüntüleme aracı.  
A modern, fast, and easy-to-use Minecraft mapping viewer.

---

## 🇹🇷 Türkçe

## Proje Hakkında
`mc_wiewer.html`, ProGuard tarzı mapping dosyalarını (`.txt`) okuyup görsel bir tabloda incelemek için tasarlanmış tek dosyalık (single-file) bir web aracıdır.

Öne çıkan amaçlar:
- Mapping analizini hızlı hale getirmek
- Sınıf / metod / alan aramalarını kolaylaştırmak
- Tek dosyayla, kurulum gerektirmeden çalışmak

## Özellikler
- ⚡ **Tek tıkta yükleme**: Mapping dosyasını seçince otomatik parse edilir.
- 🔎 **Akıllı arama**: Sınıf, metod, alan, parent ve dönüş tipine göre filtreleme.
- 🧠 **Skor bazlı sonuç sıralama**: En alakalı eşleşmeler üstte görünür.
- 🏷️ **Tür filtreleri**: Tümü / Sınıf / Metod / Alan.
- 🧩 **Class expand/collapse**: Sınıf satırlarını aç-kapat.
- 📋 **Kopyalama butonları**: Obf/deobf değerlerini hızlıca panoya al.
- 🌗 **Tema desteği**: Açık/Koyu mod.
- 🌍 **Dil desteği**: Türkçe / English.
- 📤 **CSV export**: Görünen sonuçları dışa aktar.
- 🚀 **Performans odaklı render**: Büyük dosyalarda satır limiti ve optimize listeleme.

## Neden Bu Araç?
Minecraft mapping dosyaları büyük ve karmaşık olabilir. Bu araç:
- düz metni okunabilir hale getirir,
- doğru class/method/field bulma süresini kısaltır,
- hızlı reverse-analysis iş akışına yardımcı olur.

## Kullanım
1. `mc_wiewer.html` dosyasını tarayıcıda aç.
2. Mapping `.txt` dosyanı seç.
3. Arama kutusuna sınıf/metod/alan yaz veya hazır chip’leri kullan.
4. İhtiyacın olursa filtre düğmeleriyle sonuç tipini daralt.
5. Satıra tıklayarak detay panelini aç.
6. Gerekirse CSV olarak dışa aktar.

## Desteklenen Mapping Yapısı (Örnek)
```txt
net.minecraft.client.Minecraft -> abc:
    int someField -> a
    1:10:void runTick() -> b
```

- `Class -> obf:` satırları sınıf olarak parse edilir.
- İçerideki satırlar metod veya alan olarak işlenir.
- Meta satırlar (ör. `# {"fileName": "..."}`) varsa kaynak dosya bilgisi yakalanır.

## Teknik Notlar
- Teknoloji: **HTML + Vanilla JS + Tailwind (CDN)**
- Build step yok, framework kurulumu yok.
- Tek dosyalık mimari sayesinde kolay paylaşım.

## GitHub İçin Önerilen Depo Yapısı
```text
.
├─ index.html        # GitHub Pages ana giriş dosyası
├─ mc_wiewer.html    # Orijinal dosya (opsiyonel, kaynak kopya)
├─ README.md
└─ LICENSE (opsiyonel)
```

## GitHub Pages (github.io) Yayınlama
Bu proje artık doğrudan yayınlanmaya hazırdır çünkü `index.html` dosyası oluşturuldu.

1. Bu dosyaları GitHub reposuna push et:
   - `index.html`
   - `mc_wiewer.html`
   - `README.md`
2. GitHub'da repo içine gir → **Settings** → **Pages**.
3. **Build and deployment** bölümünde:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` (veya kullandığın branch)
   - **Folder**: `/ (root)`
4. **Save** de.
5. 1-3 dakika içinde site şu formatta açılır:
   - `https://kullanici-adin.github.io/repo-adi/`

Not: Eğer özel domain kullanmayacaksan ekstra ayar gerekmez.

## Yol Haritası (Roadmap)
- [ ] Drag & drop dosya yükleme
- [ ] Regex modu
- [ ] Sıralama (sort) kontrolleri
- [ ] Çoklu dosya karşılaştırma
- [ ] Daha gelişmiş export formatları (JSON/TSV)

## Katkı
Katkı yapmak istersen issue veya pull request açabilirsin. Kod sade tutulduğu için geliştirmesi kolaydır.

## Geliştirici
**0b42** / **ebukeh**

---

## 🇬🇧 English

## About the Project
`mc_wiewer.html` is a single-file web tool built to read ProGuard-style mapping files (`.txt`) and display them in a clean, interactive table.

Main goals:
- Make mapping analysis faster
- Simplify class/method/field search
- Run instantly with zero installation

## Features
- ⚡ **One-click load**: Select a mapping file and it parses automatically.
- 🔎 **Smart search**: Filter by class, method, field, parent, and detail/return type.
- 🧠 **Score-based ranking**: Most relevant matches are prioritized.
- 🏷️ **Type filters**: All / Class / Method / Field.
- 🧩 **Class expand/collapse** for better navigation.
- 📋 **Copy buttons** for obf/deobf values.
- 🌗 **Theme support**: Light/Dark mode.
- 🌍 **Language support**: Turkish / English.
- 📤 **CSV export** of current filtered data.
- 🚀 **Performance-oriented rendering** for large mapping files.

## Why This Tool?
Minecraft mapping files can be huge and hard to scan in raw text form. This viewer helps you:
- turn plain text into structured data,
- find the exact class/method/field quickly,
- speed up reverse-analysis workflows.

## Usage
1. Open `mc_wiewer.html` in your browser.
2. Select your mapping `.txt` file.
3. Use search input or quick chips.
4. Narrow results with filter buttons.
5. Click a row to open details.
6. Export filtered output to CSV when needed.

## Supported Mapping Shape (Example)
```txt
net.minecraft.client.Minecraft -> abc:
    int someField -> a
    1:10:void runTick() -> b
```

- `Class -> obf:` lines are parsed as class entries.
- Indented lines are parsed as methods/fields.
- Metadata lines (e.g. `# {"fileName": "..."}`) are used as source hints when available.

## Technical Notes
- Stack: **HTML + Vanilla JS + Tailwind (CDN)**
- No build step, no dependency installation.
- Easy to distribute and host as a static file.

## Recommended GitHub Repository Structure
```text
.
├─ index.html        # GitHub Pages entry file
├─ mc_wiewer.html    # Original source file (optional)
├─ README.md
└─ LICENSE (optional)
```

## Deploy on GitHub Pages (github.io)
This project is now ready for direct publishing because `index.html` is created.

1. Push these files to your GitHub repository:
   - `index.html`
   - `mc_wiewer.html`
   - `README.md`
2. Open your repository on GitHub → **Settings** → **Pages**.
3. Under **Build and deployment**:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` (or your active branch)
   - **Folder**: `/ (root)`
4. Click **Save**.
5. In 1-3 minutes, your site will be available at:
   - `https://your-username.github.io/your-repo/`

Note: No extra configuration is required unless you want a custom domain.

## Roadmap
- [ ] Drag & drop upload
- [ ] Regex search mode
- [ ] Sorting controls
- [ ] Multi-file comparison
- [ ] Advanced export formats (JSON/TSV)

## Contributing
Feel free to open an issue or submit a pull request. The codebase is intentionally straightforward for easy iteration.

## Author
**0b42** / **ebukeh**

---

## License
No license file is included by default. Add a `LICENSE` file (MIT/Apache-2.0/etc.) if you want explicit reuse permissions.
