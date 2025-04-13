Hızlıca dart'ı çalıştırmak için [dartpad'i](https://dartpad.dev/) kullanabilirsiniz.
## Dart Dilinin Temelleri

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
