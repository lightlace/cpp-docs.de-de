---
title: Compilerwarnungen nach Compilerversion
ms.date: 10/24/2018
helpviewer_keywords:
- warnings, by compiler version
- cl.exe compiler, setting warning options
ms.openlocfilehash: 79cf78de865f480530df89c778e9fe432b0bbf33
ms.sourcegitcommit: a901c4acbfc80ca10663d37c09921f04c5b6dd17
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2019
ms.locfileid: "58142525"
---
# <a name="compiler-warnings-by-compiler-version"></a>Compilerwarnungen nach Compilerversion

Der Compiler kann Unterdrücken von Warnungen, die nach der Version eingeführt wurden, geben Sie mit, der [/WV](../../build/reference/compiler-option-warning-level.md) -Compileroption. Diese Option ist nützlich für die Verwaltung von Build-Prozess, wenn Sie eine neue Toolsetversion einführen und vorübergehend neue Warnungen unterdrücken möchten. Diese Option unterdrückt keine neue Fehlermeldungen. Es wird nicht empfohlen, Sie alle neue Warnungen unterdrücken dauerhaft! Es wird empfohlen, immer auf der höchsten regulären Warnstufe Kompilieren __/W4__, und Entfernen der __/WV__ Option so bald wie möglich in Ihrem Build.

Diese Versionen des Compilers eingeführt wurden, neue Warnungen:

| Produkt | Compiler-Versionsnummer |
|-|-|
| Visual C++ 2002 | 13.00.9466 |
| Visual C++ 2003 | 13.10.3077 |
| Visual C++ 2005 | 14.00.50727.762 |
| Visual C++ 2008 | 15.00.21022.08 |
| Visual C++ 2010 | 16.00.40219.01 |
| Visual C++ 2012 | 17.00.51106.1 |
| Visual C++ 2013 | 18.00.21005.1 |
| Visual C++ 2015 RTM | 19.00.23026.0 |
| Visual C++ 2015 Update 1 | 19.00.23506.0 |
| Visual C++ 2015 Update 2 | 19.00.23918.0 |
| Visual C++ 2015 Update 3 | 19.00.24215.1 |
| Visual C++ 2017 RTM | 19.10.25017.0 |
| Visual C++ 2017 Version 15.3 | 19.11.25506.0 |
| Visual C++ 2017, Version 15.5 | 19.12.25830.0 |
| Visual C++ 2017, Version 15.6 | 19.13.26128.0 |
| Visual C++ 2017, Version 15.7 | 19.14.26428.0 |
| Visual C++ 2017, Version 15.8 | 19.15.26726.0 |
| Visual C++ 2017, Version 15.9 | 19.16.26926.0 |
| Visual C++ 2019 RTM | 19.20.27004.0 |

Sie können nur die Nummer der Hauptversion, die Nummern für Haupt- und Nebenversionsnummern oder Hauptversion, Nebenversion, angeben und Buildnummern, um mit der __/WV__ Option. Der Compiler meldet alle Warnungen, die Versionen übereinstimmen, die mit der angegebenen Zahl beginnen und unterdrückt alle Warnungen für Versionen, die größer als die angegebene Anzahl. Z. B. __/Wv:17__ meldet alle Warnungen, eingeführt in oder vor einer beliebigen Version von Visual Studio 2012 und unterdrückt alle Warnungen, die von einem beliebigen-Compiler von Visual Studio 2013 (Version 18) oder höher eingeführt. Unterdrückt eingeführte Warnungen in Visual Studio 2015 update 2 und höher können Sie __/Wv:19.00.23506__. Verwendung __/Wv:19.11__ melden, alle Warnungen in einer beliebigen Version von Visual Studio vor Visual Studio 2017 Version 15.5 eingeführt, aber unterdrückt Warnungen, die in Visual Studio 2017 Version 15.5 und höher eingeführt wurden.

Den folgenden Abschnitten werden der Warnungen eingeführt, die von jeder Version von Visual C++, die Sie mithilfe von unterdrücken, können die __/WV__ -Compileroption. Die __/WV__ Option keine Unterdrückung von Warnungen, die nicht aufgelistet werden, die die angegebenen Versionen des Compilers sind älter als.

::: moniker range=">= vs-2019"

## <a name="warnings-introduced-in-visual-c-2019-rc-compiler-version-1920270040"></a>Warnungen, die in Visual C++ 2019 RC (Ressourcencompiler Version 19.20.27004.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.15__.

|||
|-|-|
C4848 | Unterstützung für das Standardattribut "keine\_eindeutige\_Adresse in C ++ 17 und früheren Versionen ist eine Erweiterung des Herstellers

::: moniker-end
::: moniker range=">= vs-2017"


## <a name="warnings-introduced-in-visual-c-2017-version-158-compiler-version-1915267260"></a>Warnungen, die in Visual C++ 2017, Version 15.8 (Compilerversion 19.15.26726.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.14__.

|||
|-|-|
C4643 | Deklarieren von Vorwärts "*Bezeichner*' im Namespace std ist nicht vom C++-Standard zulässig.
C4644 | Verwendung des Musters Offsetof-Makro-basierte in Konstanten Ausdrücken ist nicht dem standard. Verwenden von "offsetof" in der C++-Standardbibliothek definiert sind, stattdessen
C4845 | "\_\_" declspec "(keine\_Init\_alle)" wird ignoriert, wenn "/ d1initall\[0\|1\|2\|3]" wurde in der Befehlszeile nicht angegeben
C4846 | "*Wert*' ist kein gültiges Argument für ' / d1initall': befehlszeilenflag ignoriert
C4847 | "\_\_" declspec "(keine\_Init\_alle)" kann nur eine Funktion, einen Klassentyp oder eine lokale Variable angewendet werden: ignoriert
C4866 | Erzwingen Compiler möglicherweise nicht die Reihenfolge der Auswertung von links nach rechts für den Aufruf von "*Funktion*"
C5046 | "*Funktion*": Im Zusammenhang mit sprachsymboltyps mit interner Verknüpfung nicht definiert
C5047 | Verwenden der nicht dem Standard entsprechende \_ \_Wenn\_mit Modulen vorhanden ist wird nicht unterstützt
C5048 | Verwendung des Makros "*Macroname*" möglicherweise nicht deterministische Ausgabe
C5049 | "*Zeichenfolge*": Einbetten von einen vollständigen Pfad kann abhängig vom Computer-Ausgabe führen.
C5050 | Mögliche nicht kompatible Umgebung beim Importieren des Moduls "*Module_name*': *Problem*
C5100 | \_\_VA\_ARGS\_ \_ ist reserviert für die Verwendung in Variadic-Makros
C5101 | Verwendung von-präprozessoranweisung in der Argumentliste funktionsähnliches Makro ist nicht definiertes Verhalten
C5102 | Ungültige Befehlszeile Makrodefinition ignorieren "*Wert*"
C5103 | Einfügen von "*ttoken1*'und'*token2*" führt nicht zu der ein gültiges Token für die vorverarbeitung
C5104 | gefunden "*string1*#*Zeichenfolge2*"in der Liste ersetzt Makro Meinten Sie"*string1*" "#*Zeichenfolge2*"?
C5105 | Erzeugen von "Definition" makroerweiterung besitzt ein nicht definiertes Verhalten
C5106 | Makros, die mit verschiedenen Namen neu definiert
C5107 | Fehlende beenden "*Char*' Zeichen

## <a name="warnings-introduced-in-visual-c-2017-version-157-compiler-version-1914264280"></a>Warnungen, die in Visual C++ 2017 Version 15.7 (Compilerversion 19.14.26428.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.13__.

|||
|-|-|
C4642|"*Problem*': konnte nicht importiert werden die Einschränkungen für den generischen Parameter '*Parameter*"
C5045|Compilerfehler fügt Spectre-Entschärfung, Auslastung des Arbeitsspeichers angegeben, wenn "/ qspectre" wechseln

## <a name="warnings-introduced-in-visual-c-2017-version-156-compiler-version-1913261280"></a>Warnungen, die in Visual C++ 2017 Version 15.6 (Compilerversion 19.13.26128.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.12__.

|||
|-|-|
C5044|Ein Argument für die Befehlszeilenoption *Option* zeigt auf einen Pfad "*Pfad*' nicht vorhanden

## <a name="warnings-introduced-in-visual-c-2017-version-155-compiler-version-1912258300"></a>Warnungen, die in Visual C++ 2017 Version 15.5 (Compilerversion 19.12.25830.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.11__.

