Festival Documentation (česky)

1. Přehled
*Název festivalu:* European Open‑Source & Alternative Tech Fair
*Ročník:* 1.
*Termín:* 1 května – 4 května 2025 (odkaz na vstup ČR do EU).
*Místa konání:* Varšava (Polsko).
*Definice:* Festival oslavuje evropské open‑source produkty, startupy a alternativní technologie. Pořádá se ve čtyřech halách (A‑D) a kombinuje přednášky, workshopy a herní arénu.

2. Identita

*Titulek:* První ročník oslavy evropských produktů a open‑source veletrh.
*Rok:* 2027.
*Halové uspořádání:* Haly A‑D (každá má 30 stánek).
*Hlavní myšlenka:* Ukázat výhody lokálních evropských a open‑source řešení a podpořit digitální suverenitu.

3. Cílové publikum

*Všechny věkové a profesní skupiny.*
Mladiství, kteří chtějí snížit závislost na velkých amerických technologiích.
Zaměstnanci, manažeři a rozhodovací orgány hledající alternativy a nezávislost na amerických technologiích.

4. Charakter akce

*Témata:*
Milníky a dostupnost evropských open‑source řešení.
Důležitost suverenity a nezávislosti na světovém trhu.
Výhody „going local“.
Startupy a inovace.
Bezpečnost a ochrana soukromí (Linux, Proton, Microslop sledování).

*Formát:*
Talks – velká scéna (přednášky).
Workshopy – střední scéna (praktické workshopy).
Games – malá scéna (herní, mediální, publikační a praktické výtvory).




5. Struktura webu (doporučený sitemap)

*Úvod/Home*– název, představení produktů, kategorie, sponzoři.
*Program* – rozpis přednášek, workshopů a herních bloků.
*Účinkující/Exhibitors* – seznam všech 75 vystavovatelů s detaily.
*Místa/Praktické info* – mapy hal, doprava, ubytování.
*Novinky/Blog* – aktuální zprávy, oznámení, tiskové zprávy.
*Kontakt/Podpora* – e‑mail, sociální sítě, FAQ.

Inspirace webu: viz styl shirtz.cool (před odevzdáním odstranit všechny brandové odkazy a zminky).

6. Technická specifikace
6. 6.1 Aktualizovaný validator.xsd
Detekuje chybějící či špatně pojmenované elementy (všechny povinné mají use="required").
Přidává povinné pole pro každého vystavovatele: website, representative a contactEmail.
Kategorie jsou nyní výčtem (Security, Technology, Software, Mix, Startup) – lze snadno rozšířit.
Definuje globální typy: time, hallNumber, email, url.

*Omezení:*
Min. 60, max. 80 vystavovatelů (pro startupy).
Min. 3, max. 5 dní.
Min. 2 místa na den.
Časové úseky HH:00 nebo HH:30.



6. 6.2 Program

Tři scény mohou běžet paralelně (přednášky, workshopy, herní arena).
Přednášky a workshopy: 1 hodina každá, s povinnou přestávkou na oběd 14:00 – 15:00 (v tuto dobu žádná aktivita).
Herní bloky: tři nezávislé 4‑hodinové bloky denně (10:00‑14:00, 14:00‑18:00, 18:00‑22:00). Ignorují obědovou přestávku a mohou se překrývat s ostatními scénami.
Denní časový rámec: 10:00 – 22:00. Přednášky a workshopy končí nejpozději v 19:00, následovaná volnou hodinou na neformální networking.

*Ukázka jednoho dne (XML fragment):*
<day id="1" date="2025-05-01">
    <!-- Talks (large stage) -->
    <event id="t1" stageRef="talks"><title>Opening Keynote – European Digital Sovereignty</title><presenter>European Commission</presenter><time>10:00</time></event>
    …
    <!-- Obědová pauza 14:00‑15:00 (žádné přednášky ani workshopy) -->
    …
    <!-- Gaming (small stage) -->
    <event id="g1" stageRef="games"><title>Gaming Showcase – EU Indie Strategy (10:00‑14:00)</title><presenter>GameDev EU</presenter><time>10:00</time></event>
    <event id="g2" stageRef="games"><title>Gaming Showcase – Open‑Source VR Experience (14:00‑18:00)</title><presenter>VR EU</presenter><time>14:00</time></event>
    <event id="g3" stageRef="games"><title>Gaming Showcase – Retro Arcade Revival (18:00‑22:00)</title><presenter>Retro Labs</presenter><time>18:00</time></event>
</day>

6. 6.3 Definice vystavovatele (exhibitor)
*ElementPopis*
<name>Název vystavovatele (čitelné).
<company>Právnická osoba vlastnící stánek.
<category>Kategorizace: Security, Technology, Software, Mix, Startup.
<location>Identifikátor haly + číslo stánku (např. A01, D30).
<content>Stručný popis nabízeného produktu/služby.
<website>Plná URL (http:// nebo https://).
<representative>Jméno osoby zodpovědné za stánek.
<contactEmail>E‑mail pro kontakt.atribut id (povinný)Jedinečný celočíselný identifikátor.

*Příklad:*
<exhibitor id="1">
    <name>Linux Foundation</name>
    <company>Linux Foundation</company>
    <category>Software</category>
    <location>A01</location>
    <content>Kernel development &amp; community governance</content>
    <website>https://www.linuxfoundation.org</website>
    <representative>Anna Novak</representative>
    <contactEmail>anna.novak@linuxfoundation.org</contactEmail>
</exhibitor>

Celkem je v souboru 75 vystavovatelů (60 standardních + 15 startupů) a všichni splňují výše uvedenou strukturu.

7. Zdroje & inspirace

Reddit: r/BuyFromEU
AlternativeTo.net
European‑Alternatives.eu
ForGames.cz – stránka Veletrh (layout inspirace)


8. Kontrolní seznam pro odevzdání

*mandatory*
specification.md – identita, publikum, struktura webu.
festival.xml – dobře formovaný XML soubor (4 dny, ≥ 2 místa/den, ≥ 60 vystavovatelů, ≥ 60 událostí).
*non-mandatory*
validator.xsd – aktualizovaný XSD s novými požadavky.
Program (přednášky, workshopy, herní bloky) respektuje 1‑hodinovou přestávku na oběd.
Všichni vystavovatelé mají vyplněny website, representative a contactEmail.
*Should be*
Dokumentace (README.md, specification.md) je v čistém markdownu.
