# Deployment Checklist ☑️

## Před deployem

### .htaccess
- [ ] Aktivovat SSL certifikát a vynutit přesměrování na HTTPS
- [ ] Vynutit přesměrování na "www"
- [ ] Ověřit GZip kompresi a Cache-Control

### Kód a assety
- [ ] Odstranit nepoužité funkce a balíčky
- [ ] Nastavit meta tagy (meta description, atd.)
- [ ] Nastavit Open Graph obrázek
- [ ] Označit klíčové elementy dle WAI ARIA
- [ ] Ověřit 404 chybovou stránku
- [ ] Ověřit HTML minifikaci
- [ ] Ověřit lazy loading obrázků a iframů
- [ ] Ověřit, že mají obrázky definované rozměry (kvůli Cumulative Layout Shift)
- [ ] Ověřit, že se nepoužívají animace delší než 500 ms
- [ ] Ověřit lokální načítání Google fontů
- [ ] Konvertovat JPG/PNG obrázky do WebP
- [ ] Optimalizovat jednotlivé obrázky v Squoosh a SVGOMG (dávkové v TinyPNG)
- [ ] Zkontrolovat zobrazení v alternativných prohlížečích

### WordPress
- [ ] Změnit heslo administrátora
- [ ] Nastavit SMTP, Contact Form 7 a otestovat formuláře
- [ ] Zkontrolovat aktivní WP Mail Logging
- [ ] Nastavit Akismet pokud je použit Contact Form 7
- [ ] Znemožnit přístup k readme.html a licence.txt
- [ ] Znemožnit přístup k archívu autorů přes Yoast SEO
- [ ] Ověřit, že není přístupný Users REST API endpoint /wp-json/wp/v2/users
- [ ] Odstranit archívy a další položky ze sitemap.xml přes Yoast SEO, pokud nemají být dostupné
- [ ] Ověřit rozměry obrázků, které jsou zobrazovány WordPressem
- [ ] Zkontrolovat, jestli nejsou publikované vzorové příspěvky
- [ ] Zkontrolovat redirecty CPT archivů

### Analytika a SEO
- [ ] Přidat Google Analytics skript
	- [ ] Nastavit shromažďování dat (Služba –> Shromažďování dat)
 	- [ ] Změnit délku uchovávání dat (Služba –> Uchovávání dat)
	- [ ] _(Volitelné)_ Aktivovat vyhledávání na stránce (přidat parametr "s")

## Po deployi

### WordPress
- [ ] Nastavit unikátní keys a salts ve wp-config.php
- [ ] Nastavit správná CHMOD práva pro adresáře (např. uploads)
- [ ] Odstranit neaktivní pluginy
- [ ] Aktivovat a nastavit WP Super Cache
- [ ] _(Volitelné)_ Přidat web/aplikaci do správy WP Umbrella, nastavit automatické aktualizace a report

### Analytika, bezpečnost a SEO
- [ ] Ověřit, že .env není přístupný z prohlížeče
- [ ] Aktivovat Security Headers a ověřit je (https://securityheaders.com)
- [ ] Ověřit validitu HTML přes W3C validátor
- [ ] Ověřit Open Graph meta tagy Facebook debuggerem (https://developers.facebook.com/tools/debug/)
- [ ] Přidat web/aplikaci do Google Search Console
	- [ ] Přidat sitemap.xml
	- [ ] Propojit Google Analytics a Search Console profily (v Google Analytics)

### Vyhledáváče
- [ ] Podstrčit web/aplikaci Seznam.cz (http://search.seznam.cz/pridej-stranku)

### Ostatní
- [ ] Přidat stránky Zpracování osobních údajů a Zpracování cookies
- [ ] Přidat Cookie Consent
	- [ ] Povolit CORS pro zapisování logů do databáze
- [ ] Otestovat cookies (https://2gdpr.com, https://www.cookiemetrix.com)
- [ ] Přidat soubor `.well-known/security.txt`
- [ ] _(Volitelné)_ Přidat stránku Veřejných obchodních podmínek
- [ ] _(Volitelné)_ Přesměrovat stará URL na nová přes 301
- [ ] _(Volitelné)_ Přidat web/aplikaci do Uptime Kuma
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
