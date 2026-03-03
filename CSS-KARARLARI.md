# CSS Kararları

## 1. Breakpoint Seçimi
**Neden 640px ve 1024px seçtim?**
Endüstri standardı olan yaygın mobil, tablet ve masaüstü kırılımlarını yansıttığı için bu değerleri tercih ettim. 
**İçeriğim bu noktalarda nasıl değişiyor?**
640px altında (mobil) her şey alt alta (column) dizilirken, 640px ve sonrasında formlar, navbar ve iletişim kısımları yatay (row) dizilime geçiyor. 1024px sonrasında ise geniş ekranlardan faydalanmak için proje kartları 3'lü bir Grid ızgarasına oturuyor ve ana içerik merkeze hizalanıyor.

## 2. Layout Tercihleri
**Header için neden Flexbox seçtim?**
Header, navigasyon ve yetenek etiketleri (skill-tags) gibi tek boyutlu (yan yana veya alt alta) hizalama gerektiren yapılar için esnekliği nedeniyle Flexbox kullandım.
**Proje kartları için neden Grid seçtim?**
Kartların hem yatayda hem dikeyde (iki boyutlu) düzenli bir ızgara yapısına oturması gerektiği için CSS Grid tercih ettim.
**auto-fit mi auto-fill mi kullandım, neden?**
Ekran genişlediğinde boş sütun kalmaması ve mevcut kartların alanı tamamen kaplaması için `auto-fit` kullandım.

## 3. Design Tokens
**Hangi renk paletini seçtim ve neden?**
Göz yormayan, güven veren ve modern bir görünüm sunan mavi tonlarını (Primary: #1E3A8A) beyaz bir arka plan ve gri metinlerle kombinleyerek yüksek kontrast (erişilebilirlik) sağladım.
**Spacing skalasını nasıl belirledim?**
Tutarsız piksel değerleri yerine, `rem` tabanlı (0.25rem'den 4rem'e kadar) orantılı bir boşluk (spacing) sistemi oluşturdum.
**Fluid typography için clamp değerlerini nasıl ayarladım?**
`clamp()` fonksiyonu ile minimum ve maksimum font boyutlarını `rem` ile belirlerken, ortadaki tercih edilen boyuta `vw` (viewport width) ekleyerek yazıların ekranla birlikte akıcı bir şekilde küçülüp büyümesini sağladım.

## 4. Responsive Stratejiler
**Mobile-first yaklaşımını nasıl uyguladım?**
CSS kodlarımı yazarken önce `max-width` kullanmadan, varsayılan olarak en dar (mobil) ekran için tasarladım. Daha sonra `@media (min-width)` sorgularıyla kodların üzerine ekleme yaparak tablet ve masaüstü düzenlerini kurdum.
**Görsel boyutları nasıl yönettim?**
Tüm resimlerin taşıp ekranı bozmasını engellemek için global olarak `max-width: 100%` ve `height: auto` kullandım. Kartlardaki resimlerin de en-boy oranının bozulmaması için `object-fit: cover` kuralını uyguladım.
