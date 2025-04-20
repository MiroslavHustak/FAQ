**Proč F# (pouze funkcionální programování)?**

Objektivní hledisko: Ziskovější, neb méně chyb (na rozdíl od Roslynu Vám FSC nic neodpustí), debugger se používá jen velmi zřídka, jestli vůbec, je méně unit testů, pokud vůbec (integration tests a PBT samozřejmě ano), méně problémů při parallel programming při používání pure functions, žádné nereprodukovatelné chyby u pure functions.

Subjektivní hledisko: Jasnější a přehlednější kód (je ho i méně, než v ekvivalentním C# kódu). "Radostnější" programování. Nicméně tady chápu, že někdo jiný může mít na "přehlednost, jasnost a radostnost" zcela opačný názor, než já.

**Příčiny větší ziskovosti F#?**

Je to možná překvapivé, ale důvodem nejsou funkcionální prvky jako takové, ale:

- Immutability všude
- Stejné typy ve všech větvích kódu
- Absence nulls (příp. jejich okamžitá eliminace s Option types na vstupu z .NET knihoven)
- Single-direction dependency

**Tomu nevěřím / nedovedu si to představit, jaký je důkaz?**

Bohužel, tady je třeba si to vyzkoušet a přesvědčit se sám (či někdo, komu věříte, což já nejsem), chápu, že může být těžké si z výše uvedeného představit větší ziskovost. Mohu Vám na požádání poskytnout veškeré své materiály ohledně funkcionálního programování, či byt jinak nápomocen **(například zdarma účastí na Vašem ověřovacím zkušebním F# projektu)**. 

**V C# je dnes plno funkcionálních prvků, funkcionálně mohu přece programovat i v tomto jazyce?**

Striktně vzato nemůžete. Přiblížit se ano. Nicméně zkuste si přepsat některý funkcionální kód do "funkcionálního C#", a domnívám se, že sami velice rychle přijdete na to, že to opravdu není to, co byste chtěli. C# nebylo na FP "konstruováno" - přidáním volantu a kol (= funkcionálních prvků) z Porsche (F#, Haskell) ke koloběžce (C#) z této koloběžky Porsche neuděláte. 

**V F# jsou ale přece i OOP a imperativní prvky?** 

Ano, jsou, kvůli interoperabilitě s .NET knihovnami psanými v C#. Určitá disciplina je tedy v F# nutná, na rozdíl od Haskellu - viz https://github.com/MiroslavHustak/FSharp-Coding-Guidelines. Pokud budete používat imperativní a OOP prvky z jiných důvodů (což ale jde proti podnikatelské logice), garantovat větší ziskovost nemohu.  

**Kde seženu F# programátory?** 

Pokud je "nezlanaříte" z konkurenčních firem v Praze anebo nechcete remote F# programátory (těch je po světě plno), pak ve vlastní firmě. Funkcionální programování je jednoduché, intuitivní, naučení se FP je u dobrých programátorů otázka 3-4 dnů (pro samotný jazyk a pak ta samá doba pro každou technologii pro web, desktop či mobil), u průměrných programátorů, jako jsem já, je to cca 2-3 týdny na jazyk/technologii. Když už mohu v F# programovat já, kterýžto nemá žádné formální IT vzdělání a žádnou pomoc od kolegů, neb jsem OSVČ, pak už musí FP zvládnout opravdu každý, navíc kdy LLMs mohou často významně pomoci s výukovým procesem. Jediné, co může být velmi problematické, je neochota přepnout myšlení. Funkcionální programování je opravdu zcela jiné.

**Bude muset F# programátor znát kromě FP i celé OOP v F#?** 

Ano i ne. Při běžném programování sice nebudete mít „100% Haskell-like“ kód, ale z velké části ano – třeba můj poslední program je z 98% funkcionální (toto procento ale velmi závisí na okolnostech). Zbytek obvykle spočívá v nastavování vlastností (properties) nebo inicializaci objektů (volání konstruktorů tříd), a to v souvislosti s používanými knihovnami z .NET. Takže znalost OOP nemusí být nikterak velká. Pokud byste však chtěli vytvořit funkcionální wrapper nad nějakou .NET knihovnou či technologií, bude nezbytné znát důkladně jak FP, tak i OOP v prostředí F#.

**Je něco, co C# má a v F# to chybí?** 

Ano, NullReferenceException :-). A classic joke :-).
