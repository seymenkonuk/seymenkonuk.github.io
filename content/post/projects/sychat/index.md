---
title: "SYChat: WhatsApp için Ekstra Şifreleme"
description: "Bu Chrome eklentisi, WhatsApp Web mesajlarını AES algoritması ile yeniden şifreleyerek, verilerinizin gizliliğini artırmak amacıyla geliştirilmiştir."
slug: sychat
date: 2025-03-10 00:00:00+0300
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
    - privacy
    - open-source
---

Proje kaynak kodlarına [GitHub üzerindeki bu repo](https://github.com/seymenkonuk/SYChat) aracılığıyla ulaşabilirsiniz.

## Açıklama
Bu Chrome eklentisi, WhatsApp Web'teki mesajlar için ek bir güvenlik katmanı sağlar. WhatsApp Web'in yerleşik şifreleme özelliklerine ek olarak, mesajlarınızı AES (Advanced Encryption Standard) algoritması ile ekstra bir şifrelemeye tabi tutarak gizliliğinizi daha da artırır.

Sunduğu özellikler:
- Mesajları şifreleme / çözme
- Dosyaları şifreleme / çözme
- Sohbetin ortak anahtarını manuel belirleme
- Ortak anahtar belirlemek için Diffie-Hellman kullanma
- Anahtarları dosya olarak dışarı aktarma ve dosyayı içeri aktarma

### Tanıtım

{{< youtube M6rjjuHJ8M8 >}}

## Başlangıç
### Bağımlılıklar
Proje aşağıdaki tarayıcılarda test edilmiştir:
- **Google Chrome**
- **Microsoft Edge**
- **Brave**

### Kurulum
1. Bu repository'yi kendi bilgisayarınıza klonlayın:
```bash
git clone https://github.com/seymenkonuk/SYChat.git
```

2. Projeye gidin:
```bash
cd SYChat
```

3. Gerekli yapılandırmaları yaptıktan sonra eklentiyi tarayıcınıza kurunuz.
	- Chrome için kurulum aşamaları:
		1. `chrome://extensions/` adresine gidiniz.
		2. **Geliştirici Modu** aktif ediniz.
		3. `build/` klasörünü tarayıcıya sürükleyiniz.

### Yapılandırma
1. Sohbetlerinizde kullanılan anahtarlar, tarayıcının depolamasında şifreli bir şekilde saklanır. Eklenti ayarlarından bu dosyayı dışarı aktarabilir veya içeri aktarabilirsiniz.  Şifreleme anahtarı `build/src/config.min.js` dosyasındaki key bilgisidir. Güvenliğiniz için bu değeri değiştirmelisiniz.
```js
export const key="yeni-key-bilgisi";
```
2. Eklentinin ismini değiştirmek isterseniz:
	- `build/manifest.json` dosyasında **name**'i değiştiriniz.
	- `build/src/config.min.js` dosyasında app_name'i değiştiriniz.
```js
export const app_name="yeni-app-ismi";
```

### Kullanım
- Manuel Anahtar Belirleme
	1. Bir anahtar belirleyin ya da rastgele oluşturun.
	2. Eklentinin pop-up menüsünden anahtarı giriniz.
	3. **Anahtarı karşı tarafa güvenli bir şekilde iletiniz.** (Ör: PGP ile)
	4. Karşı taraf da eklentinin pop-up menüsünden anahtarı girmelidir.

{{< youtube 9I8T6yY_dyc >}}

- Diffie-Hellman ile Ortak Anahtar Belirleme
	1. Karşı tarafa public anahtarınızı gönderiniz.
	2. Karşı tarafın kendi public anahtarını göndermesini bekleyiniz.
	3. İki tarafta kendi public anahtarını gönderdiğinde; **Diffie-Hellman** algoritması ile **güvenli** bir şekilde otomatik olarak ortak anahtar oluşturulur. 

{{< youtube QXbTGolbAIA >}}

- Şifreli Mesaj Gönderme
	1. Anahtarı belirleyiniz.
	2. Mesajı yazınız ve **CTRL+ENTER** ile gönderiniz.

{{< youtube FoVyzF53sBg >}}

- Şifreli Dosya Gönderme
	1. Anahtarı belirleyiniz.
	2. Dosyayı sol taraftaki **mavi** dosya yükleme alanına sürükleyiniz.

{{< youtube JZq3YjE6Apo >}}

- Şifreli Dosyayı Çözme
	1. Anahtarı belirleyiniz.
	2. Şifreli dosyayı indiriniz.
	3. Şifreli dosyayı sol taraftaki **mavi** dosya yükleme alanına sürükleyiniz.
	4. Çözülmüş dosya bilgisayarınıza indirilecektir.
	
{{< youtube gb_IqCu1K_c >}}