|||
|-|-|
C4843|'*type1*': Ein Ausnahmehandler des Verweises zum Array oder Funktionstypen ist nicht erreichbar ist, verwenden Sie '*Typ2*"stattdessen
C4844|"export Module *Module_name*;" ist jetzt die bevorzugte Syntax zum Deklarieren einer Modulschnittstelle
C5039|"*Funktion*': Zeiger oder Verweis auf die möglicherweise auslösende Funktion übergeben" extern "C-Funktion unter - EHc übergeben. Nicht definiertes Verhalten kann auftreten, wenn diese Funktion eine Ausnahme auslöst.
C5040|Dynamische Ausnahmespezifikationen gelten nur in C ++ 14 und früher; zum Behandeln von als noexcept(false) zurückgibt
C5041|"*Definition*': Out-of-Line-Definition für statischen Constexpr-Datenmember ist nicht erforderlich, und ist in C ++ 17 veraltet
C5042|"*Deklaration*": Funktionsdeklarationen im Blockbereich können nicht "Inline" angegeben werden, in Standard-c++, entfernen Sie 'Inline'-Spezifizierer
C5043|"*Spezifikation*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein

## <a name="warnings-introduced-in-visual-c-2017-version-153-compiler-version-1911255060"></a>Warnungen, die in Visual C++ 2017 Version 15.3 (Compilerversion 19.11.25506.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.10__.

|||
|-|-|
C4597|ein nicht definiertes Verhalten: *Beschreibung*
C4604|"*Typ*': Übergabe eines Arguments nach Wert zwischen nativen und verwalteten Grenze erfordert einen gültigen Kopierkonstruktor. Andernfalls ist das Laufzeitverhalten nicht definiert
C4749|bedingt unterstützt: *Beschreibung*
C4768|__declspec-Attribute vor Verknüpfungsspezifikation werden ignoriert.
C4834|der Rückgabewert der Funktion mit dem Attribut "Nodiscard" wird verworfen.
C4841|nicht standardmäßige Erweiterung verwendet: *Erweiterung*
C4842|Das Ergebnis von 'Offsetof' wird auf einen Typ mit mehrfacher Vererbung ist nicht garantiert konsistent Compiler-Versionen
C4869|"Nodiscard" kann nur auf Klassen, Enumerationen und Funktionen mit nicht leerem Rückgabetyp angewendet werden
C5033|"*Speicherklassen-*' ist nicht mehr unterstützte Speicherklasse
C5034|Verwenden der systeminternen "*systeminterne*' bewirkt, dass Funktion *Funktion* als gastcode kompiliert.
C5035|Verwenden des Features "*Feature*' bewirkt, dass Funktion *Funktion* als gastcode kompiliert.
C5036|VarArgs-Funktion zeigerkonvertierung beim Kompilieren mit/Hybrid: x86arm64 "*type1*'to'*Typ2*"
C5037|"*Memberfunktion*': eine Out-of-Line-Definition eines Members einer Klassenvorlage kann keine Standardargumente
C5038|Datenmember "*member1*"wird nach Datenmember initialisiert werden"*member2*"

## <a name="warnings-introduced-in-visual-c-2017-rtm-compiler-version-1910250170"></a>Warnungen, die in Visual C++ 2017 RTM (Compilerversion 19.10.25017.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00__.

|||
|-|-|
C4468|"Fallthrough": Attribut muss von einer Case-Bezeichnung oder eine standardbezeichnung folgen
C4698|"*Feature*" ist für die Bewertung nur zu Evaluierungszwecken nutzen und unterliegt in künftigen updates oder entfernt.
C4839|nicht standardmäßige Verwendung der Klasse*Klasse*"als Argument an eine Variadic-Funktion
C4840|nicht Portable Verwendung der Klasse*Klasse*"als Argument an eine Variadic-Funktion

::: moniker-end

## <a name="warnings-introduced-in-visual-c-2015-update-3-compiler-version-1900242151"></a>Warnungen, die in Visual C++ 2015 Update 3 (Compilerversion 19.00.24215.1) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00.23918__.

|||
|-|-|
C4467|Verwendung von ATL-Attributen ist veraltet.
C4596|"*Namen*": Unzulässiger vollständig angegebener Name in Elementdeklaration
C4598|' #include \< *Header*\>': headernummer *Anzahl* in die *Quelle* entspricht nicht *Quelle* an Position
C4599|"*Argument*': *Quelle* Argumentnummer *Anzahl* entspricht nicht *Quelle*

## <a name="warnings-introduced-in-visual-c-2015-update-2-compiler-version-1900239180"></a>Warnungen, die in Visual C++ 2015 Update 2 (Compilerversion 19.00.23918.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00.23506__.

|||
|-|-|
C4466|Die heapauslassung der Coroutine konnte nicht ausgeführt werden.
C4595|"*Klasse*': nicht-memberoperators oder Delete-Funktionen dürfen nicht Inline deklariert werden
C4828|Die Datei enthält ein Zeichen, beginnend am Offset 0 X*Wert* , die in der aktuellen quellzeichensatz nicht zulässig ist (Codepage *Anzahl*).
C4868|Compilerfehler kann Auswertungsreihenfolge von links nach rechts in der Initialisiererliste nicht erzwungen werden.

## <a name="warnings-introduced-in-visual-c-2015-update-1-compiler-version-1900235060"></a>Warnungen, die in Visual C++ 2015 Update 1 (Compilerversion 19.00.23506.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00.23026__.

|||
|-|-|
C4426|die optimierungskennzeichnungen wurden nach dem einschließen des Headers, möglicherweise aufgrund von #pragma optimize() geändert
C4654|Einschließen von Code, die vor platziert der vorkompilierten Headerdatei wird, wird ignoriert. Fügen Sie dem vorkompilierten Header Code hinzu.
C5031|#pragma warning"(POP): wahrscheinlich fehlzuordnung, POP-Warnstatus in anderen Datei mithilfe von Push übertragen
C5032|detected #pragma warning(push) with no corresponding #pragma warning(pop)

## <a name="warnings-introduced-in-visual-c-2015-rtm-compiler-version-1900230260"></a>Warnungen, die in Visual C++ 2015 RTM (Compilerversion 19.00.23026.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:18__.

