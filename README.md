**Proč F# (pouze funkcionální programování)?**

Objektivní hledisko: Ziskovější, neb méně chyb (na rozdíl od Roslynu vám FSC prakticky nic neodpustí), debugger se používá jen velmi zřídka, jestli vůbec, je méně unit testů, pokud vůbec (integration tests a PBT samozřejmě ano), méně problémů při parallel programming při používání pure functions, žádné nereprodukovatelné chyby u pure functions, při údržbě, doplňování, změnách je funkcionální kód "odolnější ("nerozhodí" se tak snadno).

Subjektivní hledisko: Jasnější a přehlednější kód (je ho i méně, než v ekvivalentním C# kódu). "Radostnější" programování. Nicméně tady chápu, že někdo jiný může mít na "přehlednost, jasnost a radostnost" zcela opačný názor, než já.

**Příčiny větší ziskovosti F#?**

Je to možná překvapivé, ale hlavním důvodem nejsou funkcionální prvky jako takové, ale:

- Immutability všude
- Stejné typy ve všech větvích kódu
- Absence nulls u F# typů (plus okamžitá eliminace nulls, které se snaží vplížit z .NET knihoven, pomocí Option nebo Result)
- Single-direction dependency

**Tomu nevěřím / nedovedu si to představit, jaký je důkaz?**

Bohužel, tady je třeba si to vyzkoušet a přesvědčit se sám (či někdo, komu věříte, což já nejsem), chápu, že může být těžké si z výše uvedeného představit větší ziskovost. Mohu Vám na požádání poskytnout veškeré své materiály ohledně funkcionálního programování, či byt jinak nápomocen **(například zdarma účastí na Vašem ověřovacím zkušebním F# projektu)**. 

**V C# je dnes plno funkcionálních prvků, plně funkcionálně mohu přece programovat i v tomto jazyce?**

Striktně vzato nemůžete. Přiblížit se ano. Nicméně zkuste si přepsat některý funkcionální kód v Haskellu či F# do "funkcionálního C#", a domnívám se, že sami velice rychle přijdete na to, že to opravdu není to, co byste chtěli (a že to bylo alespoň 2x delší, že? :-) ). C# nebylo na FP "konstruováno" - přidáním volantu a kol (funkcionálních prvků) z Porsche (F#, Haskell) ke koloběžce (C#) z této koloběžky Porsche neuděláte. 

**V F# jsou ale přece i OOP a imperativní prvky?** 

Ano, jsou, kvůli interoperabilitě s .NET knihovnami psanými v C#. Určitá disciplina je tedy v F# nutná, na rozdíl od Haskellu - viz https://github.com/MiroslavHustak/FSharp-Coding-Guidelines. Pokud budete používat imperativní a OOP prvky ne z důvodů interoperability (což ale jde proti podnikatelské logice), garantovat větší ziskovost, menší chybovost, přehlednost, jasnost atd. nemohu. Nemohu ani garantovat to, že seženete F# programátora ochotného takový "mišmaš" udržovat/upravovat/předělávat.    

**Kde seženu F# programátory?** 

Pokud je "nezlanaříte" z konkurenčních firem v Praze anebo nechcete spolupracovat s "remote" F# programátory (těch je po světě plno), pak ve vlastní firmě. Funkcionální programování je jednoduché, intuitivní, naučení se FP je (dle informací z F# Slack) u dobrých programátorů otázka 3-4 dnů (pro samotný jazyk a pak ta samá doba pro každou technologii pro web, desktop či mobil), u průměrných programátorů, jako jsem já, je to cca 2-3 týdny na jazyk/technologii. Když už mohu v F# programovat já, kterýžto nemá žádné formální IT vzdělání a žádnou pomoc od kolegů, neb jsem OSVČ, pak už musí FP zvládnout opravdu každý, navíc kdy LLMs mohou často významně pomoci s výukovým procesem. Jediné, co může být velmi problematické, je neochota přepnout myšlení. Funkcionální programování je opravdu zcela jiné.

**Bude muset F# programátor znát kromě FP i celé OOP v F#?** 

Ano i ne. Normálně tedy ani ne. Při běžném programování sice nebudete mít „100% Haskell-like“ kód, ale z velké části ano – třeba můj poslední program je z 98% funkcionální (toto procento ale velmi závisí na okolnostech). Zbytek obvykle spočívá v nastavování vlastností (properties) nebo inicializaci objektů (volání konstruktorů tříd), a to v souvislosti s používanými knihovnami z .NET. Takže stačí jen minimální znalost OOP. Pokud byste se však chtěli zapojit do vývoje OSS a vytvořit třeba funkcionální wrapper nad nějakou .NET knihovnou či technologií, bude třeba OOP znát.

**Co se týče vibe coding, sice se k tomu stavím velmi opatrně, nicméně do jistý míry může pomoci, tak jako IntelliSense. Jsou při vibe coding lepší výsledky u FP nebo u OOP?** 

Nejen já bych rád znal odpověď na tuto otázku. Drtivá většina dnešních FP programátorů sice zná OOP (neb tím začínali), nicméně když už dnes OOP nepoužívají, také hledají odpověď u jiných - a to můžete být, na rozdíl od nás, i vy :-). Těšíme se na vaši "porovnávací" zkušenost s vibe coding v OOP a FP. Mimochodem, LLMs tvrdí, že lepší výsledky jsou u FP.

**Je něco, co C# má a v F# to chybí?** 

Ano, NullReferenceException :-). A classic joke :-).
