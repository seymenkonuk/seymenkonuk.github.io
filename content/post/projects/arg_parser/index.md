---
title: "Arg Parser"
description: C dilinde, komut satırı argümanlarını daha etkili bir şekilde yönetmek için geliştirilmiş bir kütüphane.
slug: arg-parser
date: 2025-03-08 00:00:00+0300
image: 
categories:
    - projects
    - console-applications
tags:
    - c
    - open-source
---

Proje kaynak kodlarına [GitHub üzerindeki bu repo](https://github.com/seymenkonuk/arg_parser) aracılığıyla ulaşabilirsiniz.

## Açıklama
Sunduğu özellikler:
- **Flag Yönetimi**: Bayrak (flag) parametrelerini işleme ve yönetme.
- **Opsiyonel ve Zorunlu Seçenekler**: Hem opsiyonel hem de zorunlu seçenekleri destekler.
- **Varsayılan Değerler**: Seçenekler için varsayılan değer atama imkanı sağlar.
- **Değer Validasyonu**: Seçeneklere girilen değerlerin doğruluğunu kontrol eder.
- **Yardım Menüsü**: Kullanıcıya komut satırı argümanları hakkında bilgi sunar ve nasıl kullanılacağını gösterir.

Örnek program çıktısı 1:
```bash{linenos=false}
> ./test
option --zorluk: is require.
```

Örnek program çıktısı 2:
```bash{linenos=false}
> ./test --genislik metin -h deneme --zorluk IMKANSIZ
Type Error: option --genislik expects an integer. You provided 'metin'.
Type Error: option --hiz expects an double. You provided 'deneme'.
Type Error: option --zorluk expects an ['KOLAY', 'ORTA', 'ZOR']. You provided 'IMKANSIZ'.
```

Örnek program çıktısı 3:
```bash{linenos=false}
> ./test --help
-?, --help					yardim ekrani
-m, --mod					modu degistirir
-g, --genislik <value>	oyun alaninin genisligini belirler
-y, --yukseklik <value>	oyun alaninin yuksekligini belirler
-h, --hiz <value>			oyunun hizini belirler
-t, --test <value>			test amaclidir
-z, --zorluk <value>		*oyunun zorlugunu belirler (KOLAY, ORTA, ZOR)
```

## Başlangıç
### Bağımlılıklar
Proje aşağıdaki işletim sistemlerinde test edilmiştir:
- **Debian**

Projenin düzgün çalışabilmesi için aşağıdaki yazılımların sisteminizde kurulu olması gerekir:
- **C Derleyicisi** (GCC, Clang vb.)
- **Make** (Makefile kullanarak derlemek için)
- **Docker** (Docker kullanarak çalıştırmak için)

### Kurulum
1. Bu repository'yi kendi bilgisayarınıza klonlayın:
```bash
git clone https://github.com/seymenkonuk/arg_parser.git
```

2. Projeye gidin:
```bash
cd arg_parser
```

### Yapılandırma
Yapılandırılacak bir şey yok!

### Derleme

Kütüphane, **Makefile** üzerinden kolayca derlenebilir ve linklenebilir.

- **Projeyi derlemek için**:

```bash
make
```

- **Projeyi temizlemek için**:

```bash
make clean
```

Makefile, kütüphanenizi derleyecek ve `bin/libarg_parser.a` statik kütüphanesini oluşturacaktır.

### Çalıştırma
Kütüphaneyi kullanan basit bir programı (`test/test.c`) **Docker** üzerinden çalıştırabilirsiniz:
1. Make ve Docker'ı kurunuz.
2. Aşağıdaki komutu çalıştırınız:
```bash
make docker
```

Kütüphaneyi kullanan basit bir programı (`test/test.c`) **Makefile** üzerinden çalıştırabilirsiniz:
1. Make'i kurunuz.
2. Aşağıdaki komutu çalıştırınız:
```bash
make test
```

## Kullanım
Kütüphaneyi kendi C projenizde kullanabilmek için aşağıdaki adımları izleyebilirsiniz:


1. **Kütüphaneyi derleyerek `libarg_parser.a` dosyasını elde edin.**

2. **libarg_parser.a dosyasını `/path/to` dizinine yerleştirin.**

3. **src dizini içindeki bütün .h dosyalarını `/path/to/include/arg_parser` dizinine yerleştirin.**

4. **Kütüphaneyi dahil edin**:

	`#include <arg_parser/arg_parser.h>` satırını, kullanmak istediğiniz C dosyasının başına ekleyin.

5. **Derleme sırasında kütüphaneyi linkleyin**: (Burada `/path/to` dizini herhangi bir dizin olabilir.)

```bash
gcc -o my_program my_program.c -L/path/to -larg_parser -I/path/to/include
```
