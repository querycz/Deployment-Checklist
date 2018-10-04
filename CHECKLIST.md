# Deployment Checklist

## .htaccess
- [ ] **Ošetři web/aplikaci pro doménu bez www** (viz KB)
- [ ] **Nastav GZip kompresi a kešování** (viz KB)
- [ ] **Aktivuj SSL certifikát a přesměrovat na HTTPS protokol** (viz KB)
	- [ ] Ověř, že všechny URL adresy a assety používají HTTPS protokol

## Kód a assets
- [ ] **Doplň meta tagy (meta description, atd.)**
	- [ ] **Nastav Open Graph meta tagy**
	- [ ] **Zkontroluj Open Graph meta tagy Facebook debuggerem** (https://developers.facebook.com/tools/debug/)
- [ ] **Označ klíčové elementy dle standardu WAI ARIA** (viz KB)
~~- [ ] Vlož souhlas s ukládáním cookies~~
- [ ] **Ověř, zda-li je nastavena chybová stránka 404**
- [ ] Zvaž načítání alternativních fontů přes Web Font Loader (https://github.com/typekit/webfontloader)
- [ ] **Zkontroluj, jestli zkompilovaný CSS neobsahuje nechtěné `@import`**
- [ ] **Nastav minifikace HTML kódu**
- [ ] **Zkontroluj validitu HTML kódu W3C validátorem**
- [ ] Zvaž prioritizaci načítání JavaScript skriptů (viz KB)
- [ ] **Optimalizuj obrázky v ImageOptim, ImageAlpha, TinyPNG a SVGOMG**
- [ ] **Zkontroluj zobrazení v IE 11+ a dalších prohlížečích** (https://www.browserling.com/internet-explorer-testing)

## WordPress před deployem
- [ ] **Změň heslo administrátora**
- [ ] **Odstraň a/nebo zamez přístupu k souborům readme.html a licence.txt**
- [ ] Zváž nastavení automatické aktualizace pluginů
- [ ] **Pokud jsou použity formuláře, ověř, že jsou správně nastavené**

## Analytika a SEO před deployem
- [ ] **Ověř, že není zakázáno indexování a procházení robotů skrz meta noindex, nofollow, nosnippet a noarchive jako pozůstatek z dev prostředí**
- [ ] **Nasaď měřící skript Google Analytics**
	- [ ] **Akrivuj report demografie**
	- [ ] **Nastav délku uchování dat (Služba –> Údaje o měření –> Uchovávání dat)**
	- [ ] Nastav setSiteSpeedSampleRate pro zvýšení vzorků pro testování rychlosti (https://goo.gl/FRHiAp)
	- [ ] Nastav sledování událostí – event tracking (https://goo.gl/1xAgzO)
	- [ ] Nastav sledování cílů webu
	- [ ] Nastav omezení referral spamu (http://mareklecian.cz/spamfilter/)
	- [ ] Aktivuj Site Search (přidat „s“)
	- [ ] Aktivuj Analýzy na stránce (https://support.google.com/analytics/answer/2558867/?hl=cs)
	- [ ] Doplň kód o remarketing skript (https://goo.gl/Qy7e81)

## WordPress po deployi
- [ ] **Vygeneruj unikátní extra keys a salts ve wp-config.php**
- [ ] **Nastav správných CHMOD práv adresářům (např. uploads)**
- [ ] **Nasaď WP Super Cache**
- [ ] Přidej web/aplikaci do konzole ManageWP (pouze u supportovaných projektů)

## Analytika a SEO po deployi
- [ ] **Registruj web/aplikaci do Google Search Console**
	- [ ] **Podstrč sitemap.xml**
	- [ ] **Propoj Google Analytics a Search Console profilů (na straně GA)**

## Vyhledávače
~~- [ ] **Google** (https://www.google.com/webmasters/tools/submit-url) ~~
- [ ] **Seznam** (http://search.seznam.cz/pridej-stranku)
~~- [ ] **Bing** (http://www.bing.com/toolbox/submit-site-url)~~

## Ostatní
- [ ] **Ověř, že není soubor .env přístupný z prohlížeče, pokud jsou pro připojení k db použity dotnev proměnné**
- [ ] Zvaž přidání informační stránky "Informace o zpracování osobních údajů/Jaké osobní údaje zpracováváme" (např. do patičky, jako odkaz k formulářům, atp. na všechna místa, kde se s os. údaji pracuje)
- [ ] Směruj starých URL na nové přes kód 301 (pokud bylo dohodnuto s klientem)
- [ ] Zváž přidání souboru `.well-known/security.txt`
- [ ] Přidej do monitoringu Statusdroid
- [ ] **Otestuj performance webu**
	- [ ] Google PageSpeed Insights (https://developers.google.com/speed/pagespeed/insights/)
	- [ ] Google Mobile Friendly (https://search.google.com/search-console/mobile-friendly)
	- [ ] WebPagetest (http://www.webpagetest.org) *Speed Index ideálně kolem 1000 (na LTE), průměr 5000–10000*
	- [ ] Lighthouse (https://developers.google.com/web/tools/lighthouse/run)
        - *First Meaningful Paint ideálně do 3 vteřin*
        - *First Interactive ideálně nízké jednotky vteřin*
        - *Perceptual Speed Index ideálně do 2000, nejvíce 5 000*
	- [ ] Yellow Lab Tools (http://yellowlab.tools)
	- [ ] GTmetrix (https://gtmetrix.com)
