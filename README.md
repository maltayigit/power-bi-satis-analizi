# TeknoSepet — Power BI Satış Analizi Panosu

Kurgusal **TeknoSepet** perakende şirketinin 2024–2025 satış verileriyle hazırlanmış Power BI raporu. Rapor; genel satış özeti, satış temsilcisi performansı, kampanya etkisi ve ödeme tipi analizi sayfalarından oluşur. Klasördeki üç dosya, raporun adım adım nasıl geliştiğini gösterir.

> Tüm kişi, kurum ve rakamlar kurgusaldır.

## Rapor sayfaları

| Sayfa | İçerik | Kullanılan görseller |
|---|---|---|
| Satış Özeti | Zaman içinde satılan adet, iade filtresi | Kart, çizgi + sütun birleşik grafik, çizgi grafik, dilimleyici |
| Satış Temsilcisi Performansı | Temsilci bazında satış adetleri | Kart, çizgi grafik, ödeme tipi dilimleyicisi |
| Kampanya Analizi | Kampanya kodlarına göre satış | Kart, kümelenmiş sütun grafik, dilimleyici |
| Ödeme Analizi | Ödeme tiplerinin payı | Kart, sütun grafik, halka grafik, dilimleyici |
| Tablo / Matris / Grafik *(3. sürüm)* | Mağaza, kanal ve temsilci kırılımları | Tablo, matris, kümelenmiş sütun, çizgi grafik |

## Dosyalar

```
raporlar/
  01_Satis_Panosu_Ilk_Surum.pbix              → temel sayfalar ve ilk görseller
  02_Satis_Panosu_Gelistirilmis.pbix          → düzenlenmiş sürüm
  03_Satis_Panosu_Tablo_Matris_Grafik.pbix    → tablo, matris ve ek grafik sayfaları (en güncel)
veri/
  TeknoSepet_Satis_Verisi.xlsx                → olgu + boyut tabloları, hedefler, veri sözlüğü
  aylik_csv/Satis_2024_01.csv … Satis_2025_12.csv  → 24 aylık satış dosyası (; ayraçlı, UTF-8)
```

## Veri modeli

Yıldız şema:

- **F_Satis** (olgu): SatisID, SiparisNo, Tarih, MusteriID, UrunID, MagazaID, KanalID, Adet, BirimFiyat, IndirimOrani, BirimMaliyet, IadeMi, SatisTemsilcisi, OdemeTipi, KampanyaKodu
- **D_Urun**, **D_Musteri**, **D_Magaza**, **D_Kanal** (boyutlar)
- **Hedefler_Genis**: mağaza × ay satış hedefleri
- **Veri_Sozlugu**: tüm alanların açıklamaları

## Nasıl açılır?

1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) kurun.
2. `raporlar/` altındaki `.pbix` dosyalarından birini açın. En kapsamlı sürüm `03_…` dosyasıdır.
3. Veri kaynağı uyarısı alırsanız **Veriyi dönüştür → Veri kaynağı ayarları** menüsünden kaynağı `veri/` klasöründeki dosyalara yönlendirin.

## Kullanılan beceriler

Power BI Desktop · Power Query · veri modelleme (yıldız şema) · rapor tasarımı · dilimleyicilerle etkileşimli filtreleme
