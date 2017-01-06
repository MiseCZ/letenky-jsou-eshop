# APIs - základní představení

Aktuální API, o kterých něco vím. Jde o základní přehled, pro vývoj je nutné znát celou řadu dalších informací. 

## Universal API \(UAPI\)

Hlavní API nabízené společností Travelport. Použitelné, pokud agentura pracuje se systémy Galileo, Apollo nebo Worldspan.  Kromě letenek zvládá i rezervaci hotelů, železničních jízdenek a autopůjčoven. Fakticky jde o SOAP server, se kterým se komunikuje pomocí rozsáhlých XML dokumentů.

* Dokumentace: [https://developer.travelport.com/app/developer-network/universal-api](https://developer.travelport.com/app/developer-network/universal-api)

## UAPI JSON

Nadstavba nad UAPI napsaná v node.js, se která usnadňuje komunikaci s UAPI. Místo rozsáhlých XML se používají zjednodušené JSONy. Hodí se zejména na prozkoumání terénu.

* Github: [https://github.com/Travelport-Ukraine/uapi-json](https://github.com/Travelport-Ukraine/uapi-json)

## Galileo Web Services \(GWS\)

Starší varianta společnosti Travelport. Fakticky jde stejně jako u UAPI o SOAP server, se kterým se komunikuje XMLky. Chybí některé novější vlastnosti UAPI. Dneska už nemá smysl vývoj s tímto začínat.

* Dokumentace: [https://developer.travelport.com/app/developer-network/classic-apis/](https://developer.travelport.com/app/developer-network/classic-apis/)

## GOL API

Nadstavba nad vícero systémy vyvíjená Travelport Czech Republic \(námi\). Integruje GWS, GTA, Travelfusion a některé další. Nad tradičním systémy nabízí i řešení správy rezervací, uživatelských účtů, dealerského prodeje, servisních poplatků a dalších vlastností, které stejně budete muset řešit. Komunikuje se XMLky po http. Hodí se na prozkoumání terénu a šetření vývoje zázemí. K dispozici je i white label mobilní aplikace pro iOS a Android.

* Kontakt: martin.brandysky@travelportgds.cz

## GTA

Jde o rezervační systém umožňující rezervaci hotelů. Posílají se XMLka po http.

* Dokumentace: [http://www.gta-travel.com/en/buy-from-us/how-to-work-with-us/gta-xml-api](http://www.gta-travel.com/en/buy-from-us/how-to-work-with-us/gta-xml-api)

## Travelfusion

Integrace zejména low cost leteckých dopravců. Neumožňuje ale takovou kontrolu nad rezervacemi, jako tradiční GDSy. Komunikuje se XMLky po http.

* Dokumentace: [http://xmldocs.travelfusion.com/](http://xmldocs.travelfusion.com/)