|||
|-|-|
C4427|"*Fehler*": Überlauf in konstantendivision, nicht definiertes Verhalten
C4438|"*Typ*": kann nicht problemlos aufgerufen werden, im / await: Clrcompat-Modus. Wenn "*Typ*" Aufrufe in die CLR, die sie möglicherweise CLR-Beschädigung
C4455|' Operator *Namen*": LiteralSuffix-Bezeichnern, die nicht mit einem Unterstrich beginnen sind reserviert.
C4456|Deklaration von "*Namen*" Blendet vorherige lokale Deklaration
C4457|Deklaration von "*Namen*" Blendet Funktionsparameter aus
C4458|Deklaration von "*Namen*" Blendet Klassenmember
C4459|Deklaration von "*Namen*" Blendet globale Deklaration
C4462|"*Typ*': die GUID des Typs kann nicht bestimmt werden. Das Programm kann zur Laufzeit fehlschlagen.
C4463|Überlauf; Zuweisen von *Wert* zu Bit-Feld, das nur Werte enthalten kann *Wert* zu *Wert*
C4473|"*Funktion*': nicht genügend Argumente für Formatzeichenfolge übergeben
C4474|"*Funktion*": zu viele Argumente für Formatzeichenfolge übergeben
C4475|"*Funktion*': längenmodifizierers"*Modifizierer*"kann nicht mit dem typfeldzeichen verwendet werden"*Zeichen*"im Formatbezeichner
C4476|"*Funktion*": Unbekanntes typfeldzeichen "*Zeichen*" im Formatbezeichner
C4477|"*Funktion*": Formatzeichenfolge "*Zeichenfolge*"erfordert ein Argument vom Typ"*Typ*", aber Variadic-Argument *Anzahl* weist den Typ "*Typ*"
C4478|"*Funktion*": Platzhalter mit Feldern fester Breite und nicht mit Feldern fester Breite können nicht in der gleichen Formatzeichenfolge kombiniert werden
C4494|"*Typ*": __Declspec(allocator) wird ignoriert, da der Funktionsrückgabetyp ist kein Zeiger oder Verweis
C4495|nicht dem Standard entsprechende Erweiterung "__super": Ersetzen Sie dies durch explizite Basisklassennamen
C4496|nicht dem Standard entsprechende Erweiterung 'for each' verwendet: Ersetzen Sie dies durch die bereichsbasierte for-Anweisung
C4497|nicht dem Standard entsprechende Erweiterung'sealed' verwendet: durch 'Final' ersetzen
C4498|nicht dem Standard entsprechende Erweiterung: "*Erweiterung*"
C4499|"*Spezialisierung*': eine explizite Spezialisierung keine Speicherklasse (ignoriert)
C4576|ein von einer Initialisiererliste in Klammern gesetzte Typ ist eine nicht standardmäßige explizite Typkonvertierungssyntax
C4577|"Noexcept" mit ohne angegebenen ausnahmebehandlungsmodus verwendet; Beendigung bei einer Ausnahme ist nicht garantiert. Geben Sie/EHsc
C4578|"abs": Konvertierung von '*Typ*'to'*Typ*", möglicher Datenverlust (wollten Sie rufen"*Namen*' oder #include \<Cmath >?)
C4582|"*Typ*": Konstruktor wird nicht implizit aufgerufen.
C4583|"*Typ*": Destruktor wird nicht implizit aufgerufen.
C4587|"*Typ*": verhaltensänderung: Konstruktor wird nicht mehr implizit aufgerufen.
C4588|"*Typ*": verhaltensänderung: Destruktor wird nicht mehr implizit aufgerufen.
C4589|Der Konstruktor der abstrakten Klasse*Typ*"ignoriert den Initialisierer für die virtuelle Basisklasse"*Typ*"
C4591|"Constexpr" Aufruftiefe Grenzwert von *Anzahl* überschritten (/-aufruftiefenlimit\<Anzahl >)
C4592|"*Typ*": Symbol wird dynamisch initialisiert (implementierungseinschränkung)
C4593|"*Typ*": "Constexpr" Aufruf Auswertung Schritt maximal *Wert* überschritten; verwenden Sie/constexpr: Steps\<Anzahl > um das Limit erhöhen
C4647|Verändertes Programmverhalten: __is_pod (*Typ*) verfügt über unterschiedliche Wert in früheren Versionen
C4648|das Standardattribut "Carries_dependency" wird ignoriert.
C4649|Attribute werden in diesem Kontext ignoriert.
C4753|Grenzen für den Zeiger wurde nicht gefunden. Systeminterne MPX-Funktion ignoriert
C4771|Grenzen müssen mit einem einfachen Zeiger erstellt werden. Systeminterne MPX-Funktion ignoriert
C4774|"*Beschreibung*": im Argument erwartet Formatzeichenfolge *Anzahl* ist kein Zeichenfolgenliteral
C4775|in Formatzeichenfolge nicht dem Standard entsprechende Erweiterung '*Zeichenfolge*"von Funktion'*Funktion*"
C4776|"%*Zeichen*"ist nicht zulässig in der Formatzeichenfolge der Funktion"*Funktion*"
C4777|"*Beschreibung*": Formatzeichenfolge "*Zeichenfolge*"erfordert ein Argument vom Typ"*Typ*", aber Variadic-Argument *Anzahl* weist den Typ "*Typ*"
C4778|"*Beschreibung*': nicht abgeschlossene Formatzeichenfolge"*Zeichenfolge*"
C4838|Konvertierung von '*Typ*'to'*Typ*"erfordert eine einschränkende Konvertierung
C5022|"*Typ*": mehrere bewegungskonstruktoren angegeben
C5023|"*Typ*": mehrere bewegungszuweisungsoperatoren angegeben
C5024|"*Deklaration*": Konstruktor wurde implizit als gelöscht definiert.
C5025|"*Deklaration*': Verschieben der Zuweisungsoperator wurde implizit als gelöscht definiert.
C5026|"*Typ*": Konstruktor wurde implizit als gelöscht definiert.
C5027|"*Typ*': Verschieben der Zuweisungsoperator wurde implizit als gelöscht definiert.
C5028|"*Namen*": In vorheriger Deklaration angegebene Ausrichtung (*Anzahl*) nicht in Definition angegeben.
C5029|nicht dem Standard entsprechende Erweiterung: Ausrichtungsattribute in C++, die auf Variablen, Datenmember und Tagtypen nur anwenden
C5030|Attribut "*Attribut*" wird nicht erkannt.

## <a name="warnings-introduced-in-visual-c-2013-compiler-version-1800210051"></a>Warnungen, die in Visual C++ 2013 (Compilerversion 18.00.21005.1) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:17__.

|||
|-|-|
C4301|"*Typ*": Überschreiben der virtuellen Funktion nur unterscheidet sich von "*Deklaration*' durch Const/Volatile-Qualifizierer
C4316|"*Typ*': auf dem Heap zugeordnete Objekt möglicherweise nicht ausgerichtet werden *Anzahl*
C4380|"*Typ*": Ein Standardkonstruktor kann nicht als veraltet markiert
C4388|"*token*': signed/unsigned-Konflikt
C4423|"Std:: bad_alloc": wird von Klasse abgefangen ("*Typ*") in Zeile *Anzahl*
C4424|"catch für" "*Typ*"vorangestellt"*Typ*" in Zeile *Anzahl*; unvorhersehbaren Verhalten führen kann, wenn "Std:: bad_alloc" ausgelöst wird
C4425|Eine SAL-Anmerkung kann nicht angewendet werden, auf "..."
C4464|Relative Includepfad enthält '..'
C4575|"__vectorcall" nicht kompatibel mit der "/ Clr" Option: Konvertierung nach "__stdcall"erfolgt.
C4609|"*Typ*"abgeleitet von Standardschnittstelle"*Typ*'für Typ"*Typ*". Verwenden Sie eine andere Standardschnittstelle für "*Typ*", oder unterteilen Sie die basisbeziehung/abgeleitete Beziehung.
C4754|Konvertierungsregeln für arithmetische Operationen im Vergleich bei *Beschreibung*(*Anzahl*) bedeutet, dass eine Verzweigung nicht ausgeführt werden. CAST '*Typ*'to'*Typ*"(oder einem ähnlichen Typ von *Anzahl* Bytes).
C4755|Konvertierungsregeln für arithmetische Operationen im Vergleich bei *Beschreibung*(*Anzahl*) bedeutet, dass eine Verzweigung kann nicht in einer Inline-Funktion ausgeführt werden. CAST '*Typ*'to'*Typ*"(oder einem ähnlichen Typ von *Anzahl* Bytes).
C4767|Name des Abschnitts "*Namen*' ist länger als 8 Zeichen und wird vom Linker abgeschnitten
C4770|teilweise validierte Enumeration "*Namen*" als Index verwendet
C4827|Eine öffentliche "ToString"-Methode mit 0 Parametern muss als virtuell markiert werden, und überschreiben
C4882|Übergeben von functor-Objekten mit nicht Konstanten aufrufoperatoren an Concurrency:: parallel_for_each ist veraltet.
C4973|"*Typ*': als veraltet markiert
C4974|"*Typ*': als veraltet markiert
C4981|Warbird: Funktion "*Deklaration*" als __forceinline markierte nicht inline, da sie Ausnahmesemantik enthält
C4990|Warbird: *Nachricht*
C4991|Warbird: Funktion "*Deklaration*" als __forceinline markierte nicht inline da Schutzstufe des Inlinees größer als das übergeordnete Element ist
C4992|Warbird: Funktion "*Deklaration*" als __forceinline markierte nicht inline, da es sich um Inlineassembly enthält, die nicht geschützt werden können

## <a name="warnings-introduced-in-visual-c-2012-compiler-version-1700511061"></a>Warnungen, die in Visual C++ 2012 (Compilerversion "17.00.51106.1") eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:16__.

