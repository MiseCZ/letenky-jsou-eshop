# Jak postavit web na rezervaci letenek

Pro ilustraci bodu používat obrázky z naší aktuální verze GOL IBE D3. Aktuálně pracujeme na modernější D4. A najdete hodně IBE s odvážnějším přístupem k designu. Tento je řekněme konzervativní.

## Vyhledávací formulář

Základem bude vyhledávací formulář. Například takový:

![](/assets/GOL-vyhledávácí-formulář-D3.png)

Jak vidíte budete od zákazníka hned zkraje potřebovat celou řadu informací:

* **Destinace cesty** - primárně city pair odkud kam a pak varianty pro jednosměrný let a lety, kdy se vracíte odjinud \(nebo jinam\), a možná i vícefázové lety. Pro výběr destinací budete potřebovat také nějakého pomocníka - našeptávač, výběr destinací, mapu nebo cokoliv, co s čím vaše fantazie přijde.
* **Data odletů** - podle typu cestu dvě, jedno nebo naopak více. Také tady se hodí pomocník, typicky v podobě otvíracích kalendářů. Ke zvážení je i možnost zadávat meze pro čas odletu.
* **Typy cestujících** - Typy, které chcete. Určitě ale věnujte prostor vysvětlení věkových \(případně jiných\) omezení.
* **Třída** - Zde vybrány tři běžné.
* **Letecká společnost** - Kromě letecký společností je pro některá API možné používat i kódy leteckých aliancí.
* **Přímé lety** - mohlo by se zdát, že jde o zbytečný prvek, ale stane se důležitým pokud v systému existuje hodně levných přestupných letů. Pak si už při dotazování potřebujete vynutit, že chcete přímé lety. I když vás pak jejich cena může zaskočit.

U vyhledávacího formuláře byste možná také měli vzít v úvahu, že jej budete chtít umísťovat na více stránek než jen na jednu, napevno integrovanou do vašeho IBE.

## Výsledky vyhledávání

Mohou vypadat třeba takto:

![](/assets/GOL-výsledky-vyhledávání-D3.png)

Důležité informace jsou:

* **Čísla letů** - Některé frontendy je v této fázi za důležité nepovažují a nezobrazují je.
* **Routing** - Přes jaká města a letiště se letí. Různé frontendy se informaci o přestupních místech snaží zmenšovat.
* **Datum, čas a doby** - Je třeba si vybrat, jak naložit s informacemi o datu a času odletu a přistání. Jak zákazníka upozornit, pokud někde cestuje či zůstává přes půlnoc. A jestli mu pomoci s výpočtem, jak dlouho cestuje či přestupuje.
* **Letecká společnost** - Víme, že každý segment má svoji marketingovou společnost a může mít i odlišného operujícího dopravce \(zde označeno óčkem "O"\). Přesto dost frontendů zobrazuje pouze jedno logo dopravce.
* **Cena letenky** - V zásadě je třeba se rozhodnou, zda zobrazuji cenu za všechny cestující dohromady nebo nějak zvlášť.

Důležité ovládací prvky:

* **Varianty letu** - Zde je vidět select box na odletu v "15:10", který umožňuje vybrat jinou variantu letu tam \(za stejnou cenu\). Některé frontendy tuto volbu nabízejí dvoukrokově \(po stisknutí tlačítka Vybrat let\). Nebo varianty rovnou roznásobují \(GDS je nabízí spojeně\) a zobrazují více nabídek pod sebou. Toto je jedno z těch větší a důležitějších rozhodnutí.
* **Filtry a řazení** - Vzhledem k tomu, že na řadu vyhledávání budete nabízet opravdu hodně výsledků \(protože třeba na cestu z Prahy do Londýna lze vytvořit asi tak milión kombinací s přestupy po celé Evropě\). Je skoro nezbytné nabídnout zákazníkům nějaké nástroje, jak s hromadou výsledků pracovat.
* **Další informace** - Řadě cestujícím nebudou strohé informace o letu stačit a budou potřebovat další. Cestující na dovolenou budou potřebovat vědět, kolik je v ceně zavazadel. Lidé, kteří v zahraničí pracují nebo studují, budou zase chtít vědět, jestli u zpáteční letenky mohou levně změnit datum návratu. A fajnšmekři budou třeba chtít znát typ letadla, kterým poletí. Nebo si přečíst detailní znění tarifů. Je na vás kolika tlačítky a ikonkami nabídku ověsíte. Pro některé informace, budete ale muset pokládat dodateční dotazy na server.

