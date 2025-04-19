**Disclaimer: Pokud Vámi tvořený kód nemá po zkompilování chyby (nepotřebujete debugger), snadno se udržuje a i při rozsáhlých změnách se nikdy neopravitelně "nepokazí" (či jak to říct diplomaticky), není třeba číst dále.**
<br>

**Proč F# (pouze funkcionální programování)?**

Objektivní hledisko: Ziskovější, neb méně chyb (na rozdíl od Roslynu Vám FSC nic neodpustí), debugger jen velmi zřídka, jestli vůbec, méně unit testů, pokud vůbec (integration tests a PBT samozřejmě ano), méně problémů při parallel programming při pure functions.

Subjektivní hledisko: Jasnější a přehlednější kód (je ho i méně). "Radostnější" programování. Nicméně tady chápu, že někdo jiný může mít na "přehlednost, jasnost a radostnost" zcela opačný názor, než já.

**Příčiny větší ziskovosti F#?**

Je to možná překvapivé, ale důvodem nejsou funkcionální prvky jako takové, ale:
<ul>
<li>Immutability všude</li>
<li>Stejné typy ve všech větvích kódu</li>
<li>Absence null (příp. jejich okamžitá eliminace s Option types na vstupu z .NET knihoven)</li>
<li>Single-direction dependency</li>
</ul>

**Tomu nevěřím / nedovedu si to představit, jaký je důkaz?**

Bohužel, tady je třeba si to vyzkoušet a přesvědčit se sám (či někdo, komu věříte, což já nejsem), chápu, že může být těžké si z výše uvedeného představit větší ziskovost. Mohu Vám na požádání poskytnout veškeré své materiály ohledně funkcionálního programování, či byt jinak nápomocen (**například zdarma účastí na Vašem ověřovacím zkušebním F# projektu**). 

**V C# je dnes plno funkcionálních prvků, funkcionálně mohu přece programovat i v tomto jazyce?**

Striktně vzato nemůžete. Přiblížit se ano. Nicméně zkuste si přepsat některý funkcionální kód do "funkcionálního C#", a domnívám se, že sami velice rychle přijdete na to, že to opravdu není to, co byste chtěli. Přidáním volantu a kol z Porsche ke koloběžce z této koloběžky Porsche neuděláte. 

**V F# jsou ale přece i OOP a procedurální prvky?** 

Ano, jsou, kvůli interoperabilitě s .NET knihovnami psanými v C#. Určitá disciplina je tedy nutná, na rozdíl od Haskellu - viz https://github.com/MiroslavHustak/FSharp-Coding-Guidelines. Pokud budete používat procedurální a OOP prvky z jiných důvodů, garantovat větší ziskovost nemohu.  

**Kde seženu F# programátory?** 

Pokud je "nezlanaříte" z konkurenčních firem v Praze anebo nechcete remote F# programátory (těch je po světě plno), pak ve vlastní firmě. Funkcionální programování je jednoduché, intuitivní, naučení se FP je u dobrých programátorů otázka 3-4 dnů (pro samotný jazyk a pak ta samá doba pro každou technologii pro web, desktop či mobil), u průměrných programátorů, jako jsem já, je to cca 2-3 týdny na jazyk/technologii. Když už mohu v F# programovat já, kterýžto nemá žádné formální IT vzdělání a žádnou pomoc od kolegů, neb jsem OSVČ, pak už musí FP zvládnout opravdu každý. Jediné, co na funkcionálním programování může být velmi težké, je neochota přepnout myšlení. Funkcionální programování je opravdu zcela jiné.

**Je něco, co C# má a F# ne?** 

Ano, NullReferenceException. :-)