|||
|-|-|
C4330|Attribut "*Attribut*"für Abschnitt"*Abschnitt*" ignoriert
C4415|duplicate __declspec(code_seg('*name*'))
C4416|__declspec(code_seg(...)) enthält eine leere Zeichenfolge: ignoriert
C4417|eine explizite Vorlageninstanziierung darf nicht __declspec(code_seg(...)): ignoriert
C4418|__declspec(code_seg(...)) in einer Enumeration ignoriert
C4419|"*Namen*"hat keine Auswirkungen, die bei Anwendung auf private Verweisklasse"*Typ*".
C4435|"*Typ*": Das Objektlayout unter "/ vd2" ändert sich aufgrund der virtuellen Basis '*Typ*"
C4436|Dynamic_cast von virtueller Basis '*Typ*'to'*Typ*' konnte im Konstruktor oder Destruktor mit teilweise konstruierten Objekt fehl
C4437|Dynamic_cast von virtueller Basis '*Typ*'to'*Typ*' kann in einigen Kontexten fehl
C4443|Erwarteter Pragma-Parameter '0', '1' oder '2' sein
C4446|"*Typ*": Member können nicht zugeordnet werden kann '*Namen*"in diesem Typ aufgrund eines Konflikts mit dem Typnamen. Die Methode wurde umbenannt in "*Namen*"
C4447|"main"-Signatur wurde ohne Threadmodell gefunden. Beachten Sie, mithilfe von "Int main (Platform:: Array\<Platform:: String ^ > ^ Args)".
C4448|"*Typ*" verfügt nicht über eine Standardschnittstelle, die in den Metadaten angegeben. Auswählen: "*Typ*", die zur Laufzeit fehlschlagen.
C4449|"*Typ*' nicht versiegelter Typ als"[WebHostHidden]"gekennzeichnet werden soll
C4450|"*Typ*"als gekennzeichnet werden soll "[WebHostHidden]", weil sie abgeleitet"*Typ*"
C4451|"*Typ*": Verwenden der Verweisklasse*Typ*"innerhalb dieser Kontext kann zu ungültigem Marshalling des Objekts in Kontexten führen
C4452|"*Typ*': öffentliche Typ kann nicht im globalen Gültigkeitsbereich sein. Er muss in einem Namespace sein, die ein untergeordnetes Element des Namens der winmd-Ausgabedatei ist.
C4453|"*Typ*": Ein "[WebHostHidden]" sollte nicht verwendet werden, auf der veröffentlichten Oberfläche eines öffentlichen Typs, der nicht "[WebHostHidden]"
C4454|"*Typ*" wird von mehr als die Anzahl der Eingabeparameter überladen, ohne dass [DefaultOverload] angegeben. Auswahl "*Deklaration*" als standardüberladung
C4471|"*Namen*': eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung müssen einen zugrunde liegenden Typ (Int wird angenommen)
C4472|"*Namen*" ist eine systemeigene Enumeration: Fügen Sie einen Zugriffsspezifizierer (privat/öffentlich), um eine verwaltete/WinRT-Enumeration zu deklarieren.
C4492|"*Typ*': Übereinstimmungen Basismethode der Verweisklasse"*Typ*", aber nicht"override"markiert ist
C4493|Delete-Ausdruck hat keine Auswirkungen, da der Destruktor von "*Typ*' hat keinen 'öffentlichen' Zugriff
C4585|"*Typ*": Eine WinRT "public Ref Class" muss entweder versiegelt sein oder von einer vorhandenen unversiegelten Klasse abgeleitet werden
C4586|"*Typ*": Ein öffentlicher Typ kann nicht in einem Namespace oberster Ebene namens "Windows" deklariert werden
C4695|#pragma Execution_character_set: "*Argument*' ist kein unterstütztes Argument: derzeit wird nur"UTF-8"wird unterstützt.
C4703|möglicherweise nicht initialisierte lokale Zeigervariable "*Namen*" verwendet
C4728|/ Yl-Option wird ignoriert, da ein PCH-Verweis erforderlich ist.
C4745|flüchtiger Zugriff auf "*Namen*' kann nicht aufgrund ihrer Größe berücksichtigt werden
C4746|flüchtiger Zugriff auf "*Namen*" unterliegt/volatile:\<Iso\|ms > festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen
C4872|eine Gleitkommadivision durch Null festgestellt wird, beim Kompilieren des Aufrufdiagramms für: "*Beschreibung*"
C4880|Das Umwandeln von "*Typ*'to'*Typ*': Umwandeln der Constness einen Zeiger oder Verweis kann zu nicht definiertem Verhalten in einer eingeschränkten Amp-Funktion
C4881|der Konstruktor und/oder der Destruktor wird nicht aufgerufen werden, für die Tile_static-Variable '*Typ*"
C4966|"*Beschreibung*' hat eine __code_seg-Anmerkung mit nicht unterstützten Segmentnamen, Anmerkung wird ignoriert.
C4988|"*Typ*': Variable, die außerhalb von Klassen-/Funktionsbereichs deklariert
C4989|"*Beschreibung*': Typ aufweist, in Konflikt stehende Definitionen.

## <a name="warnings-introduced-in-visual-c-2010-compiler-version-16004021901"></a>Warnungen, die in Visual C++ 2010 (Compilerversion 16.00.40219.01) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:15__.

|||
|-|-|
C4352|"*Namen*": systeminterne Funktion ist bereits definiert
C4573|die Verwendung von "*Typ*" muss der Compiler "this" aber Erfassen der aktuelle standarderfassungsmodus lässt nicht zu
C4574|"*Namen*"ist gemäß Definition "0": wollten Sie verwenden "#if *Namen*"?
C4689|"*Zeichen*': nicht unterstütztes Zeichen in #pragma Detect_mismatch"; "#pragma ignoriert
C4751|/ Arch AVX-Flag gilt nicht für die Intel(R) Streaming SIMD Extensions, die in der Inline-ASM befinden.
C4752|Intel(R) Advanced Vector Extensions; gefunden. Erwägen Sie das entsprechende/Arch AVX-flag
C4837|Trigraph gefunden: "?? *Zeichen*"ersetzt durch"*Zeichen*"
C4986|"*Deklaration*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein
C4987|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw (...)'

## <a name="warnings-introduced-in-visual-c-2008-compiler-version-15002102208"></a>Warnungen, die in Visual C++ 2008 (Compilerversion 15.00.21022.08) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:14__.

|||
|-|-|
C4396|"*Typ*': Der Inlinespezifizierer kann nicht verwendet werden, wenn eine Friend-Deklaration auf die Spezialisierung einer Funktionsvorlage verweist.
C4413|"*Deklaration*': Verweismember wird mit einem temporären, die nicht beibehalten, nach dem Beenden des Konstruktors initialisiert
C4491|"*Beschreibung*": wurde ein ungültiges Format der IDL-Version
C4603|"*Namen*": Makro ist nicht definiert oder die Definition wurde nach Verwendung des vorkompilierten Headers
C4627|"*Beschreibung*": beim Suchen nach Verwendung des vorkompilierten Headers übersprungen
C4750|"*Beschreibung*': Funktion mit" _alloca()"" inline in einer Schleife
C4910|"*Typ*": "__declspec(dllexport)" und "Extern" bei einer expliziten Instanziierung nicht miteinander kompatibel sind
C4985|"*Deklaration*": Attribute sind in vorheriger Deklaration nicht vorhanden.

## <a name="warnings-introduced-in-visual-c-2005-compiler-version-140050727762"></a>Warnungen, die in Visual C++ 2005 (Compilerversion 14.00.50727.762) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:13__.

