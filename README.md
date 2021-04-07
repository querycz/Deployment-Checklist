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
- [ ] Přidat lazy loading obrázků a/nebo iframů
- [ ] Ověřit, že obrázky mají definované rozměry kvůli Cumulative Layout Shift
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
	- [ ] _(Volitelné)_ Aktivovat vyhledávání na stránce (přidání „s“)

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
- [ ] Přidat stránky Zpracování osobních údajů a Zpracování cookies
- [ ] _(Volitelné)_ Přidat stránku Veřejných obchodních podmínek
- [ ] _(Volitelné)_ Přesměrovat stará URL na nová přes 301
- [ ] _(Volitelné)_ Přidat `.well-known/security.txt`
- [ ] _(Volitelné)_ Registrovat do Server Monitoru
- [ ] Ověřit Security Headers (https://securityheaders.com)
- [ ] Otestovat výkon v WebPagetest (http://www.webpagetest.org)
	- _Speed Index nejlépe okolo 1000 pts. (na LTE), průměr 5000–10000, na "3G Slow" je ok okolo 4 sek._
- [ ] Otestovat výkon v Google PageSpeed Insights (https://developers.google.com/speed/pagespeed/insights/)
	- Syntetická měření
		- _LPS_ – Lighthouse Performance Score
		- _FCP_ - First Contentful Paint (ideálně do 2,36 s)
		- _LCP_ – Largest Contentful Paint (ideálně do 2,5 s)
		- _SI_ – Speed Index (ideálně do 3,37 s)
		- _TTI_ – Time to Interactive (ideálně do 3,785 s)
		- _TBT_ – Total Blocking Time (ideálně do 0,287 s)
		- _CLS_ – Cumulative Layout Shift (ideálně do 0,1)
	- Core Web Vitals (uživatelská měření)
		- _LCP_ – Largest Contentful Paint (ideálně do 2,5 s)
		- _FID_ – First Input Delay (ideálně do 100 ms)
		- _CLS_ – Cumulative Layout Shifr (ideálně do 0,1)
- [ ] Otestovat Cumulative Layout Shift (https://defaced.dev/tools/layout-shift-gif-generator/)
