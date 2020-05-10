# Deployment Checklist ☑️

> Základní checklist používaný nejen při WordPress deploymentu

## Před deployem

### .htaccess
- [ ] Vynutit přesměrování webu/aplikace na "www"
- [ ] Aktivovat GZip kompresi a Cache-Control
- [ ] Aktivovat SSL certifikát a vynutit přesměrování na HTTPS
	- [ ] Ověřit, že každý asset a URL používá HTTPS

### Kód a assety
- [ ] Nastavit meta tagy (meta description, atd.)
	- [ ] Nastavit Open Graph meta tagy
- [ ] Označit klíčové elementy dle WAI ARIA
- [ ] Ověřit 404 chybovou stránku
- [ ] Ověřit, že zkompilované CSS neobsahuje nechtěné `@import`
- [ ] Aktivovat HTML minifikaci
- [ ] _(Volitelné)_ Přidat lazyloading obrázků a/nebo iframů
- [ ] _(Volitelné)_ Nastavit prioritizaci JavaScriptu
- [ ] Optimalizovat obrázky v Optimage, TinyPNG, SVGOMG (eventuálně ImageOptim, ImageAlpha, Squoosh)
- [ ] Zkontrolovat web/aplikaci v IE 11+ a alternativných prohlížečích

### WordPress
- [ ] Změnit heslo administrátora
- [ ] Znemožnit přístup k readme.html a licence.txt
- [ ] _(Volitelné)_ Znemožnit přístup k archívu autorů
- [ ] Ověřit rozměry obrázků, které jsou zobrazovány

### Analytika a SEO
- [ ] Přidat Google Analytics skript
	- [ ] Aktivovat report Demografie
	- [ ] Změnit délku uchovávání dat (Služba –> Údaje o měření –> Uchovávání dat)
	- [ ] _(Volitelné)_ Nastavit setSiteSpeedSampleRate for increase of speed sample rate (https://goo.gl/FRHiAp) 
	- [ ] _(Volitelné)_ Nastavit event tracking (https://goo.gl/1xAgzO) 
	- [ ] _(Volitelné)_ Nastavit konverzní cíle
	- [ ] _(Volitelné)_ Omezit referral spam (http://mareklecian.cz/spamfilter/)
	- [ ] _(Volitelné)_ Aktivovat vyhledávání na stránce (přidání „s“)
	- [ ] _(Volitelné)_ Aktivovat on-site analytics (https://support.google.com/analytics/answer/2558867/?hl=cs)

## Po deployi

### WordPress
- [ ] Nastavit unikátní keys a salts ve wp-config.php
- [ ] Nastavit FTP přístupy ve wp-config.php
- [ ] Nastavit správná CHMOD práva pro adresáře (např. uploads)
- [ ] Aktivovat a nastavit WP Super Cache
- [ ] Nastavit Akismet pokud je použit Contact Form 7
- [ ] Otestovat formuláře
- [ ] _(Volitelné)_ Přidat web do ManageWP

### Analytika, bezpečnost a SEO
- [ ] Ověřit, že .env není přístupný z prohlížeče
- [ ] Aktivovat Security Headers
- [ ] Ověřit validitu HTML přes W3C validátor
- [ ] Ověřit, že meta robots není nastaven na produkci nastaven na noindex,nofollow
- [ ] Ověřit Open Graph meta tagy Facebook debuggerem (https://developers.facebook.com/tools/debug/)
- [ ] Přidat web/aplikaci do Google Search Console
	- [ ] Přidat sitemap.xml
	- [ ] Propojit Google Analytics a Search Console profily (v Google Analytics)

### Vyhledáváče
- [ ] Podstrčit web Seznam.cz (http://search.seznam.cz/pridej-stranku)

### Ostatní
- [ ] Přidat stránky o zpracování osobních údajů a cookies
- [ ] _(Volitelné)_ Přesměrovat stará URL na nová přes 301
- [ ] _(Volitelné)_ Přidat `.well-known/security.txt`
- [ ] _(Volitelné)_ Registrovat do Statusdroid monitoringu
- [ ] Ověřit Security Headers (https://securityheaders.com)
- [ ] Otestovat výkon v Google PageSpeed Insights (https://developers.google.com/speed/pagespeed/insights/
- [ ] Otestovat výkon v WebPagetest (http://www.webpagetest.org)
	- _Speed Index nejlépe okolo 1000 pts. (na LTE), průměr 5000–10000, na "3G Slow" je ok okolo 4 sek._
- [ ] Otestovat výkon v Lighthouse (https://web.dev/measure)
	- _First Meaningful Paint nejlépe do 3 sek._
	- _First Interactive nejlépe nízké jednotky sek._
	- _Perceptual Speed Index nejlépe do 2000, max. do 5 000_
	- _Time To First Byte nejlépe do 500 ms_