|||
|-|-|
C4000|Unbekannte Warnung wählen Sie den technischen Supportbefehl im Visual C++-Hilfemenü, oder öffnen die Hilfedatei für technischen Support für Weitere Informationen
C4272|"*Typ*": ist als __declspec(dllimport) markiert; systemeigene Aufrufkonvention muss angegeben werden, beim Importieren einer Funktion.
C4333|"*Ausdruck*': rechtsverschiebung Betrag zu groß, Verlust von Daten
C4334|"*Ausdruck*': Ergebnis der 32-Bit-Verschiebung wird implizit in 64 Bits konvertiert (war 64-Bit-Verschiebung vorgesehen?)
C4335|Mac-Dateiformat ermittelt: Konvertieren Sie die Quelldatei in DOS- oder UNIX-Format
C4342|verhaltensänderung: '*Typ*"aufgerufen wird, jedoch ein Memberoperator aufgerufen wurde, in früheren Versionen
C4350|verhaltensänderung: '*Deklaration*"anstelle des Namens"*Deklaration*"
C4357|ParamArray-Argument gefunden wird, in der formalen Argumentliste für Delegat '*Deklaration*"ignoriert beim Generieren von"*Typ*"
C4358|"*Ausdruck*": Rückgabetyp von kombinierten Delegaten ist nicht "void"; der zurückgegebene Wert ist nicht definiert
C4359|"*Typ*": Ausrichtungsspezifizierer ist kleiner als die tatsächliche Ausrichtung (*Anzahl*), und werden ignoriert.
C4362|"*Typ*': Ausrichtung, die mehr als 8 Bytes wird von der CLR nicht unterstützt
C4364|#using für Assembly using "*Namen*" zuvor gesehen *Beschreibung*(*Anzahl*) ohne As_friend-Attribut; As_friend nicht angewendet
C4365|"*Ausdruck*': Konvertierung von '*Typ*'to'*Typ*", signed/unsigned-Konflikt
C4366|Das Ergebnis der unären '*Operator*"-Operator ist möglicherweise nicht ausgerichtete
C4367|Konvertierung von '*Typ*'to'*Typ*' kann die Ausnahme bei der Datentypausrichtung führen
C4368|kann nicht definiert "*Namen*"als Mitglied der verwaltet werden kann'*Typ*': gemischte Typen werden nicht unterstützt.
C4369|"*Typ*': Enumeratorwert"*Anzahl*"kann nicht als dargestellt werden"*Typ*', Wert ist'*Anzahl*"
C4374|"*Deklaration*": Schnittstellenmethode wird von nicht virtuellen Methode nicht implementiert '*Deklaration*"
C4375|nicht öffentliche Methode "*Deklaration*"überschreibt nicht die"*Deklaration*"
C4376|Zugriffsspezifizierer '*Spezifizierer*: "wird nicht mehr unterstützt: Verwenden Sie '*Spezifizierer*:" stattdessen
C4377|systemeigene Typen sind standardmäßig privat. -d1PrivateNativeTypes ist veraltet.
C4378|Sie benötigen Funktionszeiger zum Ausführen von Initialisierungen; ModuleHandle:: ResolveMethodHandle
C4379|Version *Version* von der common Language Runtime nicht von diesem Compiler unterstützt wird. Mit dieser Version kann zu unerwarteten Ergebnissen führen
C4381|"*Deklaration*": Schnittstellenmethode wird von nicht öffentlichen Methode nicht implementiert '*Deklaration*"
C4382|Auslösen von "*Typ*": ein Typ mit __clrcall-Destruktor oder Kopierkonstruktor kann nur in "/ CLR" abgefangen werden: pure-Modul
C4383|"*Typ*": die Bedeutung der Dereferenzierung eines Handles kann sich ändern, wenn ein benutzerdefinierter Operator '*Operator*' Operator vorhanden ist, Schreiben Sie den Operator als statische Funktion, damit der Operand explizit sein.
C4384|#pragma "*Richtlinie*" sollte nur im globalen Gültigkeitsbereich verwendet werden
C4393|"*Typ*': const hat keine Auswirkungen auf *Beschreibung* Datenmember; ignoriert
C4394|"*Typ*': anwendungsdomänenspezifisches Symbol sollte nicht mit __declspec markiert werden (*Wert*)
C4395|"*Typ*': Memberfunktion wird für eine Kopie des Initonly-Datenmembers aufgerufen werden kann '*Typ*"
C4397|DefaultCharSetAttribute wird ignoriert.
C4398|"*Typ*": Prozessspezifische globale Objekte möglicherweise funktionieren nicht ordnungsgemäß bei mehreren Anwendungsdomänen; verwenden Sie ggf. __declspec(appdomain)
C4399|"*Typ*": Prozessspezifische Symbole sollten nicht gekennzeichnet werden, mit __declspec (*Wert*) bei der Kompilierung mit/clr: pure
C4400|"*Typ*': Const/Volatile-Qualifizierer für diesen Typ werden nicht unterstützt.
C4412|"*Deklaration*': Funktionssignatur enthält Typ '*Typ*'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem bzw. systemeigenem.
C4429|Mögliche unvollständig oder falsch formatiert. Universelle Zeichennamen
C4430|Fehlender Typspezifizierer - int wird angenommen. Hinweis: C++ unterstützt nicht die Standard-int
C4431|Fehlender Typspezifizierer - int wird angenommen. Hinweis: C# unterstützt nicht mehr standardmäßig-int
C4434|ein statischer Konstruktor muss private zugriffsmöglichkeiten aufweisen; in privaten Zugriff geändert
C4439|"*Typ*': Funktionsdefinition mit einem verwalteten Typ in der Signatur muss eine __clrcall-Aufrufkonvention aufweisen
C4441|die Aufrufkonvention von "*Konvention*" ignoriert. "*Konvention*" stattdessen verwendet
C4445|"*Deklaration*': in einem verwalteten/WinRT-Typ kann eine virtuelle Methode kann nicht privat sein
C4460|CLR/WinRT-Operator "*Typ*", verfügt über Parameter als Verweis übergeben wird. CLR/WinRT-Operator "*Operator*"hat eine andere Semantik als C++-Operator"*Operator*', wollten Sie als Wert übergeben?
C4461|"*Typ*': Diese Klasse verfügt über einen Finalizer"! *Typ*", jedoch keinen Destruktor" ~*Typ*"
C4470|zur gleitkommasteuerung ignoriert unter/CLR
C4480|nicht dem Standard entsprechende Erweiterung: Angeben von zugrunde liegenden Typ der Enumeration '*Typ*"
C4481|nicht dem Standard entsprechende Erweiterung: Überschreibungsspezifizierer '*Spezifizierer*"
C4482|nicht dem Standard entsprechende Erweiterung: Enumeration '*Typ*"wird im qualifizierten Namen
C4483|Syntaxfehler: C++-Schlüsselwort erwartet.
C4484|"*Typ*': Übereinstimmungen Basismethode der Verweisklasse"*Typ*", aber nicht"virtual","new"oder"override"; gekennzeichnet ist "new" (und nicht "virtual") wird angenommen.
C4485|"*Typ*': Übereinstimmungen Basismethode der Verweisklasse"*Typ*", ist jedoch nicht markierte 'new' oder 'override'; "new" (und "virtual") werden angenommen.
C4486|"*Typ*': eine private virtuelle Methode einer Verweisklasse oder einer Werteklasse sollte"sealed"markiert werden
C4487|"*Typ*': Übereinstimmungen geerbten nicht virtuellen Methode"*Typ*"jedoch nicht explizit"new"markiert ist
C4488|"*Typ*": erfordert '*Schlüsselwort*"Schlüsselwort zur Implementierung der Schnittstellenmethode"*Typ*"
C4489|"*Schlüsselwort*': für eine Schnittstellenmethode unzulässig"*Namen*"; Override-Bezeichner sind nur für Ref-Klasse und Werteklassenmethoden zulässig
C4490|"*Schlüsselwort*": falsche Verwendung des Überschreibungsspezifizierers; "*Typ*' stimmt nicht mit eine Klassenmethode Basismethode der Verweisklasse überein.
C4538|"*Typ*': Const/Volatile-Qualifizierer für diesen Typ werden nicht unterstützt.
C4559|"*Typ*": Neudefinition; die Funktion Gewinne __declspec (*Wert*)
C4565|"*Typ*": Neudefinition; das Symbol wurde zuvor mit __declspec deklariert (*Wert*)
C4566|universelle Zeichenname dargestellte Zeichen '*Zeichen*' kann nicht in der aktuellen Codepage dargestellt werden (*Anzahl*)
C4568|"*Typ*": keine Elemente mit der Signatur der expliziten Überschreibung überein.
C4569|"*Typ*": keine Elemente mit der Signatur der expliziten Überschreibung überein.
C4570|"*Typ*": ist nicht explizit als abstrakte jedoch abstrakte Funktionen weist deklariert
C4571|Information: catch(...)-Semantik Visual C++ 7.1 geändert; strukturierte Ausnahmen (SEH) werden nicht mehr abgefangen.
C4572|[ParamArray]-Attribut ist unter "/ CLR", und verwenden als veraltet markiert "..." Stattdessen
C4580|[Attribute] ist veraltet. Geben Sie stattdessen *angegebenen*-Attribut als eine Basisklasse
C4581|Veraltetes Verhalten: ""*Namen*"" ersetzt, die mit "*Namen*' zur Verarbeitung des Attributs
C4606|#pragma-Warnung: "*Anzahl*" ignoriert. Codeanalysewarnungen sind keinen Warnstufen zugeordnet
C4631|MSXML oder XPath ist nicht verfügbar. XML-Dokumentkommentare werden nicht verarbeitet. *Beschreibung*
C4632|Der XML-Dokumentkommentar: *Beschreibung* – Zugriff verweigert: *Beschreibung*
C4633|Der XML-Dokumentkommentar *Beschreibung*: Fehler: *Beschreibung*
C4634|Der XML-Dokumentkommentar *Beschreibung*: kann nicht angewendet werden: *Beschreibung*
C4635|Der XML-Dokumentkommentar *Beschreibung*: falsch formatierte XML: *Beschreibung*
C4636|Der XML-Dokumentkommentar *Beschreibung*: Tag erfordert ein nicht leeres "*Beschreibung*' Attribut.
C4637|Der XML-Dokumentkommentar *Beschreibung*: \<enthalten >-Tag wurde verworfen. *Beschreibung*
C4638|Der XML-Dokumentkommentar *Beschreibung*: Verweis auf unbekanntes Symbol '*Beschreibung*".
C4639|MSXML-Fehler: XML-Dokument, das Kommentare nicht verarbeitet werden. *Beschreibung*
C4641|XML-Dokumentkommentar enthält einen mehrdeutigen Querverweis:
C4678|Basisklasse*Deklaration*"ist weniger zugreifbar als"*Namen*"
C4679|"*Beschreibung*': Member konnte nicht importiert
C4687|"*Typ*': eine versiegelte abstrakte Klasse kann keine Schnittstelle implementieren"*Typ*"
C4688|"*Namen*': Einschränkungsliste enthält den privaten Assemblytyp"*Deklaration*"
C4690|\[ Emitidl (Pop)]: mehr POP-als Push-Vorgänge
C4691|"*Typ*': Typ verwiesen wurde erwartet. im nicht referenzierte *Modul* "*Beschreibung*", Typ, der in der aktuellen Übersetzungseinheit, die stattdessen verwendet
C4692|"*Namen*': die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp '*Deklaration*"
C4693|"*Typ*': eine versiegelte abstrakte Klasse kann keine Instanzmember haben*Namen*"
C4694|"*Typ*': eine versiegelte abstrakte Klasse einer Basisklasse sind keine*Typ*"
C4720|Inline-Inlineassembler meldet: "*Beschreibung*"
C4721|"*Beschreibung*': nicht als systeminterne Funktion verfügbar
C4722|"*Beschreibung*": Destruktor gibt nie Werte zurück, mögliche Speicherverluste
C4726|ARM arch4/4 t unterstützt nur "\<Cpsr_f > oder \<Spsr_f >" mit unmittelbarem Wert
C4727|PCH, die mit dem Namen *Namen* mit dem gleichen Zeitstempel finden Sie im *Namen* und *Namen*.  Verwenden zuerst gefundene wird verwendet.
C4729|Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.
C4730|"*Beschreibung*': Kombinieren von _m64 und Gleitkommaausdrücken kann zu fehlerhaftem Code
C4731|"*Beschreibung*': Framezeigerregister"*registrieren*"geändert von Inline-Assemblycode
C4732|systeminterne "*systeminterne*" wird in dieser Architektur nicht unterstützt
C4733|Inline-Asm weist "fs": 0: Handler ist nicht als sicherer Handler registriert.
C4734|Mehr als 64k Debuggen Zeilennummern in einem COFF-Abschnitt "Info"; Beenden Sie die Ausgabe von COFF-Debugzeilennummern für Modul "*Modul*"
C4738|Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust
C4739|Verweis auf die Variable "*Variable*' überschreitet die Speicherplatz
C4740|Flow für oder gegen Inline-Asm-Code werden globale Optimierung unterdrückt.
C4742|"*Variable*"hat eine unterschiedliche Ausrichtung "*Speicherort*'und'*Speicherort*': *Anzahl* und *Anzahl*
C4743|"*Namen*"hat eine unterschiedliche Größe "*Speicherort*'und'*Speicherort*': *Anzahl* und *Anzahl* Bytes
C4744|"*Namen*"hat einen anderen Typ "*Speicherort*'und'*Speicherort*': '*Typ*'und'*Typ*"
C4747|Aufrufen von verwalteten '*Typ*": Verwalteter Code kann nicht unter der Loadersperre, einschließlich des DLL-Einstiegspunkts und Aufrufen von DLL-Einstiegspunkt eingehen ausgeführt werden
C4761|integraler Größenkonflikt im Argument; Konvertierung bereitgestellt.
C4764|Die Ausrichtung von catch-Objekten kann nicht mehr als 16 Bytes betragen.
C4788|"*Bezeichner*": Bezeichner wurde auf gekürzt "*Anzahl*' Zeichen
C4789|Puffer "*Namen*' Größe *Anzahl* Bytes werden überlaufen; *Anzahl* Bytes werden ab Offset geschrieben *Anzahl*
C4801|Rückgabe nach Verweis kann nicht überprüft werden: *Beschreibung*
C4819|Die Datei enthält ein Zeichen, das in der aktuellen Codepage nicht dargestellt werden kann (*Anzahl*). Speichern Sie die Datei im Unicode-Format, um Datenverluste zu verhindern
C4826|Konvertierung von '*Typ*'to'*Typ*' ist signaturerweitert. Dies kann zu unerwartetem Laufzeitverhalten führen.
C4829|Möglicherweise falsche Parameter für Main-Funktion. Betrachten Sie ' Int main (Platform:: Array\<Platform:: String ^ > ^ Argv)'
C4835|"*Typ*': die Initialisierung für exportierte Daten wird nicht ausgeführt werden, bis der ersten Ausführung von verwaltetem Code in die Host-Assembly
C4867|"*Typ*": keine Standardsyntax; verwenden Sie stattdessen '&', um einen Zeiger auf Member zu erstellen.
C4936|__declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.
C4937|"*Namen*'und'*Namen*"sind nicht differenzierbar. als Argumente für"*Option*"
C4938|"*Typ*": Reduction-Gleitkommavariable kann dazu führen, dass inkonsistente Ergebnissen bei/fp: strict oder #pragma fenv_access führen
C4939|#pragma vtordisp ist veraltet und wird in einer der nächsten Versionen von Visual C++ entfernt.
C4947|"*Typ*': als veraltet markiert
C4949|Pragmas "managed" und "unmanaged" sind sinnvoll, nur bei der Kompilierung mit "/ Clr [: Option]"
C4950|"*Typ*': als veraltet markiert
C4955|"*Beschreibung*': Import wird ignoriert; wurde bereits importiert aus"*Quelle*"
C4956|"*Typ*': Dieser Typ kann nicht überprüft werden
C4957|"*Ausdruck*": explizite Umwandlung von '*Typ*'to'*Typ*' kann nicht überprüft werden
C4958|"*Ausdruck*': Zeigerarithmetik kann nicht überprüft werden
C4959|keine nicht verwalteten definieren *Klasse* "*Typ*" in/CLR: safe da Zugriff auf seine Member nicht überprüfbaren Code ausgegeben wird
C4960|"*Beschreibung*' ist zu groß für die profilerstellung
C4961|In wurden keine Profildaten zusammengeführt "*Speicherort*', Profilgesteuerte Optimierungen werden deaktiviert.
C4962|"*Beschreibung*": Profilgesteuerte Optimierungen wurden deaktiviert, da die Optimierungen eine Inkonsistenz zwischen den Profildaten verursacht wurde.
C4963|"*Beschreibung*": keine Profildaten gefunden; verschiedene Compileroptionen wurden im instrumentierten Build verwendet.
C4964|Es wurden keine Optimierungsoptionen angegeben. Informationen zum Unternehmensprofil werden nicht gesammelt werden
C4965|Implizites Boxing mit ganzer Zahl 0.; Verwenden Sie "nullptr" oder eine explizite Umwandlung
C4970|Delegatkonstruktor: Zielobjekt ignoriert, da "*Deklaration*" ist statisch
C4971|Argumentreihenfolge: \<Zielobjekt >, \<Zielfunktion > für Delegatkonstruktor ist veraltet, verwenden Sie \<Zielfunktion >, \<Zielobjekt >
C4972|Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing-Vorgangs als L-Wert kann nicht überprüft werden.

