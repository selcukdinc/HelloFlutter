Hızlıca dart'ı çalıştırmak için [dartpad'i](https://dartpad.dev/) kullanabilirsiniz.

Daha detaylı bilgi ve pratik için udemy [kursunu](https://www.udemy.com/course/flutter-bootcamp-program-dart/) inceleyebilirsiniz.

## Dart Dilinin Temelleri

### Null Safety

Veri tipinin yanına soru işareti koyularak değişken null'anabilir.

```dart
  //tanımlama
  String? mesaj = null;
```

Yöntem-1 __*?*__ : null olabilen bir değişken kullanılmak istendiğinde, eğer değişken null uygulamanın çökmesini önler.

```dart
  print("Yöntem 1 : ${mesaj?.toUpperCase()}");
```

Yöntem-2 __*!*__ : Yazılım geliştirici insiyatif alarak null kontrolünü atlar.

```dart
print("Yöntem 2 : ${mesaj!.toUpperCase()}");
```
Yöntem-3 : If ile null kontrolü ve null olma durumunda işlem yapabilme

```dart
if(mesaj != null){
    print("Yöntem 3 : ${mesaj.toUpperCase()}");
  }else{
    print("Mesaj null'dur");
  }
```
--- 

### Değişkenler
Dart, geçmiş dönemin dillerin ilkelliğini güncel dillerin yaklaşımlarıyla birlikte harmanlanmış dildir.

#### İlkel (Primative) Yaklaşım
```dart
int degisken0 = 25;
String degisken1 = "Selçuk";
// Aynı zamanda karaketer tanımlaması da String ile yapılabilir.
String degiskeninBasHarfi0 = degisken1[0]; // "S"
String degiskeninBasHarfi0 = "S";
double degisken2 = 53.7;
```
Bu dilde de her string ifadenin birer karakter listesi gibi davranmaya devam etmesi bulunmaktadır. (bkz: `degisken1[0]`). Fakat C gibi dilden ayrılan özelliklerinden biri 'char' gibi bir türün bulunmamasıdır.

#### Güncel Yaklaşım
Bu yaklaşımda tür belirtmeyiz, programın kendisinin anlamasını bekleriz, anlarda.
```dart
var degisken0 = 25;
var degisken1 = "Selçuk";
var degiskeninBasHarfi = degisken1[0]; // "S"
var degisken2 = 53.7;
```

*En iyi yaklaşım*, her tanımlama yaklaşımının en faydalı olacağı alanlarda kullanmaktır.

### Sabitler
Sabitler final veya const olarak tanımlanır.
Dillerin kendi sabitleri Java(final), Swift(let), Kotlin(val) şeklindendir.


Const ve finali isterseniz her yerde kullanabilirsiniz fakat en iyi yaklaşım kullanacağınız yere göre değişmektedir.

#### Sabit türü : final 
Kodlamayı çalıştırdığımızda hafızada oluşur.
*Genellikle değişken düzeyindeki sabitler için kullanılır*
```dart
final int sabit1 = 22; 
```


#### Sabit türü : const
Değişken tanımlandığında hafızada oluşur
*Genellikle ui elementleri düzeyindeki sabitler için kullanılır*
```dart
const int sabit2 = 44; 
```

---

### Kontrol Koşulları (If-Else / Switch-case)
#### If-else semantiği
```dart
if(koşul-1){
    // eğer koşul doğru ise
} else if(koşul-2){
    // eğer koşul-1 doğru değil, koşul-2 doğru ise
} else {
    // koşul-1 ve koşul-2 doğru değilse
}
```


### Koleksiyon Tipleri
Veriyi depolarız, kullanırız. Her verinin turşusunu kurmasakta kolleksiyonluk yapabiliriz. Kullanım senaryolarına göre farklı tipte kolleksiyonlar vardır.

#### 'List'ler

Hemen hemen bir çok alanda kullanılabilecek yapılardır.

| İndeks | Değerler |
|:--:|:--:|
| 0 | 6 Yumurta |
| 1 | Süt |
| 2 | Un |
| 3 | Kabartma Tozu |

#### 'HashSet'ler

HashSet'lerde bir gruplama olmasına rağmen listeye hangi zamanda eklendiği bilinmemektedir. Kullanım alanlarına bir örnek verecek olursak şıklı bir soru yapıyorsanız aynı soruyu her çağırdığınızda şıkların sürekli yer değiştirdiğini görebiliriz. 

#### 'HashMap'ler

HashMaplar ise indeks'leri doğal sayılar yerine anahtarlardan oluşan listelere benzerler. Bu benzerliği ilkokuldan beri *sözlükler* ile biliyoruz aslında. Bir anahtar kelime ve o anahtar kelimeye karşılık gelen anlam. Anahtar 'kelime' olabileceği gibi yazılımda 'hashable' sınıflarda 


## Olaylar 

#### Olay : 'Switch-case' ile Enum'u bir arada kullanmak
- `konserve_boyut` adında yeni dosya oluştur
- aşağıdaki gibi enumu belirt
   - ```dart
        enum KonserveBoyut {
            kucuk,orta,buyuk
        }
- Switch-Case kullanılacak yere gel
  - ```dart
        void ucretHesala(KonserveBoyut boyut, int adet){
            int maliyet = 1;
            switch(boyut){
              case KonserveBoyut.kucuk :  { maliyet = adet * 20; } break;
              case KonserveBoyut.orta :   { maliyet = adet * 40; } break;
              case KonserveBoyut.buyuk :  { maliyet = adet * 60; } break;
            }
            print("toplam maliyet : $maliyet");
        }
  - Örnek bir kullanım yukarıda verilmiştir.
  - Kullanıdığın enum farklı bir dosyada olduğu için <br> `import 'package:flutter_entry/nesne_tabanli_programlama/konserve_boyut.dart';` <br> senin durumuna uyan bir import eklenmiş olması gerekiyor.
