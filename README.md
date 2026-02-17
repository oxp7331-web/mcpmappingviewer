# Minecraft Mapping Explorer (MC Mapping Viewer) — Ultra Fast

**Minecraft mapping (.txt) dosyalarını** tarayıcı içinde *çok hızlı* şekilde görüntülemek, aramak, filtrelemek ve CSV olarak dışa aktarmak için tek dosyalık (single-file) bir HTML aracı.

- ⚡ Dosyayı seç → anında hazır görünüm  
- 🔎 Akıllı arama (class/method/field + token bazlı skor)  
- 🧩 Class collapse/expand (en iyi eşleşen class’ları otomatik açar)  
- 📋 Tek tıkla kopyala (deobf / obf)  
- 🌗 Light/Dark tema  
- 🌍 TR/EN dil desteği  
- 📤 Filtrelenmiş görünümü CSV export  
- 🧠 `# "fileName": "..."` metadata desteği (source file gösterimi)

---

## Demo / Live
> GitHub Pages kullanıyorsan buraya link koy:
- `https://<kullanici>.github.io/<repo>/`

---

## Kurulum (TR)

### 1) İndir & Aç
Bu proje **backend gerektirmez**.

1. Repo’yu indir / clone’la  
2. `index.html` dosyasını çift tıklayıp tarayıcıda aç  
3. Mapping dosyanı seç (`.txt`)  
4. Arama / filtre / kopyala / export kullan

### 2) GitHub Pages ile Yayınlama
1. Repo Settings → **Pages**  
2. Source: `main` / `(root)`  
3. Kaydet → link birkaç dakika içinde oluşur

---

## Kullanım (TR)

### Mapping dosyası seçme
Üstteki **Dosya** alanından mapping `.txt` dosyanı seç.  
Seçince:
- Filtre `Tümü` olur
- Arama alanı temizlenir
- İlk class otomatik açılır (hızlı başlangıç)

### Arama (Akıllı)
Arama alanı:
- Class, metod veya alan içinde arar
- TR karakter normalizasyonu yapar (ı/İ → i, ş → s vb.)
- `/` ve `\` yazınca `.` gibi davranır (package araması kolaylaşır)
- Sınıf ismi / tam sınıf yolu / dosya adı (fileName) skorlanır

**Örnek aramalar:**
- `net.minecraft.client.Minecraft`
- `minecraft`
- `render`
- `Gui`
- `class minecraft` (type alias destekli)
- `field tick`
- `SomeClass.java` (java filename odaklı arama)

### Filtreler
- **Tümü**: her şeyi gösterir  
- **Sınıf**: sadece class kayıtları  
- **Metod**: sadece method kayıtları  
- **Alan**: sadece field kayıtları  

### Hızlı chip’ler
`Minecraft / Client / Render / GUI` chip’lerine tıklayınca aramayı otomatik doldurur.

### Detay Paneli
Tablodan bir satıra tıkla:
- Tür, parent sınıf, deobf/obf/detay alanları üst panelde açılır

### CSV Export
**Export CSV** butonu:
- Mevcut filtre + arama sonucunu CSV olarak indirir  
- Başlıklar:
  - `type,deobf,obf,detail,parent`

---

## Mapping Formatı (TR)

Bu viewer, **ProGuard/R8 mapping** formatını destekler.

### Minimal Örnek (`example_mapping.txt`)
```txt
net.minecraft.client.Minecraft -> abc:
    void run() -> a
    int fps -> b

net.minecraft.client.gui.Gui -> def:
    void render() -> c
    boolean debug -> d
