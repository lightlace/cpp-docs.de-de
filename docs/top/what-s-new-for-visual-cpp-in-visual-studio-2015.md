---
title: "Neues bei Visual&#160;C++ in Visual Studio&#160;2015"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1cc09fad-85a2-43c2-b022-bb99f5fe0ad7
caps.latest.revision: 101
caps.handback.revision: "101"
ms.author: "ghogen"
manager: "ghogen"
---
# Neues bei Visual&#160;C++ in Visual Studio&#160;2015
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In Visual Studio 2015 wurden der C\+\+ Compiler und die Standardbibliothek mit erweiterter Unterstützung für C\+\+11 und grundlegender Unterstützung für bestimmte Features von C\+\+14 aktualisiert.  Diese schließen darüber hinaus vorläufige Unterstützung für bestimmte Features ein, deren Implementierung im C\+\+17\-Standard erwartet wird.  
  
 Es wurden außerdem Projektvorlagen für die plattformübergreifende Entwicklung für mehrere Geräte unter [Android und iOS](../Topic/Visual%20C++%20for%20Cross-Platform%20Mobile%20Development.md) hinzugefügt, verschiedene [Diagnose](#BK_Diagnostics)\- und [Produktivität](#BK_IDE)sverbesserungen vorgenommen und [Buildzeiten](#BK_FasterBuildTimes) deutlich verbessert.  
  
> [!WARNING]
>  In Visual Studio 2015 ist Visual C\+\+ nicht standardmäßig installiert   Achten Sie bei der Installation darauf, **Benutzerdefiniert** und anschließend die erforderlichen C\+\+\-Komponenten auszuwählen.  Wenn Visual Studio bereits installiert ist, wählen Sie **Datei &#124; Neu &#124; Projekt &#124; C\+\+**, anschließend werden Sie aufgefordert, die erforderlichen Komponenten zu installieren.  
  
 Informationen zu anderen Hinzufügungen in Visual Studio 2015 finden Sie unter [Neues in Visual Studio 2015](../Topic/What's%20New%20in%20Visual%20Studio%202015.md).  
  
 In diesem Thema:  
  
1.  [Compiler](#BK_Compiler)  
  
2.  [C++-Standardbibliothek](#BK_CppStdLib)  
  
3.  [C Runtime Library](#BK_CRT)  
  
4.  [Schnellere Builds](#BK_FasterBuildTimes)  
  
5.  [Leistung und Codequalität](#BK_PerfCodeQuality)  
  
6.  [Produktivität, Debuggen und Diagnose](#BK_IDE)  
  
    1.  [IntelliSense mit Einzeldatei](#BK_SingleFileIntelliSense)  
  
    2.  [Umgestaltung](#BK_Refactoring)  
  
    3.  [Verbesserungen der Programmdatenbank](#BK_PDB)  
  
    4.  [Diagnose](#BK_Diagnostics)  
  
7.  [Ausrichtung auf Windows 10](#BK_Win10)  
  
8.  [Grafikdiagnose](#BK_GraphicsDiagnostics)  
  
9. [Neues GPU-Auslastungstool](#BK_GPUUsage)  
  
10. [Neue MFC-Features](#BK_MFC)  
  
## Unterstützung von ISO\-C\/C\+\+\-Standards  
  
###  <a name="BK_Compiler"></a> Compiler  
  
-   **Fortsetzbare Funktionen \(resume\/await\)** Die Schlüsselwörter "resume" und "await" bieten Unterstützung auf Sprachebene für asynchrone Programmierung und ermöglichen fortsetzbare Funktionen.  Dieses Feature dient derzeit zu Testzwecken und wird nur für x64\-Ziele unterstützt.  **\(Vorgeschlagen für C\+\+17 \[N3858\]\)**  
  
-   **Generische \(polymorphe\) Lambda\-Ausdrücke** Parametertypen von Lambdafunktionen können jetzt mithilfe von "auto" angegeben werden; der Compiler interpretiert "auto" in diesem Kontext so, dass der Funktionsaufrufoperator der closure\-Klasse eine Memberfunktionsvorlage ist und jede Verwendung von "auto" im Lambda\-Ausdruck einem unterschiedlichen Vorlagentypparameter entspricht.  **\(C\+\+14\)**  
  
-   **Generalisierte Lambda\-Erfassungsausdrücke** Auch als "init\-capture" bezeichnet.  Das Ergebnis eines arbiträren Ausdrucks kann jetzt einer Variablen in der Erfassungsklausel eines Lambda\-Ausdrucks zugeordnet werden.  Dies ermöglicht die Erfassung von Typen, die nur zur Verschiebung dienen, nach dem Wert und ermöglichen einem Lambda\-Ausdruck, arbiträre Datenelemente in seinem Schlussobjekt zu definieren.  **\(C\+\+14\)**  
  
-   **Binäre Literale** Binäre Literale werden jetzt unterstützt.  Diesen Literalen steht ein Präfix 0B oder 0b voran, und sie bestehen lediglich aus den Ziffern 0 und 1.  **\(C\+\+14\)**  
  
-   **Ableitung des Rückgabetyps** Der Rückgabetyp normaler Funktionen kann jetzt abgeleitet werden; das trifft auch auf Funktionen mit mehreren Rückgabeanweisungen und auf rekursive Funktionen zu.  Diesen Funktionsdefinitionen steht jetzt das Schlüsselwort "auto" voran, wie bei Funktionsdefinitionen mit einem nachstehenden Rückgabetyp, der nachstehende Rückgabetyp wird jedoch ausgelassen.  **\(C\+\+14\)**  
  
-   **decltype\(auto\)** Typableitung mithilfe des Schlüsselworts "auto" zum Initialisieren von Ausdrücken entfernt Verweisqualifizierer und CV\-Qualifizierer der obersten Ebene aus dem Ausdruck.  Mit "decltype\(auto\)" werden Ref\- und CV\-Qualifizierer beibehalten; er kann nun überall dort verwendet werden, wo "auto" verwendet werden kann, ausgenommen bei der Einführung von Funktionen mit abgeleitetem oder nachstehendem Rückgabetyp.  **\(C\+\+14\)**  
  
-   **Implizite Generierung von speziellen Bewegungsmemberfunktionen** Bewegungskonstruktoren und Bewegungszuweisungsoperatoren werden jetzt implizit generiert, wenn es die Bedingungen zulassen, wodurch der Compiler sich hinsichtlich rvalue\-Verweisen vollständig C\+\+11\-konform verhält.  **\(C\+\+11\)**  
  
-   **Vererbung für Konstruktoren** Eine abgeleitete Klasse kann jetzt festlegen, dass sie die Konstruktoren ihrer Basisklasse "Base" erbt, indem sie die Anweisung mithilfe von "Base::Base;" in ihrer Definition verwendet.  Eine ableitende Klasse kann nur alle Konstruktoren ihrer Basisklasse erben, es gibt keine Möglichkeit, nur bestimmte Konstruktoren der Basis zu erben.  Eine ableitende Klasse kann nicht von mehreren Basisklassen erben, wenn sie über Konstruktoren mit identischer Signatur verfügen, noch kann die ableitende Klasse einen Konstruktor definieren, der eine mit einem geerbten Konstruktor identische Signatur aufweist.  **\(C\+\+11\)**  
  
-   **Abfrage und Steuerung der Ausrichtung** Die Ausrichtung einer Variablen kann mithilfe des Operators "alignof\(\)" abgefragt und mithilfe des Spezifizierers "alignas\(\)" gesteuert werden.  "alignof\(\)" gibt die Byte\-Grenze zurück, an der Instanzen des Typs zugeordnet werden müssen; bei Verweisen wird die Ausrichtung des referenzierten Typs und bei Arrays die Ausrichtung des Elementtyps zurückgegeben.  "alignas\(\)" steuert die Ausrichtung einer Variablen; als Argument wird eine Konstante oder ein Typ angenommen, wobei ein Typ die verkürzte Schreibung von "alignas\(alignof\(type\)\)" darstellt.  **\(C\+\+11\)**  
  
-   **Aufhebung der Zuordnung mit Größeninformationen** Die globalen  `void operator delete(void *, std::size_t) noexcept` und `void operator delete[](void *, std::size_t) noexcept` können nun überladen werden.  
  
-   **Erweitertes "sizeof"**Die Größe einer Klassen\- oder Strukturmembervariablen kann jetzt durch Verwendung von "sizeof\(\)" ohne eine Instanz der Klasse oder Struktur bestimmt werden. **\(C\+\+11\)**  
  
-   **Attribute** bieten eine Möglichkeit, die Syntax für Funktionen, Variablen, Typen und andere Programmelemente zu erweitern, ohne dass dafür neue Schlüsselwörter definiert werden müssen.**\(C\+\+11\)**  
  
-   **constexpr** Erstellung von konstanten Variablen, Funktionen und benutzerdefinierten Typen zur Kompilierzeit.  **\(C\+\+11\)**  
  
-   **Benutzerdefinierte Literale \(UDLs, User\-Defined Literals\)** Bedeutungstragende Suffixe können jetzt an numerische und Zeichenfolgenliterale angehängt werden, um ihnen eine bestimmte Semantik zu verleihen.  Der Compiler interpretiert Literale mit Suffix als Aufrufe des entsprechenden UDL\-Operators.  **\(C\+\+11\)**  
  
-   **"Magische" threadsichere statische Variablen** Lokale statische Variablen werden jetzt auf threadsichere Weise initialisiert, wodurch die Notwendigkeit der manuellen Synchronisierung entfällt.  Nur die Initialisierung ist threadsicher, die Verwendung von lokalen statischen Variablen durch mehrere Threads muss weiterhin manuell synchronisiert werden.  Die Funktion für threadsichere statische Variablen kann mithilfe des Flags "\/Zc:threadSafeInit\-" deaktiviert werden, um eine Abhängigkeit vom CRT zu vermeiden.  **\(C\+\+11\)**  
  
-   **Threadlokaler Speicher** Verwenden Sie das Schlüsselwort "thread\_local", um zu deklarieren, dass ein unabhängiges Objekt für jeden Thread erstellt werden soll.  **\(C\+\+11\)**  
  
-   **noexcept** Der Operator "noexcept" kann jetzt verwendet werden, um zu überprüfen, ob ein Ausdruck möglicherweise eine Ausnahme auslöst.  Der Spezifizierer "noexcept" kann jetzt verwendet werden, um anzugeben, dass eine Funktion keine Ausnahmen auslöst.  **\(C\+\+11\)**  
  
-   **Inline\-Namespaces** Ein Namespace kann jetzt als inline festgelegt werden, um seinen Inhalt auf den umschließenden Namespace auszudehnen.  Inline\-Namespaces können zum Erstellen versionierter Bibliotheken verwendet werden, die standardmäßig ihre aktuellste Version verfügbar machen, während frühere API\-Versionen explizit weiterhin verfügbar gemacht werden können.  **\(C\+\+11\)**  
  
-   **Unbeschränkte Unions** Ein Typ "Union" kann jetzt Typen mit nicht trivialen Konstruktoren enthalten.  Konstruktoren für diese Unions müssen definiert werden.  **\(C\+\+11\)**  
  
-   **Neue Zeichentypen und Unicode\-Literale** Zeichen\- und Zeichenfolgenliterale in UTF\-8, UTF\-16 und UTF\-32 werden jetzt unterstützt, und die neuen Zeichentypen "char16\_t" und "char32\_t" wurden eingeführt.  Zeichenliterale können die Präfixe "u8" \(UTF\-8\), "u" \(UTF\-16\) oder "U" \(UTF\-32\) wie in "U'a'" tragen, während Zeichenfolgenliterale zusätzlich die Rohzeichenfolgen\-Äquivalente "u8R" \(UTF\-8\-Rohzeichenfolge\), "uR" \(UTF\-16\-Rohzeichenfolge\), oder "UR" \(UTF\-32\-Rohzeichenfolge\) aufweisen können.  Universelle Zeichennamen können in Unicode\-Literalen frei verwendet werden, z. B. u'\\u00EF', u8"\\u00EF ist i" und u"\\U000000ef ist I".  **\(C\+\+11\)**  
  
-   **Trennzeichen für Ziffern** Einfache Anführungszeichen können in regelmäßigen Abständen eingefügt werden, damit lange numerische Literale besser zu lesen sind:  `int x = 1'000'000;` **C\+\+ 14**  
  
-   **\_\_func\_\_** Der vordefinierte Bezeichner "\_\_func\_\_" ist implizit als Zeichenfolge definiert, die den unqualifizierten und nicht erweiterten Namen der einschließenden Funktion enthält.  
  
-   **\_\_restrict \_\_** "restrict" kann jetzt auf Verweise angewendet werden.  
  
###  <a name="BK_CppStdLib"></a> C\+\+\-Standardbibliothek  
  
-   **Benutzerdefinierte Literale \(UDLs\) für Standardbibliothekstypen** Die Header \<chrono\>, \<string\> und \<complex\> stellen jetzt zu Ihrer Unterstützung UDL\-Operatoren bereit.  Beispielsweise bedeutet "123ms" "std::chrono::milliseconds\(123\)", "hello"s bedeutet "std::string\("hello"\)" und "3.14i" bedeutet "std::complex\(0.0, 3.14\)".  
  
-   **Null\-Vorwärtsiteratoren** Die Standardbibliothek ermöglicht jetzt die Erstellung von Vorwärtsiteratoren, die nicht auf eine Containerinstanz verweisen.  Diese Initiatoren sind wertinitialisiert und werden im Vergleich mit einem bestimmten Containertyp als gleich angesehen.  Der Vergleich eines wertinitialisierten Iterators mit einem nicht wertinitialisierten Iterator ist undefiniert.  **\(C\+\+14\)**  
  
-   **quoted\(\)** Die Standardbibliothek unterstützt jetzt die Funktion "quoted\(\)", um die Arbeit mit Zeichenfolgenwerten in Anführungszeichen sowie mit E\/A zu erleichtern.  Bei Angabe von "quoted\(\)" wird eine gesamte in Anführungszeichen stehende Zeichenfolge als einzelne Entität behandelt \(wie Zeichenfolgen von nicht aus Whitespace bestehenden Zeichen in E\/A\-Datenströmen\); darüber hinaus bleiben Escapesequenzen bei E\/A\-Vorgängen erhalten.  **\(C\+\+14\)**  
  
-   **Heterogenes assoziatives Nachschlagen** Die Standardbibliothek unterstützt jetzt heterogene Nachschlagefunktionen für assoziative Container.  Diese Funktionen ermöglichen das Nachschlagen nach anderen Typen als "key\_type", sofern der Typ mit "key\_type" vergleichbar ist.  **\(C\+\+14\)**  
  
-   **Integersequenzen zur Kompilierzeit** Die Standardbibliothek unterstützt jetzt den Typ "integer\_sequence", der eine Sequenz von ganzzahligen Werten darstellt, die zur Kompilierzeit ausgewertet werden kann, um das Arbeiten mit Parameterpaketen zu erleichtern und bestimmte Programmiermuster bei Vorlagen zu vereinfachen.  **\(C\+\+14\)**  
  
-   **exchange\(\)** Die Standardbibliothek unterstützt jetzt die Hilfsfunktion "std::exchange\(\)", um einem Objekt einen neuen Wert zuzuweisen und seinen alten Wert zurückzugeben.  Bei komplexen Typen vermeidet "exchange\(\)" das Kopieren des alten Werts, wenn ein Bewegungskonstruktor verfügbar ist, vermeidet das Kopieren des neuen Werts, wenn er temporär ist oder verschoben wird, und nimmt alle Typen als neuen Typ an, wobei beliebige konvertierende Zuweisungsoperatoren genutzt werden.  **\(C\+\+14\)**  
  
-   **"equal\(\)", "is\_permutation\(\)", "mismatch\(\)" mit zwei Bereichen** Die Standardbibliothek unterstützt jetzt Überladungen für "std::equal\(\)", "std::is\_permutation\(\)" und "std::mismatch\(\)", die zwei Bereiche akzeptieren.  Diese Überladungen überprüfen, ob die beiden Sequenzen die gleiche Länge aufweisen, wodurch dies nicht mehr in die Zuständigkeit des aufrufenden Codes fällt; bei Sequenzen, die die Anforderungen eines wahlfreien Iterators nicht unterstützen, überprüfen diese Überladungen die Länge während des Elementvergleichs, was effizienter ist.  **\(C\+\+14\)**  
  
-   **get\<T\>\(\)** Die Standardbibliothek unterstützt jetzt die Vorlagenfunktion "get\<T\>\(\)", um die Adressierung von Tupelelementen anhand ihres Typs zu ermöglichen.  Wenn ein Tupel zwei oder mehr Elemente des gleichen Typs enthält, kann "get\<T\>\(\)" für das Tupel nicht anhand dieses Typs adressiert werden, andere Elemente mit eindeutigem Typ können aber trotzdem adressiert werden.  **\(C\+\+14\)**  
  
-   **tuple\_element\_t** Die Standardbibliothek unterstützt jetzt den Typalias "tuple\_element\_t\<I, T\>", der einen Alias für den Typnamen "tuple\_element\<I, T\>::type" darstellt.  Dies stellt eine gewisse Vereinfachung für Vorlagenprogrammierer dar, ähnlich den anderen Typaliasen für Metafunktionen in \<type\_traits\>.  **\(C\+\+14\)**  
  
-   **Technische Dateisystemspezifikation "V3"** Die enthaltene Implementierung der technischen Dateisystemspezifikation wurde auf Version 3 der Spezifikation aktualisiert.  \[N3940\]  
  
-   **Minimale Zuweisungen** Die Standardbibliothek unterstützt jetzt durchgängig die Schnittstelle für minimale Zuweisungen; erwähnenswerte Verbesserungen umfassen die Funktionen "std::function", "shared\_ptr", "allocate\_shared\(\)" und "basic\_string".  **\(C\+\+11\)**  
  
-   **\<chrono\>** Die chrono\-Typen "high\_resolution\_clock" und "steady\_clock" wurden repariert.  **\(C\+\+11\)**  
  
-   **N2761 Atomics in Signalhandlern \(C\+\+11\)**  
  
-   **N3922 Neue Regeln für „auto“ mit „braced\-init\-lists“. \(C\+\+17\)**  
  
-   **N4051 „typename“ in Vorlagen und Vorlagenparametern \(C\+\+17\)**  
  
-   **N4259 std::uncaught\_exceptions\(\)**  
  
-   **N4266 Attribute für Namespaces und Enumeratoren**  
  
-   **N4267 u8\-Zeichenliterale**  
  
###  <a name="BK_CRT"></a> C Runtime Library  
 **CRT\-Bibliothek\-Umgestaltung**. Die CRT wurde in zwei Teilen umgestaltet.  Die **Universal CRT** enthält den Code, der die standardmäßige C Runtime Library implementiert.  Die „vcruntime140.dll“ \(oder .lib\) enthält versionsspezifischen Code für die Prozessstart\- und Ausnahmenverarbeitung.  Universal CRT hat eine stabile API und kann somit verwendet werden, ohne die Versionsnummer in jeder Visual Studio\-Version ändern zu müssen.  Es handelt sich hierbei nun um eine Windows\-Betriebssystemkomponente, die durch Windows Update unterstützt wird.  Es ist bereits in Windows 10 installiert.  Mithilfe des Visual C\+\+ Redistributable Package \(vcredist\) können Sie es zusammen mit Ihren Anwendungen für frühere Windows\-Versionen bereitstellen.  
  
 **C99\-Konformität**. [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] implementiert die C99\-Standardbibliothek in vollem Umfang, und zwar mit Ausnahme von Bibliotheksfeatures, die von Compilerfeatures abhängig sind, die durch den Visual C\+\+\-Compiler \(beispielsweise ist \<tgmath.h\> nicht implementiert\) zurzeit noch nicht unterstützt werden.  
  
 **Leistung**. Es wurden viele Elemente der Bibliothek umgestaltet, um die Headerdatei\-Makroverwendung zu optimieren bzw. zu vereinfachen.  Dadurch werden die Kompilierung und IntelliSense beschleunigt und die Lesbarkeit verbessert.  Zudem wurden viele „stdio“\-Funktionen zwecks Einhaltung der Standards und verbesserter Leistung umgeschrieben.  
  
### Die Lauffähigkeit der Anwendung beeinträchtigende Änderungen  
 Diese verbesserte Unterstützung für ISO C\-\/C\+\+\-Standards erfordert möglicherweise Änderungen am vorhandenen Code, sodass er C\+\+11 und C99 entspricht und ordnungsgemäß in Visual Studio 2015 kompiliert wird.  Weitere Informationen finden Sie unter [Wichtige Änderungen in Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md).  
  
 Die "concurrency::task"\-Klasse und verwandte Typen in "ppltasks.h" basieren nicht mehr auf der ConcRT\-Laufzeit.  Sie verwenden nun den Windows\-Threadpool als Planer.  Dies wirkt sich nur auf Code aus, der ConcRT\-Synchronisierungsprimitive in "concurrency::task"\-Vorgängen verwendet.  Bei solchem Code sollten stattdessen Windows\-Synchronisierungsprimitive verwendet werden.  
  
 Die Synchronisierungsprimitiven in STL basieren ebenfalls nicht mehr auf ConcRT.  Um Deadlocks zu vermeiden, verwenden Sie keine STL\-Synchronisierungsprimitive innerhalb von Funktionen wie **concurrency::parallel\_for** oder mit asynchronen Agent\-Typen der PPL.  
  
##  <a name="BK_FasterBuildTimes"></a> Schnellere Builds  
  
-   **Inkrementelle Codegenerierung zur Linkzeit \(LTCG, Incremental Link\-Time Code Generation\)** Das inkrementelle Verknüpfen kann jetzt zusammen mit LTCG verwendet werden, um die Linkzeiten von Anwendungen, die LTCG verwenden, zu verkürzen.  Aktivieren Sie dieses Feature mithilfe der Linkerschalter "\/LTCG:incremental" und "\/LTCG:incremental\_rebuild".  \\  
  
-   **Inkrementelles Verknüpfen für statische Bibliotheken** Änderungen an statischen Bibliotheken, die von anderen Codemodulen referenziert werden, werden jetzt inkrementell verknüpft.  
  
-   **\/Debug:FastLink** verkürzt die Linkzeiten durch die Verwendung von neuen PDB\-Erstellungstechniken erheblich.  
  
-   Verbesserungen an den Algorithmen beim Linker bewirken kürzere Linkzeiten.  
  
-   Verbesserungen wurden vorgenommen, die das Erstellen von Code mit vielen Vorlagen beschleunigen.  
  
-   **Schnelle PGO\-Instrumentation \(Profile Guided Optimization\)** Mit PGO wurde ein neuer, schlanker Instrumentationsmodus für Spiele und Echtzeitsysteme eingeführt.  In Verbindung mit anderen neuen Features, die über die Linkerschalter "\/GENPROFILE" und "\/FASTGETPROFILE" verfügbar gemacht werden, können Sie jetzt Codequalität und Buildgeschwindigkeit bei der Verwendung von PGO ausbalancieren.  
  
-   **Verringerte Größe von Objektdateien** Verbesserungen am Compiler und der C\+\+\-Standardbibliothek führen zu erheblich kleineren Objektdateien und statischen Bibliotheken.  Diese Verbesserungen wirken sich nicht auf die Größe von DLLs \(Dynamically\-Linked Libraries\) oder EXEs \(Programmdateien\) aus, da der redundante Code dort bereits in der Vergangenheit durch den Linker entfernt wurde.  
  
##  <a name="BK_PerfCodeQuality"></a> Leistung und Codequalität  
  
-   **Verbesserte automatische Vektorisierung** Schließt jetzt die Vektorisierung der Ablaufsteuerung \(if\-then\-else\), die Vektorisierung beim Kompilieren unter \/O1 \(Größe minimieren\) und Verbesserungen an der Vektorcodequalität insgesamt ein, einschließlich Unterstützung für Parallel STL, Vektorisierung von mehr bereichsbasierten For\-Schleifen und Unterstützung für "\#pragma loop\(ivdep\)".  
  
-   **Verbesserte skalare Optimierung** Bessere Codegenerierung von Bitprüfoperationen, Zusammenführung und Optimierung der Ablaufsteuerung \(loop\-if switching\) und weitere skalare Optimierungen \(z. B. bessere Codegenerierung für "std::min" und "std::max"\).  
  
-   **Profilgesteuerte Optimierung \(PGO\)** Eine Reihe von Verbesserungen wurde an der PGO vorgenommen, einschließlich verbesserter Verweissätze, besserer Möglichkeiten zum Datenlayout und der Fähigkeit, zuvor getroffene Entscheidungen zu Inlining, dem Kompromiss aus Geschwindigkeit und  Größe sowie dem Layout erneut zu verwenden.  
  
##  <a name="BK_IDE"></a> Produktivität, Debuggen und Diagnose  
  
###  <a name="BK_SingleFileIntelliSense"></a> IntelliSense mit Einzeldatei  
 Beim Öffnen einer einzelnen Quellcodedatei im Editor können Sie jetzt IntelliSense nutzen, ohne dass Sie eine Projektdatei öffnen müssen.  
  
###  <a name="BK_Refactoring"></a> Umgestaltung  
 Es wurde Umgestaltungsunterstützung für C\+\+ mit den folgenden Features hinzugefügt:  
  
-   **Symbol umbenennen** Ändert den Namen eines Symbols in allen Vorkommen.  
  
-   **Funktionsextraktion** Verschiebt ausgewählten Code in eine eigene Funktion.  Diese Umgestaltung ist als Erweiterung zu Visual Studio in der Visual Studio Gallery verfügbar.  
  
-   **Implementierung von reinen virtuellen Funktionen** Generiert Funktionsdefinitionen für reine virtuelle Funktionen, die von einer Klasse oder Struktur geerbt wurden.  Mehrfachvererbung und rekursive Vererbung werden unterstützt.  Aktivieren Sie diese Umgestaltung aus der erbenden Klassendefinition, um alle geerbten reinen virtuellen Funktionen zu implementieren, oder aus einem Basisklassenspezifizierer, um nur reine virtuelle Funktionen aus der betreffenden Basisklasse zu implementieren.  
  
-   **Deklaration oder Definition erstellen** Generiert eine Deklaration aus einer vorhandenen Definition oder eine Standardefinition aus einer vorhandenen Deklaration.  Greifen Sie auf diese Umgestaltung aus der vorhandenen Deklaration oder Definition oder über den Glühbirnenindikator zu.  
  
-   **Verschieben der Funktionsdefinition** Verschiebt den Hauptteil einer Funktion zwischen den Quellcode\- und den Headerdateien.  Aktivieren Sie diese Umgestaltung aus der Signatur der Funktion.  
  
-   **Konvertieren in ein Rohzeichenfolgenliteral** Konvertiert eine Zeichenfolge, die Escapesequenzen enthält, in ein Rohzeichenfolgenliteral.  Unterstützte Escapesequenzen sind \\\\ \(umgekehrter Schrägstrich\), \\n \(neue Zeile\), \\t \(Tab\), \\' \(einfaches Anführungszeichen\), \\" \(doppeltes Anführungszeichen\) und \\?  \(Fragezeichen\).  Aktivieren Sie dieses Feature, indem Sie mit der rechten Maustaste an beliebiger Position in einer Zeichenfolge klicken.  
  
 Das Suchen in Dateien wurde verbessert, indem das Anfügen nachfolgender Ergebnisse an vorhergehende Ergebnisse ermöglicht wurde; akkumulierte Ergebnisse können gelöscht werden.  
  
 **Verbesserte Lesbarkeit bei IntelliSense** Komplexe Instanziierungen von Vorlagen und Typdefinitionen wurden in der Parameterhilfe und den QuickInfos vereinfacht, um sie leichter lesbar zu machen.  
  
###  <a name="BK_PDB"></a> Verbesserungen der Programmdatenbank  
  
-   Die Überprüfung von Projektmappen erfolgt jetzt schneller, besonders bei umfangreichen Projektmappen.  
  
-   Vorgänge wie "Gehe zu Definition" sind während der Projektmappenüberprüfung nicht mehr blockiert, mit Ausnahme der ersten Überprüfung der Projektmappe, wenn eine neue Projektmappe zum ersten Mal geöffnet wird.  
  
##  <a name="BK_Diagnostics"></a> Diagnose  
  
1.  **Debuggervisualisierungen** Fügen Sie Ihrem Visual Studio\-Projekt Natvis\-Debuggervisualisierungen hinzu, um Verwaltung und Quellcodeintegration zu erleichtern.  Natvis\-Dateien können während einer Debugsitzung bearbeitet und gespeichert werden, und der Debugger übernimmt die Änderungen automatisch.  Weitere Informationen finden Sie in diesem [Blogbeitrag](http://blogs.msdn.com/b/vcblog/archive/2014/06/12/project-support-for-natvis.aspx).  
  
2.  **Systemeigene Arbeitsspeicherdiagnose**  
  
    1.  **Arbeitsspeicher\-Diagnosesitzungen** \(Strg\+Alt\+F2\) ermöglichen es, während einer Debugsitzung eine Liveüberwachung der Arbeitsspeicherverwendung für Ihre systemeigene Anwendung durchzuführen.  
  
    2.  **Arbeitsspeicher\-Momentaufnahmen** erfassen ein momentanes Bild der Heapinhalte Ihrer Anwendung.  Unterschiede im Heapstatus können durch Vergleich zweier Arbeitsspeicher\-Momentaufnahmen untersucht werden.  Zeigen Sie Objekttypen, Instanzwerte und Zuordnungs\-Aufruflisten für jede Instanz nach dem Beenden der Anwendung an.  Zeigen Sie die Aufrufstruktur pro Stapelrahmen für jede Momentaufnahme an.  
  
3.  **Verbesserte Deadlockerkennung und \-wiederherstellung** beim Aufruf von C\+\+\-Funktionen aus den Fenstern "Überwachen" und "Direkt".  
  
4.  **Verbesserte Compilerdiagnose** Der Compiler gibt verbesserte Warnungen bei verdächtigem Code aus.  Neue Warnungen wurden hinzugefügt \(z. B. Schattenvariablen und nicht passende printf\-Formatzeichenfolgen\).  Die vorhandenen Warnmeldungen wurden klarer formuliert.  
  
5.  **Flag "\/Wv"** Warnungen, die nach einer bestimmten Compilerversion "XX.YY.ZZZZ" eingeführt wurden, können mithilfe des Flags "\/Wv:XX.YY.ZZZZ" deaktiviert werden.  Andere Warnungen können über die im Flag "\/Wv" angegebenen hinaus spezifisch deaktiviert werden.  
  
6.  **Verbesserte Unterstützung für das Debuggen von optimiertem Code** Debuggen Sie Code mit aktivierten Flags "\/Zi", "\/Zo" oder "\/Z7".  
  
##  <a name="BK_Win10"></a> Ausrichtung auf Windows 10  
 Visual Studio unterstützt jetzt die Ausrichtung auf Windows 10 in C\+\+.  Neue Projektvorlagen für die universelle Windows\-App\-Entwicklung unterstützen die Zielgruppenadressierung für Windows 10\-Geräte, wie z. B. Desktop\-PCs, Mobiltelefone, Tablet\-PCs, HoloLens und andere Geräte.  Weitere Informationen finden Sie unter [Erstellen eine „Hello World“\-App in Windows 10](https://msdn.microsoft.com/en-us/library/windows/apps/dn996906.aspx).  
  
##  <a name="BK_GraphicsDiagnostics"></a> Grafikdiagnose  
 Die Grafikdiagnose wurde durch die folgenden Features verbessert:  
  
-   **Grafikdiagnoseunterstützung für DirectX12.** Das Visual Studio\-Grafikdiagnosetool unterstützt nun das Debuggen von Renderingproblemen in DirectX12\-Anwendungen.  
  
-   **Erfassung aufeinanderfolgender Frames** Erfassen Sie mit einer einzelnen Erfassung bis zu 30 aufeinanderfolgende Frames.  
  
-   **Programmgesteuerte Erfassung** Leiten Sie die Erfassung von Frames programmgesteuert ein.  Die programmgesteuerte Erfassung ist insbesondere beim Debuggen von Compute\-Shadern in Programmen nützlich, die "Present" niemals aufrufen, oder in Fällen, in denen ein Renderingproblem manuell schwer zu erfassen ist, aber programmgesteuert aufgrund des Status der App zur Laufzeit vorhergesagt werden kann.  
  
-   **Erweiterte Grafikereignisliste** Eine neue Ansicht "Zeichnen\-Befehle" wurde hinzugefügt, die erfasste Ereignisse und ihren Status in einer nach Zeichnen\-Befehlen geordneten Hierarchie anzeigt.  Zeichnen\-Befehle können erweitert werden, um den Gerätestatus zum Zeitpunkt des Zeichnen\-Befehls anzuzeigen, und Sie können jede Art Status noch weiter erweitern, um die Ereignisse anzuzeigen, auf die der Wert des jeweiligen Status zurückgeht.  
  
-   **Unterstützung für Windows Phone 8.1** Die Grafikdiagnose unterstützt jetzt das Debuggen von Windows Phone 8.1\-Apps im Phone\-Emulator oder auf einem per Tethering angebundenen Smartphone in vollem Umfang.  
  
-   **Grafikframe\-Analyse** Dieses Tool sammelt Leistungsmessungen für erfasste Frames; darüber hinaus führt es eine Reihe vordefinierter Experimente durch, die Einblick darin geben, wie sich die Anwendung verschiedener Texturierungstechniken auf die Leistung auswirken würde.  Die Frame\-Analyse sammelt außerdem Leistungsindikatoren von der Hardware.  
  
-   **Dedizierte Benutzeroberfläche für die Grafikanalyse** Das neue Fenster "Visual Studio\-Grafikanalyse" stellt einen dedizierten Arbeitsbereich für die Analyse von Grafikframes dar.  
  
-   **Shader bearbeiten und anwenden** Stellen Sie die Auswirkungen von Änderungen am Shader\-Code in einem erfassten Protokoll dar, ohne die App erneut auszuführen.  
  
-   Konfigurieren Sie die Erfassungsoptionen unter "Extras" \> "Optionen" \> "Grafikdiagnose".  
  
-   Befehlszeilentool für das Erfassen und Abspielen von Frames.  
  
 Weitere Informationen finden Sie unter [Grafikdiagnose \(Debuggen von DirectX\-Grafiken\)](../Topic/Visual%20Studio%20Graphics%20Diagnostics.md).  
  
##  <a name="BK_GPUUsage"></a> Neues GPU\-Auslastungstool  
 Das GPU\-Auslastungstool in Visual Studio 2015 kann verwendet werden, um die GPU\-Nutzung durch DirectX\-Anwendungen nachvollziehen zu können.  Diagramme zu Framezeit, Framerate und GPU\-Auslastung sind live während der Ausführung der Anwendungen verfügbar.  Darüber hinaus kann dieses Tool durch die Erfassung und Analyse detaillierter GPU\-Nutzungsdaten Einblicke in die Ausführungszeit einzelner DirectX\-Ereignisse in CPU und GPU liefern und so helfen zu bestimmen, ob die CPU oder die GPU die Ursache eines Leistungsengpasses darstellt.  Siehe [GPU\-Nutzung](../Topic/GPU%20Usage.md).  
  
##  <a name="BK_MFC"></a> Neue MFC\-Features  
 Sie können jetzt angeben, wie Steuerelemente automatisch die Größe anpassen und sich bewegen, wenn ein Benutzer die Größe eines Dialogfelds ändert.  Weitere Informationen finden Sie unter [Dynamisches Layout](../mfc/dynamic-layout.md).  
  
## Siehe auch  
 [Neues in Visual Studio 2015](../Topic/What's%20New%20in%20Visual%20Studio%202015.md)   
 [Visual C\+\+\-Teamblog](http://blogs.msdn.com/b/vcblog/)