## <a name="warnings-introduced-in-visual-c-2003-compiler-version-13103077"></a>Warnungen, die in Visual C++ 2003 (Compilerversion 13.10.3077) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:13.00.9466__.

|||
|-|-|
C4343|#pragma optimieren (*Beschreibung*, deaktiviert) "/ Og"-Option überschreibt
C4344|verhaltensänderung: Verwendung von expliziten Vorlagenargumenten löste im Aufruf von "*Deklaration*"
C4346|"*Typ*": abhängiger Name ist kein Typ
C4348|"*Deklaration*": Neudefinition des Standardparameters: Parameter *Anzahl*
C4356|"*Typ*": statische Datenmember kann nicht über eine abgeleitete Klasse initialisiert werden
C4408|anonyme *Struktur* wurden keine Datenmember deklariert
C4544|"*Deklaration*': Standardvorlagenargument wird für diese Vorlagendeklaration ignoriert
C4545|Ausdruck vor dem Komma wird als Funktion ausgewertet, der eine Argumentliste fehlt
C4546|Funktionsaufruf vor dem Komma ohne Argumentliste
C4547|"*Ausdruck*': Operator vor dem Komma keine Auswirkungen hat; Operator mit Nebeneffekten erwartet
C4548|Ausdruck vor dem Komma hat keine Auswirkung; es wurde ein Ausdruck mit Nebeneffekt erwartet
C4549|"*Ausdruck*': Operator vor dem Komma hat keine Auswirkungen; wollten Sie"*Ausdruck*"?
C4628|'digraphs' werden mit '-Ze' nicht unterstützt. Zeichenfolge '*Sequenz*"nicht als alternatives Token für interpretiert"*token*"
C4629|wurde verwendet, Zeichensequenz "*Sequenz*"als Token interpretiert."*token*" (Fügen Sie kein Leerzeichen zwischen den beiden Zeichen, ist dies nicht beabsichtigt)
C4671|"*Beschreibung*': der Kopierkonstruktor ist nicht möglich.
C4676|"*Beschreibung*': der Destruktor ist nicht möglich.
C4677|"*Namen*': die Signatur des nicht privaten Members enthält den privaten Assemblytyp"*Deklaration*"
C4686|"*Typ*": mögliche verhaltensänderung, Änderung in der UDT gibt zurück Aufrufkonvention
C4812|Veralteter Deklarationsstil: Verwenden Sie '*Typ*::*Namen*"stattdessen
C4813|"*Typ*': eine Friend-Funktion einer lokalen Klasse muss bereits deklariert
C4821|Um festzustellen, Unicode-Codierungstyp, speichern Sie die Datei mit Signatur (BOM) nicht möglich.
C4822|"*Typ*": Lokale Klassenmemberfunktion keinen Text enthalten.
C4823|"*Typ*": verwendet, die feste Zeigern, die Entladesemantik ist aber nicht aktiviert. Erwägen Sie die Verwendung von/EHa
C4913|Benutzerdefinierter binärer Operator "," ist vorhanden, die Überladung konnte aber alle Operanden nicht konvertieren. Es wurde der standardmäßig enthaltene binäre Operator "," verwendet.
C4948|der Rückgabetyp des '*Deklaration*' stimmt nicht mit dem letzten Parametertyp des entsprechenden Setters überein
C4951|"*Beschreibung*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, funktionsprofildaten werden nicht verwendet
C4952|"*Beschreibung*": keine Profildaten gefunden wird, in der Programmdatenbank '*Beschreibung*"
C4953|Inlinee "*Beschreibung*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, Profildaten werden nicht verwendet
C4954|"*Beschreibung*": keine profilerstellung durchgeführt (enthält Switch-Ausdruck __int64)

