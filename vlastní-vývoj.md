# Vlastní vývoj

Existuje několik možností, jak začít s vývojem eshopu. Potřebujete si ale zodpovědět pár základních otázek.

## Jste IATA agentura?

Tato otázka bude důležitá podle toho, jak se rozhodnete v další kapitole. Každopádně je ale důležité si hned zkraje uvědomit, jestli do celého dobrodružství půjdete zcela sami nebo jestli budete potřebovat partnera.

Pokud IATA agentura nejste nebo nevíte, co to je budete možná potřebovat partnerství s nějakou IATA agenturou. Aktuálně pracuji na tom, abych zde mohl přímo uvést kontakty na konkrétní lidi, které čekají na právě takové, jako jste vy.

Pokud máte certifikaci IATA, budete moci letenky rezervovat i vystavovat. Finanční závazek bude vznikat přímo vám a sami si také budete muset domluvit přístup k veškerým datovým zdrojům.

## Kde vezmete data?

* _Screenscraping_ - Teoreticky se nemusíte nikoho na nic ptát. Můžete rovnou začít "těžit" data z existujících webových portálů. To znamená simulovat průchod browseru a vyparsovávat data z HTML. Jedná se o celkem riskantní přístup. Lze očekávat řadu technických potíží a možná i obranu ze strany těžených webů.
* _1:1 API_ - Lze kontaktovat jednotlivé letecké společnosti a domluvit si přístup k jejich datům na přímo. S tímto nemám příliš zkušeností. Obecně budete muset sladit různé formáty dat a přístupy k API.
* _1:1 NDC API_ - NDC je snaha sjednotit API na úrovni leteckých společností a usnadnit tak integraci.
* _Integrátoři_ - Připojíte se k někomu, kdo už s různými zdroji dat pracuje za vás.
* _GDSy_ - Nejserióznější vrstva integrátorů. Global distribution systems jsou systémy, do kterých jsou letecké společnosti už integrovány. Tyto systémy data dále kombinují a cachují. U nás přichází v úvahu Galileo \(to jsem já\) nebo Amadeus. GDSy nabízejí různá API, které můžete využit.