## Informace o cestujících

Opět příklad:

![](/assets/GOL-informace-o-cestujících-D3.png)

Jde o spíše maximalistickou variantu, kdy se kromě jména a příjmení vybírají i informace o pasu, věrnostní program a preference ohledně sedačky \(ulička/okénko\) a jídla \(je na to číselník\). V této podobě jsou preference spíše přání než garantovaná služba.

Rezervace na přesnou sedačku není k dispozici vždy a vyžadovala by zvláštní proces s vyžádáním mapy letadla a výběrem z volných sedaček. Někdy placených.

Za zvláštní pozornost stojí oslovení, které slouží i k odlišení cestujících se shodnými jmény. Otec a syn mohou být MR a MSTR \(master\) nebo JR a SR. Je to na složitější vysvětlování pokud používáte API, kde si to musíte ošetřovat sami \(GWS\), a nemusíte to řešit pokud použijete něco chytřejšího \(GOL API\).

[https://en.wikipedia.org/wiki/Master\_\(form\_of\_address\)](https://en.wikipedia.org/wiki/Master_(form_of_address)\)

## Další služby

Mezi běžné služby, které se k letenkám přidávají navíc, patří například pojištění nebo parkování na letišti. Letenková API, ale tyto služby obvykle nenabízí. Můžete tedy být tak kreativní, kolik si seženete dodavatelů služeb.

Implementaci vám dodatečné služby zkomplikují hlavně o vymýšlení, jak služby bookovat pokud možno transakčně \(alespoň trochu\). Dále pak, o chování při částečných selháních, výpadcích a timeoutech. Od určitého objemu návštěvnosti se vám stanou všechny nepříjemné zanedbané kombinace. A věřte, že je to dříve než myslíte.

## Po rezervaci \(a hlídač\)

Rezervace letenky bohužel nebývá, krátká atomická operace. Typicky položíte dotaz na vytvoření rezervace, systém si ji u sebe založí a potom začne ověřovat, jestli vám opravdu potvrdí jednotlivé segmenty letu. Obvykle na to potřebujete další dotazy, abyste se finálního stavu dopátrali.

Někdy to stihnete v řádu sekund, někdy musíte zákazníka u browseru držet málem minuty. A zákazník může browser samozřejmě kdykoliv zavřít. Už z toho důvodu doporučuji zakládat rezervace nejprve ve vaší databázi a teprve poté v systému, který používáte. Dále budete potřebovat nějakého hlídače, který bude pravidelně kontrolovat stav rezervací, u kterých neznáte finální stav.

My rozlišujeme pět základních stavů:

* Pending - rezervace vzniká
* Active - rezervace byla úspěšně vytvořena
* Issued - rezervace byla úspěšně ticketována
* Cancelled - rezervace byla zrušena
* Unsuccessful - rezervaci se nepodařilo úspěšně vytvořit

## Platba

O variantách, jak platit jsem se rozepsal v kapitole Základní kameny. Pro realizaci IBE bych doporučil jen jednu drobnost. Nemíchat dohromady "stav rezervace" a "stav platby". Nám se osvědčilo držet tyto dvě informace odděleně.

## Eticketing

Ne vždy budete eticketovat automaticky. Pokud bude zákazník platit například hotově na pobočce vaší agentury \(nebo agentury, se kterou spolupracujete\), bude letenky vystavovat pravděpodobně letenkář, který bude peníze přijímat. Tuto situaci vám ošetří výše zmíněný hlídač. Zrovna tak, jako situaci, kdy letenkář naopak z nějakého důvodu vaši úspěšnou rezervaci zruší.

Naopak eticketovat budete v případě, že zákazník úspěšně absolvuje procházku přes online platební bránu. Další detaily k tomu najdete v kapitole Základní kameny.

