# TRAJECTORY: Son Kıvılcım

Gerçek fizik tabanlı, **görsel doyum** ve **karakter (Nova)** üzerine kurulu, **hikâyeli** ve **sonsuz** (Candy Crush gibi sürekli bölüm eklenen) bir balistik **hassasiyet bulmacası**. Tek dosya (`index.html`), bağımlılık yok (Matter.js CDN’den yüklenir).

## Hikâye — "Son Kıvılcım"

Güneş söndü; geriye sonsuz bir alacakaranlık kaldı. Gökyüzünü bir zamanlar iki ikiz yıldız aydınlatırdı: **Lyra** ve kardeşi **Sönük**. Lyra düşünce Sönük kederinden dondu ve dünyaya, ışığı hapseden **karanlık çekirdekler** ekti. Sen **Nova**’sın — Lyra’nın **son kıvılcımı**. Bekçi **Atlas** asırlık **Yıldız Sapanı**’nı senin için geriyor.

- Her bölüm bir **anı/ipucu** açar; her karanlık çekirdeği kırınca hapsolmuş **ışık serbest kalır**.
- İlerledikçe gökyüzü **alacakaranlıktan şafağa** döner — ama **tam şafak asla gelmez**: Nova ile Sönük her seferinde tam kavuşacakken araya yeni bir karanlık girer. Bu yüzden oyun **bitmez**; 10 elle yazılmış bölümden sonra **sonsuz, prosedürel** bölümlerle devam eder ve araya yeni hikâye parçaları girer.
- Nova **son ışık** olduğu için her boşa atış onu soluklaştırır → **hassasiyet** ödüllendirilir (yıldız = az kıvılcımla çöz; "İLK ATIŞTA!" / "MÜKEMMEL").

## Karakter: NOVA

Her mermi aslında **Nova** — gözleri, kaşları, ağzı olan, esneyip büzülen (squash & stretch), bakış yönünü takip eden, göz kırpan ve tepesinde alev tutuşan bir kıvılcım-yıldız yaratığı. Oyunun tüm görsel dili Nova’nın ifadeleri üzerine kuruludur:

- **Sapanda** geri çekilirken Nova fırlatma yönüne bakar, gerilim arttıkça kararlı/zorlanan bir ifade alır.
- **Uçarken** gözleri büyür, yanakları pembeleşir, ağzı heyecanla açılır; hıza göre esner.
- **Kostümler** (yetenekler) Nova’nın görünüşünü değiştirir: bomba (fitil + kızgın surat), gülle (zırh kaskı), roket (gözlük), üçleme.

## Yeni mekanikler

- **Mermi türleri** (alttaki cephanelikten seç, uçarken **ekrana dokun** → yetenek):
  - **Standart** — dengeli
  - **Bomba** — dokun: patla (AoE savurma + hasar)
  - **Üçleme** — dokun: 3’e bölün, geniş hedefleri süpür
  - **Roket** — dokun: ileri fırla, rüzgarı/savunmayı yen
  - **Gülle** — çok ağır, duvarları ezerek geçer
- **Yeni malzemeler**: Buz (kaygan/kırılgan), Metal (çok sert), TNT (zincirleme patlar).
- **Skor + Kombo çarpanı** (x2…x6), ekranda uçuşan puanlar, ekran sarsıntısı, çekirdek imhasında **ağır çekim**.
- **Mücevher** toplama (uçarken yakala), **coin** ekonomisi, **localStorage kayıt** (yıldız, en iyi skor, kilit açma).
- **Ses efektleri** (Web Audio, prosedürel) — `M` ile sustur.
- **Arena ∞ modu**: dalga bazlı, gittikçe zorlaşan, sonsuz “bir tur daha” modu; en iyi dalga kaydedilir.

## Oynanış

- Sapanı **geri çek ve bırak** (mouse veya dokunmatik).
- Sağ üstteki **ATIŞ ÇÖZÜMÜ** panelinden açı°, güç%, rüzgar, tahmini menzil ve zirve yüksekliğini oku.
- **Noktalı yörünge** seçili mermiyle birebir aynı simülasyonu kullanır.
- Tüm **çekirdekleri** (kırmızı kristal) imha et. Yıldız: kullandığın mühimmata göre (par’ı tuttur = 3 yıldız).

Kısayollar: `R` yeniden başlat · `Esc` menü · `M` ses · `Boşluk` uçarken yetenek.

## GitHub Pages’e yükleme

1. Repo köküne `index.html` koy → **Settings → Pages** → **Deploy from a branch** → **main / (root)**.
2. 1–2 dakika sonra `https://KULLANICI.github.io/REPO/` adresinde yayında.

> Tek dosya yeterli; `index.html` repo kökünde olmalı.

## Özelleştirme

`index.html` içindeki `LEVELS` dizisini düzenle. Blok: `blk(cx, cy, w, h, 'wood'|'glass'|'ice'|'stone'|'metal'|'tnt')`. Çekirdek: `{cx, cy, w, h}`. Bölüm alanları: `wind` (sağ +/sol −), `arsenal` (örn. `{orb:2, bomb:1}`), `par` (yıldız hedefi), `gems` (toplanabilir mücevherler). Mermi türleri `PROJ_TYPES`, malzemeler `MAT` içinde tanımlı. Zemin üst yüzeyi `GROUND_Y` (636).
