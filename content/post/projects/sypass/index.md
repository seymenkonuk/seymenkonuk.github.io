---
title: "SYPass: Parola Yöneticisi"
description: Bu Chrome eklentisi, kullanıcıların parolalarını güvenli bir şekilde yönetmelerini ve formları kolayca doldurabilmelerini sağlar.
slug: sypass
date: 2025-03-11 00:00:00+0000
image: 
categories:
    - projects
    - chromium-extension
tags:
    - html
    - css
    - js
    - chromium-extension
    - encryption
    - open-source
---

Proje kaynak kodlarına [GitHub üzerindeki bu repo](https://github.com/seymenkonuk/SYPass) aracılığıyla ulaşabilirsiniz.

## Açıklama
Kullanıcılar, farklı hesaplar için güçlü ve benzersiz parolalar oluşturabilir, saklayabilir ve hızlıca erişebilir. Eklenti, parolaları şifreli bir şekilde saklar ve sadece doğru anahtar ile erişim sağlar. Kullanıcı dostu bir arayüz sunarak, parolalarınızı kolayca ekleyip düzenlemenize olanak tanır.

Sunduğu özellikler:
- Güçlü parola oluşturucu
- Parolaların şifreli saklanması
- Otomatik form doldurma
- Parolalarınızı aktif sekmenin base-domain'ine göre gruplama
- Parolalarınızı dosya olarak dışarı aktarma ve dosyayı içeri aktarma

### Tanıtım

{{< youtube u3CtZp4M1lY >}}

## Başlangıç
### Bağımlılıklar
Proje aşağıdaki tarayıcılarda test edilmiştir:
- **Google Chrome**
- **Microsoft Edge**
- **Brave**

### Kurulum
1. Bu repository'yi kendi bilgisayarınıza klonlayın:
```bash
git clone https://github.com/seymenkonuk/SYPass.git
```

2. Projeye gidin:
```bash
cd SYPass
```

3. Gerekli yapılandırmaları yaptıktan sonra eklentiyi tarayıcınıza kurunuz.
	- Chrome için kurulum aşamaları:
		1. `chrome://extensions/` adresine gidiniz.
		2. **Geliştirici Modu** aktif ediniz.
		3. `build/` klasörünü tarayıcıya sürükleyiniz.

### Yapılandırma
1. Ayarlarınız, tarayıcının depolamasında şifreli bir şekilde saklanır. Eklenti ayarlarından bu dosyayı dışarı aktarabilir veya içeri aktarabilirsiniz.  Şifreleme anahtarı `build/src/config.min.js` dosyasındaki key bilgisidir. Güvenliğiniz için bu değeri değiştirmelisiniz.
```js
export const key="yeni-key-bilgisi";
```
2. Eklentinin ismini değiştirmek isterseniz:
	- `build/manifest.json` dosyasında **name**'i değiştiriniz.
	- `build/src/config.min.js` dosyasında app_name'i değiştiriniz.
```js
export const app_name="yeni-app-ismi";
```
