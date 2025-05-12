**Proč F# (pouze funkcionální programování)?**

Objektivní hledisko: Ziskovější, neb méně chyb (na rozdíl od Roslynu vám FSC prakticky nic neodpustí), debugger se používá jen velmi zřídka, jestli vůbec (a to "zřídka" nastává zpravidla jen při interoperabilitě s .NET knihovnami), je méně unit testů, pokud vůbec má je smysl psát (integration tests a PBT samozřejmě ano), méně problémů při parallel programming při používání pure functions, žádné nereprodukovatelné chyby u pure functions, při údržbě, doplňování, změnách je funkcionální kód "odolnější ("nerozhodí" se tak snadno).

Subjektivní hledisko: Jasnější a přehlednější kód (je ho i méně, než v ekvivalentním C# kódu). Nicméně chápu, že někdo jiný může mít na "přehlednost a jasnost" zcela opačný názor, než já.

**Jaké jsou příčiny větší ziskovosti F#?**

Je to možná překvapivé, ale hlavním důvodem nejsou funkcionální prvky jako takové, ale:

- Immutability všude
- Stejné typy ve všech větvích kódu
- Absence nulls u F# typů (plus okamžitá eliminace nulls, které se snaží vplížit z .NET knihoven, pomocí Option nebo Result)
- Single-direction dependency

**Tomu nevěřím / nedovedu si to představit, jaký je důkaz?**

Bohužel, tady je třeba si to vyzkoušet a přesvědčit se sám (či někdo, komu věříte, což já nejsem), chápu, že může být těžké si z výše uvedeného představit větší ziskovost. Mohu Vám na požádání poskytnout veškeré své materiály ohledně funkcionálního programování, či byt jinak nápomocen **(například zdarma účastí na Vašem ověřovacím zkušebním F# projektu)**. 

**V C# je dnes plno funkcionálních prvků, plně funkcionálně mohu přece programovat i v tomto jazyce?**

Striktně vzato plně funkcionálně nemůžete. Přiblížit se ano. Nicméně zkuste si přepsat některý funkcionální kód v Haskellu či F# do "funkcionálního C#", a domnívám se, že sami velice rychle přijdete na to, že to opravdu není to, co byste chtěli (a že to bylo alespoň 2x delší, že? :-) ). C# nebylo na FP "konstruováno" - přidáním volantu a kol (funkcionálních prvků) z Porsche (F#, Haskell) ke koloběžce (C#) z této koloběžky Porsche neuděláte. 

**Ale i v F# jsou přece OOP a imperativní prvky ...** 

Ano, jsou, kvůli interoperabilitě s .NET knihovnami psanými v C#. Určitá disciplina v "nepoužívání něčeho" je tedy pro psaní funkcionálního kódu v F# nutná, na rozdíl od Haskellu - viz https://github.com/MiroslavHustak/FSharp-Coding-Guidelines. Pokud budete používat imperativní a OOP prvky ne z důvodů interoperability (což ale jde proti podnikatelské logice), garantovat větší ziskovost, menší chybovost, přehlednost, jasnost atd. nemohu. Nemohu ani garantovat to, že seženete F# programátora ochotného takový "mišmaš" udržovat/upravovat/předělávat.    

**Kde seženu F# programátory?** 

Pokud je "nezlanaříte" z konkurenčních firem v Praze anebo nechcete spolupracovat s "remote" F# programátory (těch je po světě plno), pak ve vlastní firmě. Funkcionální programování je jednoduché, intuitivní, naučení se FP je (dle informací z F# Slack) u dobrých programátorů otázka 3-4 dnů (pro samotný jazyk a pak ta samá doba pro každou technologii pro web, desktop či mobil), u průměrných programátorů, jako jsem já, je to cca 2-3 týdny na jazyk/technologii (dle vlastní zkušenosti). Když už mohu v F# programovat já, kterýžto nemá žádné formální IT vzdělání a žádnou pomoc od kolegů, neb jsem OSVČ, pak už musí FP zvládnout opravdu každý, navíc kdy LLMs mohou často významně pomoci s výukovým procesem. Jediné, co může být velmi problematické, je neochota přepnout myšlení. Funkcionální programování je opravdu zcela jiné.

**Bude muset F# programátor znát kromě FP i celé OOP v F#?** 

Ano i ne. Normálně tedy ani ne. Při běžném programování sice nebudete mít „100% Haskell-like“ kód, ale z velké části ano – třeba můj poslední program je z 98% funkcionální (toto procento ale velmi závisí na okolnostech). Zbytek nejčastějí spočívá v nastavování vlastností (properties), inicializaci objektů (volání konstruktorů tříd), nějaká ta metoda či dědičnost se také tu a tam vyskytne - vše v souvislosti s používanými knihovnami z .NET (výjimkou je builder pro CE s použitím metod na SCDU). Takže abych odpověděl na otázku - stačí jen minimální znalost OOP. Pokud byste se však chtěli zapojit do vývoje OSS a vytvořit třeba funkcionální wrapper nad nějakou .NET knihovnou či technologií, bude třeba OOP znát (kvůli interoperability).

**Je něco, co C# má a v F# to budu postrádat?** 

Ano, NullReferenceException :-). 
