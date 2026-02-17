- 

```md
# Minecraft Mapping Explorer (MC Mapping Viewer) — Ultra Fast ⚡

Minecraft mapping (`.txt`) dosyalarını tarayıcı içinde **aşırı hızlı**, modern ve akıcı şekilde görüntülemek, aramak, filtrelemek ve CSV olarak dışa aktarmak için hazırlanmış **tek dosyalık (single-file) HTML tool**.

---

## ✨ Features

- ⚡ Dosyayı seç → anında hazır görünüm
- 🔎 Akıllı arama sistemi (class / method / field + skor bazlı)
- 🧩 Class collapse / expand sistemi
- 📋 Tek tıkla kopyalama (deobf / obf)
- 🌗 Light / Dark tema
- 🌍 TR / EN dil desteği
- 📤 Filtrelenmiş veriyi CSV export
- 🧠 `# {"fileName":"..."}` metadata desteği
- 🚀 Büyük mapping dosyalarında performans optimizasyonu

---

# 🇹🇷 Türkçe

## 📦 Kurulum

### 1) Çalıştırma
Backend gerekmez.

1. Repo’yu indir / clone’la
2. `index.html` dosyasını tarayıcıda aç
3. Mapping `.txt` dosyanı seç
4. Arama / filtre / export özelliklerini kullan

---

### 2) GitHub Pages ile Yayınlama

1. GitHub Repo → **Settings**
2. Sol Menü → **Pages**
3. Source → `main` / `(root)`
4. Save → birkaç dakika içinde link oluşur

---

## 🎮 Kullanım

### Dosya Seçimi
Mapping `.txt` dosyasını seçince:

- Arama temizlenir
- Filtre "Tümü" olur
- İlk class otomatik açılır
- Tablo otomatik render edilir

---

## 🔎 Akıllı Arama

Desteklenen özellikler:

- Class / Method / Field arama
- Türkçe karakter normalize edilir (ı → i, ş → s, ç → c, vb.)
- `/` ve `\` karakterleri `.` gibi davranır
- `fileName` metadata içinden arama yapabilir
- Type alias destekler (class / method / field)

### Örnek Aramalar

```

net.minecraft.client.Minecraft
minecraft
render
gui
field tick
method run
SomeClass.java

```

---

## 🎛 Filtreler

- **Tümü**
- **Sınıf**
- **Metod**
- **Alan**

---

## 📋 Copy Sistemi

Her satırda 📋 butonu ile:

- Obf veya Deobf isimleri kopyalanabilir.

---

## 📤 CSV Export

Export butonu mevcut filtre + arama sonucunu indirir.

CSV formatı:

```

type,deobf,obf,detail,parent

```

---

# 🧾 Mapping Formatı

Bu tool **ProGuard / R8 mapping formatı** destekler.

---

## ✅ Minimal Mapping Örneği

```

net.minecraft.client.Minecraft -> abc:
void run() -> a
int fps -> b

net.minecraft.client.gui.Gui -> def:
void render() -> c
boolean debug -> d

net.minecraft.client.renderer.RenderGlobal -> ghi:
void renderEntities() -> a
void renderSky() -> b
int renderDistanceChunks -> c

```

---

## ✅ Ayrıntılı Mapping Örneği (Metadata Destekli)

Viewer `# {"fileName":"..."}` satırlarını algılar:

```

net.minecraft.client.Minecraft -> abc:

# {"fileName":"Minecraft.java"}

```
12:45:void run() -> a
46:46:int fps -> b
50:60:void startGame() -> c
70:70:boolean running -> d
```

net.minecraft.client.gui.Gui -> def:

# {"fileName":"Gui.java"}

```
void render() -> a
void drawRect(int,int,int,int,int) -> b
boolean debug -> c
```

net.minecraft.client.renderer.RenderGlobal -> ghi:

# {"fileName":"RenderGlobal.java"}

```
void renderEntities() -> a
void renderSky() -> b
int renderDistanceChunks -> c
10:90:void loadRenderers() -> d
91:110:void markBlocksForUpdate(int,int,int,int,int,int) -> e
```

net.minecraft.client.entity.EntityPlayerSP -> jkl:

# {"fileName":"EntityPlayerSP.java"}

```
void onUpdate() -> a
void sendChatMessage(java.lang.String) -> b
float rotationYaw -> c
float rotationPitch -> d
```

net.minecraft.client.multiplayer.WorldClient -> mno:

# {"fileName":"WorldClient.java"}

```
void tick() -> a
void updateEntities() -> b
int difficultySetting -> c
```

````

📌 Not:
- Metadata satırı class satırından sonra gelmelidir.
- Method/field otomatik parent class’a bağlanır.

---

# ⚙ Performans

Büyük mapping dosyalarında UI donmaması için:

- `MAX_RENDER_ROWS` limiti vardır
- Çok fazla class varsa sınırlama uygulanır
- Çok fazla member varsa class başına limit vardır
- Aramada en iyi eşleşen class’lar otomatik expand edilir

---

# 🛠 Customization

Kod içinden değiştirebilirsin:

```js
const MAX_RENDER_ROWS = 1800;
const AUTO_EXPAND_SEARCH_CLASS_LIMIT = 30;
const SEARCH_MEMBER_LIMIT_PER_CLASS = 220;
````

---

# 🌍 English

## 📦 Installation

No backend required.

1. Download / clone repository
2. Open `index.html` in browser
3. Select a `.txt` mapping file
4. Use search / filter / export

---

## 🔎 Smart Search

Supports:

* Class / Method / Field search
* Turkish character normalization
* `/` and `\` act like `.`
* `fileName` metadata search
* Type alias tokens

### Example Queries

```
net.minecraft.client.Minecraft
minecraft
render
gui
field tick
method run
SomeClass.java
```

---

## 🎛 Filters

* All
* Class
* Method
* Field

---

## 📤 CSV Export

Exports current filtered + searched dataset.

Format:

```
type,deobf,obf,detail,parent
```

---

# 🧾 Supported Mapping Format

ProGuard / R8 mapping format supported.

---

## Minimal Example

```
net.minecraft.client.Minecraft -> abc:
    void run() -> a
    int fps -> b
```

---

## Detailed Example with Metadata

```
net.minecraft.client.Minecraft -> abc:
# {"fileName":"Minecraft.java"}
    12:45:void run() -> a
```

---

# 📜 License

MIT License recommended.

---

# ⭐ Credits

Made with ❤️ using HTML + TailwindCSS.
Ultra Fast Rendering optimized for large mapping files.

```


