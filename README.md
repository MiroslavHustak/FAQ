**Proč F# (pouze funkcionální programování)?**

Objektivní hledisko: Ziskovější, neb méně chyb (na rozdíl od Roslynu vám FSC prakticky nic neodpustí a vyrobit chybu vyžaduje někdy hodně úsilí a znalostí), debugger se používá jen velmi zřídka, jestli vůbec (a to "zřídka" nastává zpravidla jen u interoperability s .NET knihovnami), je méně unit testů, pokud vůbec má je smysl psát (PBT samozřejmě ano, integration tests po úvaze), méně problémů při paralelním programování (při používání pure či lazy functions), žádné nereprodukovatelné chyby u pure functions, při údržbě, doplňování, změnách je funkcionální kód "odolnější ("nerozhodí" se tak snadno).

Subjektivní hledisko: Jasnější a přehlednější kód (je ho i méně, než ekvivalentního C# kódu). Nicméně chápu, že někdo jiný může mít na "přehlednost a jasnost" zcela opačný názor, než já.

**Jaké jsou příčiny větší ziskovosti F#?**

Je to možná překvapivé, ale hlavním důvodem nejsou funkcionální prvky jako takové, ale:

- Immutability všude
- Single-direction dependency
- Stejné typy ve všech větvích kódu
- Absence nulls u F# typů (plus okamžitá eliminace nulls, které se snaží vplížit z .NET knihoven, pomocí Option nebo Result)
- Separace purity a impurity
- Separace dat a operací s daty (což je zcela v protikladu s principy class-based OOP)

**Tomu nevěřím / nedovedu si to představit, jaký je důkaz?**

Bohužel, tady je třeba si to vyzkoušet a přesvědčit se sám (či někdo, komu věříte, což já nejsem), chápu, že může být těžké si z výše uvedeného představit větší ziskovost. Mohu Vám na požádání poskytnout veškeré své materiály ohledně funkcionálního programování, či byt jinak nápomocen **(například účastí na Vašem ověřovacím zkušebním F# projektu)**. 

**V C# je dnes plno funkcionálních prvků, plně funkcionálně mohu přece programovat i v tomto jazyce?**

Striktně vzato plně funkcionálně nemůžete. Přiblížit se ano. Nicméně zkuste si přepsat některý funkcionální kód v Haskellu či F# do "funkcionálního C#", a domnívám se, že sami velice rychle přijdete na to, že to opravdu není to, co byste chtěli (a že to bylo alespoň 2x delší, že? :-) ). C# nebylo na FP "konstruováno" - přidáním volantu a kol z Porsche (F#, Haskell) ke koloběžce (C#) z této koloběžky Porsche neuděláte. Navíc máte 10-20 let zpoždění vůči FP jazykům. 

**Ale i v F# jsou přece OOP a imperativní prvky ...** 

Ano, jsou, kvůli interoperability s .NET knihovnami psanými v C#. Určitá disciplina v "nepoužívání něčeho" je tedy pro psaní funkcionálního kódu v F# nutná, na rozdíl od Haskellu - viz https://github.com/MiroslavHustak/FSharp-Coding-Guidelines. Pokud budete používat imperativní a OOP prvky ne z důvodů interoperability, ale "protože jste na ně zvyklí" (což ale jde proti podnikatelské logice - proč jste tedy investovali do F#, že?), garantovat větší ziskovost, menší chybovost, přehlednost, jasnost atd. nemohu. Nemohu ani garantovat to, že seženete F# programátora ochotného takový "mišmaš" udržovat/upravovat/předělávat.    

**Kde seženu F# programátory? Musí znát vysokoškolskou matematiku?** 

Pokud funkcionální programátory "nezlanaříte" z konkurenčních firem v Praze anebo nechcete spolupracovat s "remote" F# programátory (těch je po světě plno), pak je seženete ve vlastní firmě. Funkcionální programování je jednoduché, intuitivní, naučení se FP je (dle informací z F# Slack) u dobrých programátorů otázka 3-4 dnů (pro samotný jazyk a pak ta samá doba pro každou technologii pro web, desktop či mobil), u běžných/obyčejných programátorů, jako jsem já, je to cca 2-3 týdny na jazyk/technologii (dle vlastní zkušenosti). Když už mohu v F# programovat já, kterýžto nemá žádné formální IT vzdělání a žádnou pomoc od kolegů, neb jsem OSVČ, pak už musí FP zvládnout opravdu každý, navíc kdy LLMs mohou často významně pomoci s výukovým procesem. Jediné, co může být velmi problematické, je neochota přepnout myšlení. Funkcionální programování je opravdu zcela jiné.

Znalost matematiky 8. třídy ZŠ je vše, co budete běžně potřebovat. Jen pokud se budete pouštět do ML, DL, LLM atd. (jinými slovy do oblasti numerických řešení matematických či pravděpodobnostních modelů), tak tam je to stejné, jako u OOP nebo procedurálních programátorů - znalost matematiky prvních čtyř semestrů VŠ technického zaměření se docela hodí.

**Bude muset F# programátor znát kromě FP i celé OOP v F#?** 

Ano i ne. Normálně tedy ani ne. Při běžném programování sice nebudete mít „100% Haskell-like“ kód, ale z velké části ano – třeba můj poslední program je z 98% funkcionální. Zbytek nejčastějí spočívá v nastavování vlastností (properties), inicializaci objektů (volání konstruktorů tříd), nějaká ta metoda či dědičnost se také tu a tam vyskytne - vše v souvislosti s používanými knihovnami z .NET (výjimkou je builder pro CE s použitím metod na SCDU). Procento "funkcionálnosti" ale velmi závisí na okolnostech, momentálně vytvářím "mini" LLM pomocí TorchSharp (ekv. PyTorch pro .NET) a tam už je OOP prvků více. Takže abych odpověděl na otázku - stačí jen minimální znalost OOP. Pokud byste se však chtěli zapojit do vývoje OSS a vytvořit třeba funkcionální wrapper nad nějakou .NET knihovnou či technologií, bude třeba OOP znát (kvůli interoperability).

**Je něco, co C# má a v F# to budu postrádat?** 

Ano, NullReferenceException :-). 