## <a name="warnings-introduced-in-visual-c-2002-compiler-version-13009466"></a>Warnungen, die in Visual C++ 2002 (Compilerversion 13.00.9466) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:12__.

|||
|-|-|
C4096|"*Typ*": Schnittstelle ist keine COM-Schnittstelle; wird nicht nach IDL emittiert.
C4097|Erwarteter pragma-Parameter sollte "restore" oder "off" sein
C4165|"HRESULT" wird in "Bool" konvertiert werden sind Sie sicher, dass dies gewünscht ist?
C4183|"*Namen*": Rückgabetyp fehlt; davon ausgegangen, dass eine Memberfunktion, die "Int" zurückgibt
C4199|*Beschreibung*
C4255|"*Namen*': Kein Funktionsprototyp angegeben: '()" zu "(void)" konvertiert
C4256|"*Deklaration*": Konstruktor für die Klasse mit virtuellen Basen besitzt "..."; Aufrufe möglicherweise nicht mit älteren Versionen von Visual C++ kompatibel
C4258|"*Namen*': Definition von der for-Schleife ignoriert; die Definition des umschließenden Gültigkeitsbereich verwendet
C4263|"*Deklaration*': Memberfunktion überschreibt keine virtuelle Memberfunktion einer Basisklasse nicht
C4264|"*Deklaration*": keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar "*Klasse*"; die Funktion wird ausgeblendet
C4265|"*Typ*": Klasse besitzt virtuelle Funktionen, aber der Destruktor ist nicht virtuell Instanzen dieser Klasse möglicherweise nicht korrekt gelöscht werden
C4266|"*Deklaration*": keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar "*Klasse*"; die Funktion wird ausgeblendet
C4267|"*Ausdruck*': Konvertierung von 'Size_t' nach '*Typ*", möglicher Datenverlust
C4274|#ident ignored; see documentation for #pragma comment(exestr, 'string')
C4277|importierte Element "*Typ*::*Namen*" vorhanden ist, als Datenmember und Funktionsmember; Datenmember wird ignoriert
C4278|"*Namen*": Bezeichner in der Typbibliothek "*Beschreibung*' ist bereits ein Makro; benutzen Sie den"Rename"-Qualifizierer
C4279|"*Namen*": Bezeichner in der Typbibliothek "*Beschreibung*" ist ein Schlüsselwort; benutzen Sie den "Rename"-Qualifizierer
C4287|"*Ausdruck*": unsigned/Negative-konstantenkonflikt
C4288|nicht dem Standard entsprechende Erweiterung: "*Namen*': Loop-Steuerelementvariable, die in der for-Schleife deklariert wurde, wird außerhalb des for-Schleifenbereichs; es liegen Konflikte mit der Deklaration im äußeren Gültigkeitsbereich
C4289|nicht dem Standard entsprechende Erweiterung: "*Namen*': Loop-Steuerelementvariable, die in der for-Schleife deklariert wurde, wird außerhalb der for-Schleife-Bereich
C4293|"*Ausdruck*": Umschaltanzahl ist negativ oder zu groß, Verhalten undefiniert
C4295|"*Typ*": Array ist zu klein, um ein abschließendes Nullzeichen einzuschließen
C4296|"*Ausdruck*': Ausdruck ist immer *Wert*
C4297|"*Typ*': Funktion davon ausgegangen, dass keine Ausnahme ausgelöst.
C4298|"*Namen*": Bezeichner in der Typbibliothek "*Beschreibung*' ist bereits ein Makro; umbenennen in" __*Namen*"
C4299|"*Namen*": Bezeichner in der Typbibliothek "*Beschreibung*" ist ein Schlüsselwort; umbenennen in "__*Namen*"
C4302|"*Ausdruck*': Verkürzung von '*Typ*'to'*Typ*"
C4303|*Konvertierung* aus "*Typ*'to'*Typ*" ist veraltet, verwenden Sie Static_cast, __try_cast oder Dynamic_cast
C4314|Erwarteter Pragma-Parameter "32" oder "64" sein.
C4315|"*Typ*": "this"-Zeiger für das Element "*Typ*" möglicherweise nicht ausgerichtet werden *Anzahl* wie vom Konstruktor erwartet
C4318|Übergabe der Konstante Null als Länge an memset
C4319|"*Ausdruck*": Null erweitert "*Typ*'to'*Typ*" größeren
C4321|generiert automatisch eine IID für die Schnittstelle "*Typ*"
C4322|automatische Generierung von CLSID für Klasse*Typ*"
C4323|erneute Verwendung der registrierten CLSID für Klasse*Typ*"
C4324|"*Typ*': Struktur wurde aufgrund der ausrichtungsspezifizierer aufgefüllt.
C4325|Attribute für Standardabschnitt "*Beschreibung*" ignoriert
C4326|der Rückgabetyp des '*Namen*'muss'*Typ*"anstelle von"*Typ*"
C4327|"*Ausdruck*": Dereferenzierungsausrichtung von LHS (*Anzahl*) ist größer als RHS (*Anzahl*)
C4328|"*Beschreibung*": Dereferenzierungsausrichtung des formalen Parameters *Anzahl* (*Anzahl*) ist größer als die tatsächliche argumentausrichtung (*Anzahl*)
C4329|ausrichtungsspezifizierer wird für die Enumeration ignoriert.
C4336|Importieren Sie die übergreifende Typbibliothek "*Bibliothek*"vor dem Importieren von"*Beschreibung*"
C4337|die übergreifende Typbibliothek "*Bibliothek*"in"*Beschreibung*" wird automatisch importiert
C4338|#pragma *Beschreibung*: Abschnitt "standard" '*Abschnitt*"wird verwendet
C4339|"*Typ*": Verwendung eines undefinierten Typs wurde entdeckt. in CLR/WinRT - Metadaten verwenden dieses Typs führt möglicherweise zu einer Laufzeitausnahme
C4353|nicht dem Standard entsprechende Erweiterung: Konstante 0 als Funktionsausdruck.  Verwenden Sie stattdessen die systeminterne '__noop'-Funktion
C4370|"*Deklaration*': Layout der Klasse von einer früheren Version des Compilers aufgrund der besseren Komprimierung geändert hat
C4371|"*Deklaration*': Layout der Klasse möglicherweise von einer früheren Version des Compilers durch bessere Verpackung des Members geändert"*Member*"
C4373|"*Typ*": virtuelle Funktion überschreibt*Deklaration*', frühere Versionen des Compilers nicht überschrieben, wenn der Parameter nur durch Const/Volatile-Qualifizierer Compilerversionen
C4387|"*Beschreibung*": wurde berücksichtigt
C4389|"*Ausdruck*': signed/unsigned-Konflikt
C4391|"*Deklaration*": Falscher Rückgabetyp für systeminterne Funktion, erwartet "*Typ*"
C4392|"*Deklaration*": falsche Anzahl von Argumenten für systeminterne Funktion, erwartet "*Anzahl*' Argumente
C4407|Umwandeln von verschiedenen Zeigern in Memberrepräsentationen, kann Compiler falschen Code generieren
C4420|"*Namen*': Operator nicht verfügbar ist, mithilfe von"*Namen*"stattdessen laufzeitüberprüfung beeinträchtigt werden
C4440|Neudefinition der Aufrufkonvention von "*Beschreibung*'to'*Beschreibung*" ignoriert
C4442|eingebettete null-Terminator im __annotation-Argument.  Wert wird abgeschnitten.
C4444|"*Namen*": Toplevel "__unaligned" ist in diesem Kontext nicht implementiert.
C4526|"*Typ*": statische Memberfunktion kann nicht virtuelle Funktion überschreiben '*Deklaration*"außer Kraft setzen, die ignoriert, virtuelle Funktion ausgeblendet
C4531|C++-Ausnahmebehandlung ist unter Windows CE nicht verfügbar. Verwenden Sie die strukturierte Ausnahmebehandlung
C4532|"*Beschreibung*':-Anweisungsblock Herausspringen *schließlich* -Block weist ein undefiniertes Verhalten während der Abbruchbehandlung
C4533|Initialisierung von "*Deklaration*" wird übersprungen, indem Sie ' Gehe zu *Deklaration*"
C4534|"*Deklaration*' können nicht auf ein Standardkonstruktor für *Klasse* "*Typ*' aufgrund von das Standardargument
C4535|calling _set_se_translator() requires /EHa
C4536|"*Beschreibung*': Typ größer als das Metadatenlimit von"*Anzahl*' Zeichen
C4537|"*Deklaration*': '.' auf nicht-UDT-Typ angewendet wird
C4542|Generieren der zusammengefügten eingefügten Textdatei wird übersprungen, kann nicht geschrieben werden *Typ* Datei: '*Filename*': *Fehler*
C4543|Eingefügten Text wurde vom Attribut "keine\_Injected_text"
C4555|Der Ausdruck hat keine Auswirkungen; Ausdruck mit Nebeneffekten erwartet
C4557|"__assume" enthält den Effekt '*Auswirkung*"
C4558|Wert des Operanden "*Anzahl*"liegt außerhalb des Bereichs"*Anzahl* - *Anzahl*"
C4561|"__fastcall" nicht kompatibel mit der "/ Clr" Option: Konvertierung nach "__stdcall"erfolgt.
C4562|vollständige Funktionen mit Prototyp sind erforderlich, mit der "/ Clr" Option: '()"zu"(void)"konvertiert
C4564|Methode "*Namen*" der *Klasse* "*Typ*"definiert den nicht unterstützten Standardparameter"*Parameter*"
C4584|"*Typ*": Basisklasse*Deklaration*"ist bereits eine Basisklasse von"*Deklaration*"
C4608|Mehrere Member der Union initialisiert: "*Typ*'und'*Typ*"
C4619|#pragma-Warnung: Es gibt keine Warnungsnummer '*Anzahl*"
C4623|"*Typ*": Standardkonstruktor wurde implizit als gelöscht definiert.
C4624|"*Typ*": Destruktor wurde impliziert als gelöscht definiert.
C4625|"*Typ*": Kopierkonstruktor wurde implizit als gelöscht definiert.
C4626|"*Typ*': Zuweisungsoperator wurde implizit als gelöscht definiert.
C4645|mit "Noreturn" deklarierte Funktion weist eine return-Anweisung
C4646|mit "Noreturn" deklarierte Funktion weist nicht-Void-Rückgabetyp
C4659|#pragma "*Beschreibung*": Gebrauch des reservierten Segments "*Namen*' weist ein undefiniertes Verhalten, verwenden Sie #pragma Comment (Linker,...)
C4667|"*Deklaration*": keine Funktionsvorlage definiert, die entspricht der erforderlichen Instanziierung
C4668|"*Namen*"ist nicht definiert als ein Präprozessormakro, und Ersetzen Sie dabei mit "0" für"*Wert*"
C4669|"*Ausdruck*": unsichere Konvertierung: "*Typ*" ist ein Objekt verwaltet/WinRT-Typ
C4674|"*Namen*" sollte als "static" deklariert werden, und genau einen Parameter haben
C4680|"*Typ*': Co-Klasse gibt eine Standardschnittstelle keine
C4681|"*Typ*': Co-Klasse gibt eine Standardschnittstelle, die eine Ereignisquelle ist keine
C4682|"*Typ*': kein direktionales Parameterattribut angegeben, Standardwert [in]
C4683|"*Deklaration*': Ereignisquelle hat einen"Out"-Parameter. Seien Sie vorsichtig, wenn mehrere Ereignishandler eine Hookfunktion erstellen
C4684|"*Beschreibung*": WARNUNG!! Attribut kann zu Ungültiger codegenerierung führen: Verwenden Sie mit Vorsicht
C4685|"> >" erwartet. ">>" wurde beim Verarbeiten der Vorlagenparameter gefunden
C4700|nicht initialisierte lokale Variable "*Namen*" verwendet
C4701|möglicherweise nicht initialisierte lokale Variable "*Namen*" verwendet
C4702|unerreichbarer code
C4711|Funktion "*Namen*" ausgewählt für automatische Inlineerweiterung
C4714|Funktion "*Deklaration*" als __forceinline markierte nicht inline
C4715|"*Funktion*': nicht alle Codepfade geben einen Wert zurück.
C4716|"*Funktion*": muss einen Wert zurückgeben
C4717|"*Funktion*": rekursiv für alle Steuerelementpfade, die Funktion verursacht einen Stapelüberlauf zur Laufzeit
C4718|"*Funktion*': rekursiver Aufruf besitzt keine Nebeneffekte, wird gelöscht
C4719|Doppelte Konstante gefunden wird, wenn Qfast angegeben – verwenden Sie "f" als Suffix mit einfacher Genauigkeit an.
C4723|Mögliche Division durch 0
C4724|Mögliches Modulo durch 0 (Null)
C4725|Anweisung kann auf einigen Pentium-Prozessoren ungenau sein
C4757|Subskript besteht aus einem großen unsignierten Wert, wollten Sie eine negative Konstante?
C4772|#import auf einen Typ aus einer fehlenden Typbibliothek verwiesen; "*Beschreibung*" als Platzhalter verwendet
C4792|Funktion "*Funktion*' deklariert ist, unter Verwendung von Sysimport und auf die verwiesen wird von nativem Code; Importbibliothek ist zum Verknüpfen erforderlich
C4794|Segment der Thread-lokalen Speicher-Variablen "*Namen*"geändert"*Segment*'to'*Segment*"
C4798|für p-Code-Funktion generierte systemeigene Code "*Namen*" mit einem Ausnahmehandler oder Entladesemantik
C4799|Funktion "*Namen*' hat keine EMMS-Anweisung
C4803|"*Deklaration*': Die Raise-Methode verfügt über eine andere Speicherklasse als die des Ereignisses,"*Deklaration*"
C4810|value of pragma pack(show) == *number*
C4811|value of pragma conform(forScope, show) == *value*
C4820|"*Typ*': '*Anzahl*' Bytes Abstand hinzugefügt werden, nachdem *Typ* "*Typ*"
C4905|Breites Zeichenfolgenliteral umgewandelt zu "*Typ*"
C4906|Zeichenfolgenliteral umgewandelt zu "*Typ*"
C4912|"*Attribut*": Attribut wurde ein nicht definiertes Verhalten für ein geschachteltes UDT
C4916|Um einen Dispid "*Typ*": muss eine Schnittstelle eingeführt werden
C4917|"*Typ*': eine GUID kann nur eine Klasse, Schnittstelle oder Namespace zugeordnet werden
C4918|"*Zeichen*": Ungültiges Zeichen in der Pragma-Optimierungsliste
C4920|Enum *Namen* Member *Namen*=*Anzahl* bereits in %s *Namen* als *Namen* = *Anzahl*
C4921|"*Namen*": Attribut '*Wert*' sollte nicht mehrfach angegeben werden
C4925|"*Deklaration*": Dispinterface-Methode kann nicht von einem Skript aufgerufen werden
C4926|"*Deklaration*": Symbol ist bereits definiert: Attribute werden ignoriert
C4927|Unzulässige Konvertierung. mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen.
C4928|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen
C4929|"*Beschreibung*': Typbibliothek enthält eine Union; der Embedded_idl-Qualifizierer wird ignoriert.
C4930|"*Deklaration*': Funktion mit Prototyp nicht aufgerufen (war eine Variablendefinition gemeint?)
C4931|Es wird angenommen, die Typbibliothek erstellt wurde, für die *Anzahl*-bit-Zeiger
C4932|__identifier (*Beschreibung*) und __identifier (*Beschreibung*) sind nicht differenzierbar.
C4934|"__delegate(multicast)" ist veraltet, verwenden Sie "__delegate"
C4935|Assembly-Zugriffsspezifizierer wurde von geändert "*Beschreibung*"
C4944|"*Namen*": Symbol aus kann nicht importiert "*Quelle*': unter*Deklaration*' ist im aktuellen Bereich bereits vorhanden.
C4945|"*Namen*": Symbol aus kann nicht importiert "*Quelle*': unter*Deklaration*'wurde bereits importiert aus einer anderen Assembly'*Quelle*"
C4946|Reinterpret_cast wird zwischen verknüpften Klassen verwendet: "*Deklaration*'und'*Deklaration*"
C4995|"*Namen*": Name wurde als #pragma als veraltet markiert
C4996|'*issue*': *description*
C4997|"*Typ*': Co-Klasse implementiert keine COM- oder Pseudoschnittstelle
C4998|Erwartung fehlgeschlagen: *Beschreibung*(*Anzahl*)

## <a name="see-also"></a>Siehe auch

- [/ WV-Compileroption](../../build/reference/compiler-option-warning-level.md)
- [Compiler-Warnungen, die standardmäßig deaktiviert sind](../../preprocessor/compiler-warnings-that-are-off-by-default.md)
- [warning](../../preprocessor/warning.md)
