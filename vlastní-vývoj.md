# Vlastní vývoj

Existuje několik možností, jak začít s vývojem letenkového e-shopu. Potřebujete si ale zodpovědět dvě základní otázky.

## Jste IATA agentura?

Tato otázka bude důležitá podle toho, jaký zdroj dat pro svůj e-shop si vyberete. Pokud si vyberete GDS \(viz. další kapitola\), je  podstatné si hned zkraje uvědomit, jestli do celého dobrodružství půjdete zcela sami, nebo jestli budete potřebovat partnera.

Pokud IATA agentura nejste nebo nevíte, co to je, budete nejspíš potřebovat partnerství s nějakou už hotovou IATA agenturou. Aktuálně pracuji na tom, abych zde mohl přímo uvést kontakty na konkrétní lidi, které čekají na právě takové, jako jste vy.

Pokud máte certifikaci IATA, budete moci letenky nejen rezervovat, ale i vystavovat. Finanční závazek a zodpovědnost za vystavování tak bude vznikat přímo vám.

## Kde vezmete data?

* **Screenscraping** - Teoreticky se nemusíte nikoho na nic ptát. Můžete rovnou začít "těžit" data z existujících webových portálů. To znamená simulovat průchod browseru a vyparsovávat data z HTML. Jedná se o celkem riskantní přístup. Lze očekávat řadu technických potíží a možná i obranu ze strany těžených webů.
* **1:1 API** - Lze kontaktovat jednotlivé letecké společnosti a domluvit si přístup k jejich datům na přímo. S tímto nemám příliš zkušeností. Obecně budete muset sladit různé formáty dat a přístupy k API. Navíc budete řešit kombinování různých společností pro delší cesty, správu rezervací apod.
* **1:1 NDC API** - NDC je snaha sjednotit API na úrovni leteckých společností a usnadnit tak integraci. Problémy kombinací cest a se správou rezervací bude podobný, jako v předchozím bodě.
* **Integrátoři** - Připojíte se k někomu, kdo už s různými zdroji dat pracuje za vás.
* **GDSy** - Nejserióznější vrstva integrátorů. Global distribution systems jsou systémy, do kterých jsou letecké společnosti už integrovány. Tyto systémy data dále kombinují a cachují. U nás přichází v úvahu Galileo \(to jsem já\) nebo Amadeus. GDSy nabízejí různá API, které můžete využit. Navíc poskytují přístupy kde se dají rezervace spravovat, měnit apod.



