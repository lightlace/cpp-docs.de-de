---
title: Compilerwarnungen nach Compilerversion | Microsoft Docs
ms.custom: 
ms.date: 01/31/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- warnings, by compiler version
- cl.exe compiler, setting warning options
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f6ee65b1001f0cf651fcbbd68170484cd134aa4
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2018
---
# <a name="compiler-warnings-by-compiler-version"></a>Compilerwarnungen nach Compilerversion

Der Compiler kann Unterdrücken von Warnungen, die nach der Version eingeführt wurden, Sie mithilfe geben, der [WV](../../build/reference/compiler-option-warning-level.md) -Compileroption. Dies ist nützlich für die Verwaltung des Buildprozesses, wenn Sie eine neue Toolsetversion eingeführt und vorübergehend neue Warnungen unterdrücken möchten. Diese Option unterdrückt keine neue Fehlermeldungen. Es wird nicht empfohlen, Sie alle neue Warnungen unterdrücken dauerhaft! Es wird empfohlen, immer auf der höchsten reguläre Warnebene Kompilieren __/W4__, und Entfernen der __WV__ Option in den Build so bald wie möglich. 

Diese Versionen des Compilers wurden neue Warnungen eingeführt:

| Produkt | Versionsnummer des Compilers |
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
| Visual C++ 2017 RTM | 19.10.24903.0 |
| Visual C++ 2017 Version 15.1 | 19.10.25017.0 |
| Visual C++ 2017 Version 15.3 | 19.11.25506.0 |
| Visual C++ 2017 Version 15.5 | 19.12.25827.0 |

Sie geben nur die Nummer der Hauptversion, die Nummern für Haupt- und Nebenversionsnummern oder Haupt-oder Nebenversion, und erstellen Sie Zahlen können die __WV__ Option. Der Compiler meldet alle Warnungen, die Versionen stimmen überein, die mit der angegebenen Zahl beginnen und unterdrückt alle Warnungen für Versionen, die größer als die angegebene Anzahl. Beispielsweise __/Wv:17__ meldet alle Warnungen in oder vor einer Version von Visual Studio 2012 eingeführt und unterdrückt alle Warnungen, die von einem Compiler von Visual Studio 2013 (Version 18) oder höher eingeführt. Unterdrückt Warnungen, eingeführt in Visual Studio 2015 update 2 und höher können Sie __/Wv:19.00.23506__. Verwendung __/Wv:19.11__ melden Sie alle Warnungen in einer beliebigen Version von Visual Studio vor Visual Studio 2017 Version 15.5 eingeführt, aber unterdrückt Warnungen, die in Visual Studio 2017 15.5 und höher eingeführt wurden.

Die folgenden Abschnitte Listen die Warnungen eingeführt, die von der jeweiligen Version von Visual C++, die Sie mithilfe von unterdrücken können die __WV__ -Compileroption. Die __WV__ Option keine Unterdrückung von Warnungen, die nicht aufgeführt sind, die schon vor die angegebenen Versionen des Compilers verfügbar waren.

## <a name="warnings-introduced-in-visual-c-2017-version-155-compiler-version-1912258270"></a>Warnungen, die in Visual C++ 2017 Version 15.5 (Compilerversion 19.12.25827.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.11__.

|||
|-|-|
C5044|Ein Argument an die Befehlszeilenoption *Option* verweist auf einen Pfad "*Pfad*", nicht vorhanden

## <a name="warnings-introduced-in-visual-c-2017-version-153-compiler-version-1911255060"></a>Warnungen, die in Visual C++ 2017 Version 15.3 (Compilerversion 19.11.25506.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.10__.

|||
|-|-|
C4843|"*Typ1*": ein Ausnahmehandler eines Verweises auf Array- oder Funktionsausdruck Typ ist nicht erreichbar, verwenden Sie "*Typ2*" stattdessen
C4844|"Exportieren Modul *Modulname*;" ist jetzt die bevorzugte Syntax zum Deklarieren einer Modul-Schnittstelle
C5039|"*Funktion*': Zeiger oder Verweis auf potenziell Auslösen von Funktion" extern "C-Funktion unter - EHc übergeben. Nicht definiertes Verhalten kann auftreten, wenn diese Funktion eine Ausnahme auslöst.
C5040|Dynamische Ausnahmespezifikationen sind gültig, nur in C ++ 14 und früheren Versionen. zum Behandeln von als noexcept(false)
C5041|"*Definition*": Out-of-Line-Definition für Constexpr statischer Datenmember ist nicht erforderlich und veraltetes Feature in C ++ 17
C5042|"*Deklaration*": Funktionsdeklarationen im Gültigkeitsbereich der-Block nicht "Inline" angegeben sein, in standardmäßigem C++ – "Inlinespezifizierer" entfernen
C5043|"*Spezifikation*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein

## <a name="warnings-introduced-in-visual-c-2017-version-151-compiler-version-1910250170"></a>Warnungen, die in Visual C++ 2017 Version 15.1 (Compilerversion 19.10.25017.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.10.24903__.

|||
|-|-|
C4597|ein nicht definiertes Verhalten: *Beschreibung*
C4604|"*Typ*": Argumentübergabe nach Wert systemeigenen und verwalteten Apartmentgrenze gültige Kopierkonstruktor erfordert. Andernfalls ist das Laufzeitverhalten nicht definiert
C4749|bedingt unterstützt: *Beschreibung*
C4768|__declspec-Attribute vor Verknüpfungsspezifikation werden ignoriert.
C4834|Verwerfen von Rückgabewert der Funktion mit 'Nodiscard'-Attribut
C4841|nicht standardmäßige Erweiterung verwendet: *Erweiterung*
C4842|Das Ergebnis des "Offsetof" auf einen Typ mit mehrfacher Vererbung angewendet wird nicht garantiert, Compilerversionen konsistent sein.
C4869|"Nodiscard" kann nur auf Klassen, Enumerationen und Funktionen mit nicht-Void-Rückgabetyp angewendet werden
C5033|"*speicherklassenattribute*" ist nicht mehr unterstützte Speicherklasse
C5034|Verwenden der systeminternen "*systeminterne*" bewirkt, dass Funktion *Funktion* als Gast-Code kompiliert werden
C5035|Verwenden der Funktion "*Feature*" bewirkt, dass Funktion *Funktion* als Gast-Code kompiliert werden
C5036|Beim Kompilieren mit /hybrid:x86arm64-Funktion Varargs zeigerkonvertierung "*Typ1*'to'*Typ2*"
C5037|"*Memberfunktion*': eine Out-of-Line-Definition eines Elements einer Klassenvorlage sind keine Standardargumente
C5038|Datenmember "*member1*"wird so initialisiert, nach der Datenmember"*member2*"

## <a name="warnings-introduced-in-visual-c-2017-rtm-compiler-version-191024903"></a>Warnungen, die in Visual C++ 2017 RTM (Compilerversion 19.10.24903) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00__.

|||
|-|-|
C4468|"Fallthrough": Attribut muss gefolgt von einer Case-Bezeichnung oder einer standardbezeichnung
C4698|"*Feature*" ist für die Auswertung nur zu Testzwecken und unterliegt Änderungen oder Entfernung in Zukunft aktualisiert.
C4839|nicht standardmäßige Verwendung der Klasse*Klasse*"als Argument an eine Variadic-Funktion
C4840|nicht Portable verwenden der Klasse*Klasse*"als Argument an eine Variadic-Funktion

## <a name="warnings-introduced-in-visual-c-2015-update-3-compiler-version-1900242151"></a>Warnungen, die in Visual C++ 2015 Update 3 (Compilerversion 19.00.24215.1) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00.23918__.

|||
|-|-|
C4467|Verwendung von ATL-Attribute ist veraltet.
C4596|"*Namen*': Unzulässiger gekennzeichneter Name in Memberdeklaration
C4598|' #include \< *Header*\>": Anzahl der Header *Anzahl* in der *Quelle* stimmt nicht überein *Quelle* an, die Position
C4599|"*Argument*": *Quelle* Argumentennummer *Anzahl* entspricht nicht *Quelle*

## <a name="warnings-introduced-in-visual-c-2015-update-2-compiler-version-1900239180"></a>Warnungen, die in Visual C++ 2015 Update 2 (Compilerversion 19.00.23918.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00.23506__.

|||
|-|-|
C4466|Coroutine Heap Elision konnte nicht ausgeführt werden.
C4595|"*Klasse*': nicht-memberoperators New- oder Delete-Funktionen dürfen nicht Inline deklariert werden
C4828|Die Datei enthält ein Zeichen ab dem Offset 0 X*Wert* , die in der aktuellen quellzeichensatz ungültig ist (Codepage *Anzahl*).
C4868|Compilerfehler möglicherweise die Reihenfolge der Auswertung von links nach rechts in der Initialisiererliste nicht erzwungen.

## <a name="warnings-introduced-in-visual-c-2015-update-1-compiler-version-1900235060"></a>Warnungen, die in Visual C++ 2015 Update 1 (Compilerversion 19.00.23506.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:19.00.23026__.

|||
|-|-|
C4426|optimierungseinstellungen geändert, nachdem einschließlich Header, möglicherweise aufgrund von #pragma optimize()
C4654|Code platziert werden, bevor der vorkompilierten Headerdatei umfassen Zeile werden ignoriert. Fügen Sie Code, um vorkompilierte Header.
C5031|#pragma warning"(POP): wahrscheinlich Konflikt die Folge, herunternehmen Status" Warnung "in anderen Datei abgelegt
C5032|#pragma warning"(Push) ohne entsprechende #pragma warning"(POP) erkannt

## <a name="warnings-introduced-in-visual-c-2015-rtm-compiler-version-1900230260"></a>Warnungen, die in Visual C++ 2015 RTM (Compilerversion 19.00.23026.0) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:18__.

|||
|-|-|
C4427|"*Fehler*': Überlauf in Konstanten Division zu nicht definiertem Verhalten
C4438|"*Typ*": kann nicht problemlos aufgerufen werden, / "await": Clrcompat-Modus. Wenn "*Typ*" Aufrufe in die CLR es möglicherweise CLR Head Beschädigung
C4455|' Operator *Namen*": literales Suffix-Bezeichner, die nicht mit einem Unterstrich beginnen, sind reserviert.
C4456|Deklaration von "*Namen*" Blendet die frühere lokalen Deklaration
C4457|Deklaration von "*Namen*" Blendet Parameter-Funktion
C4458|Deklaration von "*Namen*" Blendet den Klassenmember
C4459|Deklaration von "*Namen*" Blendet globale Deklaration
C4462|"*Typ*": die GUID des Typs kann nicht bestimmt werden. Das Programm kann zur Laufzeit fehlschlagen.
C4463|Überlauf; Zuweisen von *Wert* Bitfeld, das nur Werte aus enthalten können *Wert* zu *Wert*
C4473|"*Funktion*': nicht genügend Argumente für Formatzeichenfolge
C4474|"*Funktion*': zu viele Argumente zu übergeben, für die Formatzeichenfolge
C4475|"*Funktion*": argumentlängenmodifizierer "*Modifizierer*'cannot be used with Typzeichen für Feld'*Zeichen*" im Formatbezeichner
C4476|"*Funktion*": Unbekannte Typzeichen für Feld '*Zeichen*"im Formatbezeichner
C4477|"*Funktion*": Formatzeichenfolge "*Zeichenfolge*"erfordert ein Argument des Typs"*Typ*", sondern Variadic-Argument *Anzahl* weist den Typ "*Typ*"
C4478|"*Funktion*": können nicht mit Feldern fester Breite und nicht mit Feldern fester Breite Platzhalter in der gleichen Formatzeichenfolge kombiniert werden
C4494|"*Typ*": __declspec(allocator) wird ignoriert, da der Rückgabetyp für der Funktion ist kein Zeiger oder Verweis
C4495|nicht dem Standard entsprechende Erweiterung "__super": explizite Basisklassennamen ersetzt
C4496|nicht dem Standard entsprechende Erweiterung 'for each"verwendet: Ersetzen Sie durch wie Serveradresse-for-Anweisung
C4497|"sealed" verwendeten, nicht dem Standard entsprechende Erweiterung: 'letzte' ersetzt
C4498|nonstandard extension used: '*extension*'
C4499|"*Spezialisierung*': eine explizite Spezialisierung sind keine Speicherklasse (ignoriert)
C4576|ein in Klammern gefolgt von einer Initialisiererliste ist eine nicht standardmäßige expliziten Typ Konvertierung-syntax
C4577|"Noexcept" verwendet, mit der keine Ausnahmebehandlung angegebenen Modus; Beenden von Ausnahme ist nicht gewährleistet. Geben Sie/EHsc
C4578|'abs': Konvertierung von "*Typ*'to'*Typ*', möglicher Datenverlust (wollten Sie rufen Sie"*Namen*"oder auf #include <cmath>?)
C4582|"*Typ*': Konstruktor wird nicht implizit aufgerufen.
C4583|"*Typ*": Destruktor wird nicht implizit aufgerufen.
C4587|"*Typ*": verhaltensänderung: Konstruktor wird nicht mehr implizit aufgerufen.
C4588|"*Typ*": verhaltensänderung: Destruktor wird nicht mehr implizit aufgerufen.
C4589|Konstruktor abstrakten Klasse*Typ*'ignoriert Initialisierer für die virtuelle Basisklasse'*Typ*"
C4591|"Constexpr" Aufruf Tiefe maximal *Anzahl* überschritten (/ Constexpr:depth<NUMBER>)
C4592|"*Typ*": Symbol werden dynamisch initialisiert (Implementierung Beschränkung)
C4593|"*Typ*": "Constexpr" Aufruf Auswertung Schritt kann maximal *Wert* überschritten; verwenden Sie /constexpr:steps<NUMBER> um den Grenzwert zu erhöhen.
C4647|Verändertes Programmverhalten: __is_pod (*Typ*) anderen Wert aufweist, in früheren Versionen
C4648|Standard-Attribut "Carries_dependency" wird ignoriert.
C4649|Attribute werden in diesem Kontext ignoriert.
C4753|Grenzen für Zeiger wurde nicht gefunden. Systeminterne ignoriert MPX-Funktion
C4771|Grenzen müssen mithilfe eines Zeigers, der einfachen erstellt werden. Systeminterne ignoriert MPX-Funktion
C4774|"*Beschreibung*": im Argument erwartet Formatzeichenfolge *Anzahl* ist kein Zeichenfolgenliteral
C4775|nicht dem Standard entsprechende Erweiterung in der Formatzeichenfolge "*Zeichenfolge*'der Funktion"*Funktion*"
C4776|"%*Zeichen*"ist nicht zulässig in der Formatzeichenfolge der Funktion"*Funktion*"
C4777|"*Beschreibung*": Formatzeichenfolge "*Zeichenfolge*"erfordert ein Argument des Typs"*Typ*", sondern Variadic-Argument *Anzahl* weist den Typ "*Typ*"
C4778|"*Beschreibung*': nicht terminierte Formatzeichenfolge"*Zeichenfolge*"
C4838|Konvertierung von '*Typ*'to'*Typ*"ist eine einschränkende Konvertierung erforderlich
C5022|"*Typ*': mehrere bewegungskonstruktoren angegeben
C5023|"*Typ*': mehrere Verschiebe-standardzuweisungsoperatoren angegeben
C5024|"*Deklaration*": Verschieben Konstruktor wurde implizit als gelöscht definiert.
C5025|"*Deklaration*': Zuweisungsoperator wurde implizit als gelöscht definiert, verschieben
C5026|"*Typ*": Verschieben Konstruktor wurde implizit als gelöscht definiert.
C5027|"*Typ*': Zuweisungsoperator wurde implizit als gelöscht definiert, verschieben
C5028|"*Namen*': Ausrichtung angegeben, in der vorherigen Deklaration (*Anzahl*) nicht in der Definition angegeben.
C5029|nicht dem Standard entsprechende Erweiterung: Ausrichtungsattribute in C++, Zuweisen von Variablen, Datenmember und Transpondertypen nur
C5030|Attribut "*Attribut*" wird nicht erkannt.

## <a name="warnings-introduced-in-visual-c-2013-compiler-version-1800210051"></a>Warnungen, die in Visual C++ 2013 (Compilerversion 18.00.21005.1) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:17__.

|||
|-|-|
C4301|"*Typ*": Überschreiben der virtuellen Funktion nur unterscheidet sich von "*Deklaration*" durch Const/Volatile-Qualifizierer
C4316|"*Typ*": Objekt auf dem Heap reserviert möglicherweise nicht ausgerichtet *Anzahl*
C4380|"*Typ*": ein Standardkonstruktor kann nicht als veraltet markiert werden
C4388|"*token*': Konflikt zwischen signed/unsigned
C4423|"Std:: bad_alloc": wird von Klasse abgefangen ("*Typ*") in Zeile *Anzahl*
C4424|für catch '*Typ*"vorangestellt"*Typ*"in Zeile *Anzahl*; unvorhersehbaren Verhalten kann auftreten, wenn"Std:: bad_alloc"ausgelöst wird
C4425|SAL-Anmerkung kann nicht angewendet werden, um "..."
C4464|Relative Includepfad enthält '..'
C4575|"__vectorcall" nicht kompatibel mit der "/ Clr" Option: '__stdcall' konvertieren
C4609|"*Typ*"ableitet, Standardschnittstelle"*Typ*"für Typ"*Typ*". Verwenden Sie eine andere Standardschnittstelle für "*Typ*", oder die Beziehung Basistypen zu abgeleiteten unterbrochen.
C4754|Konvertierungsregeln für arithmetische Operationen im Vergleich zur *Beschreibung*(*Anzahl*) bedeuten, dass ein Branch nicht ausgeführt werden kann. CAST "*Typ*'to'*Typ*" (oder ähnlichen Typ mit *Anzahl* Bytes).
C4755|Konvertierungsregeln für arithmetische Operationen im Vergleich zur *Beschreibung*(*Anzahl*) bedeuten, dass ein Branch nicht ausgeführt werden, in einer Inline-Funktion. CAST "*Typ*'to'*Typ*" (oder ähnlichen Typ mit *Anzahl* Bytes).
C4767|Name des Abschnitts "*Namen*' ist länger als 8 Zeichen und wird vom Linker abgeschnitten
C4770|teilweise validiert Enum '*Namen*"als Index verwendet
C4827|Eine öffentliche Methode von "ToString" mit 0-Parametern als virtuell gekennzeichnet werden, und überschreiben
C4882|übergeben Funktionselemente mit Operatoren nicht Const-Aufruf an Concurrency:: parallel_for_each ist veraltet.
C4973|"*Typ*': als veraltet markiert
C4974|"*Typ*': als veraltet markiert
C4981|Warbird: Funktion "*Deklaration*" als __forceinline markiert nicht inline, da sie die Semantik der Ausnahme enthält
C4990|Warbird: *Nachricht*
C4991|Warbird: Funktion "*Deklaration*" als "__forceinline" nicht inline Schutzebene des Inlinees: größer als das übergeordnete Element ist markiert
C4992|Warbird: Funktion "*Deklaration*" als __forceinline markiert nicht inline, da es sich um Inlineassembly enthält, der nicht geschützt werden können

## <a name="warnings-introduced-in-visual-c-2012-compiler-version-1700511061"></a>Warnungen, die in Visual C++ 2012 (Compilerversion "17.00.51106.1") eingeführt

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:16__.

|||
|-|-|
C4330|Attribut "*Attribut*"für den Abschnitt"*Abschnitt*" ignoriert
C4415|duplicate __declspec(code_seg('*name*'))
C4416|__declspec(code_seg(...)) contains empty string: ignored
C4417|eine explizite Vorlageninstanziierung sind keine __declspec(code_seg(...)): ignoriert
C4418|__declspec(code_seg(...)) ignored on an enum
C4419|"*Namen*"wirkt sich nicht bei Anwendung auf private Verweisklasse"*Typ*".
C4435|"*Typ*': das Objektlayout unter/vd2 ändert sich aufgrund der virtuellen Basis '*Typ*"
C4436|Dynamic_cast von virtueller Basis '*Typ*'to'*Typ*"im Konstruktor oder Destruktor fehlschlagen mit teilweise erstelltes Objekt
C4437|Dynamic_cast von virtueller Basis '*Typ*'to'*Typ*' konnte in einigen Kontexten fehl
C4443|Pragma-Parameter erwartet '0', '1' oder '2' sein.
C4446|"*Typ*': Member können nicht zugeordnet"*Namen*"in diesem Typ aufgrund eines Konflikts mit dem Typnamen. Die Methode wurde umbenannt in "*Namen*"
C4447|'main' Signatur ohne Threadingmodell gefunden. Erwägen Sie ' Int main (Platform:: Array\<Platform:: String ^ > ^ Args) ".
C4448|"*Typ*" verfügt nicht über eine Standardschnittstelle, die in den Metadaten angegeben. Kommissionierung: "*Typ*", die zur Laufzeit fehlschlagen.
C4449|"*Typ*' eine nicht versiegelten Typs als"[WebHostHidden]"gekennzeichnet werden soll
C4450|"*Typ*"sollte als gekennzeichnet werden [WebHostHidden], da es abgeleitet"*Typ*"
C4451|"*Typ*': Verwendung von Verweisklasse*Typ*" innerhalb dieser Kontext kann zu ungültigen Marshalling eines Objekts über Kontexte hinweg führen
C4452|"*Typ*": öffentlicher Typ darf nicht im globalen Gültigkeitsbereich sein. Es muss in einem Namespace, der den Namen der Ausgabedatei winmd untergeordnet ist.
C4453|"*Typ*": ein Typ "[WebHostHidden]" sollte nicht verwendet werden, auf der veröffentlichten Oberfläche eines öffentlichen Typs, der nicht [WebHostHidden]
C4454|"*Typ*" ist überladen, um mehr als die Anzahl von Eingabeparametern ohne [DefaultOverload] angegeben. Kommissionieren "*Deklaration*" als die standardmäßige Überladung
C4471|"*Namen*': eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung benötigen einen zugrunde liegenden Typ (Int wird angenommen)
C4472|"*Namen*" ist eine systemeigene Enumeration: Fügen Sie einen Zugriffsspezifizierer (privat/öffentlich), um eine verwaltete/WinRT-Enumeration zu deklarieren.
C4492|"*Typ*": Übereinstimmungen basieren Ref-Klassenmethode "*Typ*", aber nicht "override" markiert ist
C4493|Delete-Ausdruck hat keine Wirkung, da der Destruktor von "*Typ*" keinen 'öffentlichen' Zugriff
C4585|"*Typ*": ein WinRT "Öffentliche Verweisklasse" muss entweder versiegelt oder eine Ableitung von einer vorhandenen unversiegelten Klasse
C4586|"*Typ*": ein öffentlicher Typ kann nicht in einem Namespace der obersten Ebene namens "Windows" deklariert werden
C4695|#pragma execution_character_set: '*argument*' is not a supported argument: currently only 'UTF-8' is supported
C4703|potenziell nicht initialisierten lokalen Zeigervariablen "*Namen*" verwendet
C4728|/ Yl-Option-ignoriert, weil die PCH-Verweis erforderlich ist.
C4745|flüchtige Zugriff des "*Namen*" kann nicht berücksichtigt aufgrund ihrer Größe werden
C4746|flüchtige Zugriff des "*Namen*" / volatile des unterliegt:\<Iso\|ms > festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen
C4872|Floating Point Division durch 0 (null), die beim Kompilieren des Aufrufdiagramms für das Concurrency:: parallel_for_each am erkannt: '*Beschreibung*"
C4880|Umwandlung von '*Typ*'to'*Typ*": Umwandeln von einem Zeiger oder Verweis Constness möglicherweise zu nicht definiertem Verhalten in einer eingeschränkten Amp-Funktion
C4881|des Konstruktors und/oder des Destruktors wird nicht aufgerufen werden, für die "tile_static" Variable "*Typ*"
C4966|"*Beschreibung*" __code_seg Anmerkung mit nicht unterstützten Segmentnamen Anmerkung ignoriert hat
C4988|"*Typ*': Variable deklariert Bereichs der äußeren Klasse/Funktion
C4989|"*Beschreibung*': Typ verfügt über in Konflikt stehende Definitionen.

## <a name="warnings-introduced-in-visual-c-2010-compiler-version-16004021901"></a>Warnungen, die in Visual C++ 2010 (Compilerversion 16.00.40219.01) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:15__.

|||
|-|-|
C4352|"*Namen*": systeminterne Funktion, die bereits definiert.
C4573|die Verwendung von "*Typ*' benötigt den Compiler, 'this' jedoch Erfassen der aktuellen standarderfassungsmodus ein Modus lässt nicht zu
C4574|"*Namen*'definiert ' 0': wollten Sie verwenden" #if *Namen*"?
C4689|"*Zeichen*': nicht unterstützte Zeichen in #pragma Detect_mismatch; #pragma ignoriert
C4751|/ Arch AVX-Flag gilt nicht für Intel(R) Streaming SIMD Extensions, die Inline-ASM gewiesen
C4752|Intel Advanced Vector Extensions; gefunden. Erwägen Sie die entsprechenden/Arch AVX-flag
C4837|Trigraph erkannt: '?? *Zeichen*"ersetzt durch"*Zeichen*"
C4986|"*Deklaration*': Ausnahmespezifikation stimmt nicht mit der vorherigen Deklaration überein
C4987|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw (...)'

## <a name="warnings-introduced-in-visual-c-2008-compiler-version-15002102208"></a>Warnungen, die in Visual C++ 2008 (Compilerversion 15.00.21022.08) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:14__.

|||
|-|-|
C4396|"*Typ*": Der Inlinespezifizierer kann nicht verwendet werden, wenn eine Friend-Deklaration auf die Spezialisierung einer Funktionsvorlage verweist
C4413|"*Deklaration*": Verweismember wird an einen temporären, die nicht beibehalten, nach dem Beenden des Konstruktors initialisiert.
C4491|"*Beschreibung*": hat ein ungültiges Format der IDL-Version
C4603|"*Namen*": Makro ist nicht definiert oder die Definition wurde nach Verwendung des vorkompilierten Headers
C4627|"*Beschreibung*": bei der Suche nach Verwendung des vorkompilierten Headers übersprungen
C4750|"*Beschreibung*': Funktion mit" _alloca()"" inline in einer Schleife
C4910|'*type*': '__declspec(dllexport)' and 'extern' are incompatible on an explicit instantiation
C4985|"*Deklaration*": Attribute in vorheriger Deklaration nicht vorhanden sind.

## <a name="warnings-introduced-in-visual-c-2005-compiler-version-140050727762"></a>Warnungen, die in Visual C++ 2005 (Compilerversion 14.00.50727.762) eingeführt

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:13__.

|||
|-|-|
C4000|Unbekannte Warnung wählen Sie den technischen Supportbefehl im Visual C++-Hilfemenü, oder öffnen Sie den technischen Support-Hilfedatei für Weitere Informationen
C4272|"*Typ*": von "__declspec(dllimport)" "markiert; systemeigene Aufrufkonvention muss angeben werden, wenn eine Funktion zu importieren.
C4333|"*Ausdruck*": von zu viel, Verlust von Daten nach rechts verschieben
C4334|"*Ausdruck*": Ergebnis der 32-Bit-Verschiebung implizit zu 64 Bit konvertiert (war ein 64-Bit-Verschiebung vorgesehen?)
C4335|Mac-Dateiformat erkannt: Konvertieren Sie die Quelldatei in DOS oder UNIX-Format
C4342|verhaltensänderung: '*Typ*"aufgerufen wird, jedoch ein Memberoperator aufgerufen wurde, in früheren Versionen
C4350|verhaltensänderung: '*Deklaration*"anstelle des Namens"*Deklaration*"
C4357|ParamArray-Argument in der formalen Argumentliste für den Delegaten gefunden "*Deklaration*"wird ignoriert, während der Generierung"*Typ*"
C4358|"*Ausdruck*": Rückgabetyp von kombinierten Delegaten ist nicht "void"; zurückgegebene Wert ist nicht definiert
C4359|"*Typ*': Ausrichtung-Spezifizierer ist kleiner als die tatsächliche Ausrichtung (*Anzahl*), und werden ignoriert.
C4362|"*Typ*': Ausrichtung, die größer als 8 Bytes wird von der CLR nicht unterstützt
C4364|#using für die Assembly "*Namen*" zuvor gesehen am *Beschreibung*(*Anzahl*) ohne As_friend-Attribut; As_friend nicht angewendet
C4365|"*Ausdruck*': Konvertierung von '*Typ*'to'*Typ*', Konflikt mit/ohne Vorzeichen
C4366|Das Ergebnis der unären "*Operator*" Operator kann möglicherweise nicht ausgerichteten.
C4367|Konvertierung von '*Typ*'to'*Typ*"verursachen Datatype Speicheranweisung-Ausnahme
C4368|kann nicht definiert "*Namen*"als Mitglied der verwaltete'*Typ*": gemischte Typen werden nicht unterstützt.
C4369|"*Typ*": Enumeratorwert "*Anzahl*"kann nicht als dargestellt werden"*Typ*', Wert ist'*Anzahl*"
C4374|"*Deklaration*": Schnittstellenmethode wird durch nicht virtuelle Methode nicht implementiert "*Deklaration*"
C4375|nicht öffentlichen Methode "*Deklaration*"nicht überschreiben"*Deklaration*"
C4376|Zugriffsspezifizierer '*Spezifizierer*: "wird nicht mehr unterstützt: Verwenden Sie"*Spezifizierer*: "stattdessen
C4377|systemeigene Typen sind standardmäßig privat. -d1PrivateNativeTypes ist veraltet.
C4378|Sie benötigen Funktionszeiger zum Ausführen der Initialisierer; ResolveMethodHandle
C4379|Version *Version* von der common Language Runtime nicht von diesem Compiler unterstützt wird. Mit dieser Version kann zu unerwarteten Ergebnissen führen
C4381|"*Deklaration*": Schnittstellenmethode wird durch den nicht öffentlichen Methode nicht implementiert "*Deklaration*"
C4382|Auslösen von "*Typ*": ein Typ mit __clrcall-Destruktor oder Kopierkonstruktor nur in "/ CLR" abgefangen werden kann: pure-Modul
C4383|"*Typ*": die Bedeutung der Dereferenzieren eines Handles kann sich ändern, wenn eine benutzerdefinierte "*Operator*" Operator vorhanden ist, Schreiben Sie den Operator als eine statische Funktion der Operand explizit sein
C4384|#pragma "*Richtlinie*" sollte nur im globalen Gültigkeitsbereich verwendet werden
C4393|"*Typ*': const hat keine Auswirkungen auf *Beschreibung* Datenmember; ignoriert
C4394|"*Typ*": anwendungsdomänenspezifisches Symbol sollte nicht gekennzeichnet werden, mit __declspec (*Wert*)
C4395|"*Typ*': Memberfunktion wird aufgerufen, auf eine Kopie der Datenmember Initonly"*Typ*"
C4397|DefaultCharSetAttribute wird ignoriert.
C4398|"*Typ*": prozessspezifisch globales Objekt möglicherweise nicht ordnungsgemäß mit mehreren Anwendungsdomänen; erwägen __declspec(appdomain)
C4399|"*Typ*": Symbol pro Prozess sollte nicht mit __declspec gekennzeichnet werden (*Wert*) beim Kompilieren mit/clr: pure
C4400|"*Typ*": Const/Volatile-Qualifizierer für diesen Typ werden nicht unterstützt.
C4412|"*Deklaration*': Funktionssignatur enthält Typ '*Typ*'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem oder systemeigenem.
C4429|Mögliche unvollständig oder falsch formatierte universelle Zeichenname
C4430|Fehlender Typspezifizierer - int wird angenommen. Hinweis: C++ unterstützt keine Standard-int
C4431|Fehlender Typspezifizierer - int wird angenommen. Hinweis: default-int wird von C++ nicht unterstützt
C4434|ein statischer Konstruktor muss private zugriffsmöglichkeiten aufweisen; in privaten Zugriff geändert
C4439|"*Typ*': Definition der Funktion mit einem verwalteten Typ in der Signatur benötigen eine __clrcall-Aufrufkonvention
C4441|die Aufrufkonvention der "*Konvention*" ignoriert. "*Konvention*" stattdessen verwendet
C4445|"*Deklaration*': in einem verwalteten/WinRT-Typ kann eine virtuelle Methode kann nicht privat sein
C4460|CLR/WinRT-Operator "*Typ*", Parameter als Verweis übergeben. CLR/WinRT-Operator "*Operator*"hat eine andere Semantik als C++-Operator"*Operator*", wollten Sie als Wert übergeben?
C4461|"*Typ*": Diese Klasse verfügt über einen Finalizer '! *Typ*", jedoch keinen Destruktor ' ~*Typ*"
C4470|gleitkommasteuerelements Pragmas unter/CLR ignoriert
C4480|nicht dem Standard entsprechende Erweiterung: Angeben von zugrunde liegender Typ für Enum '*Typ*"
C4481|nicht dem Standard entsprechende Erweiterung: Überschreibungsspezifizierer '*Spezifizierer*"
C4482|nicht dem Standard entsprechende Erweiterung: Enum '*Typ*"in qualifizierten Namen verwendet
C4483|Syntaxfehler: C++-Schlüsselwort erwartet.
C4484|"*Typ*": Übereinstimmungen basieren Ref-Klassenmethode "*Typ*", aber nicht "virtual", "new" oder "override"; markiert ist "new" (und nicht "virtual") wird angenommen.
C4485|"*Typ*": Übereinstimmungen basieren Ref-Klassenmethode "*Typ*", aber nicht markierte 'new' oder 'override'; "new" (und "virtual") werden angenommen.
C4486|"*Typ*': eine private virtuelle Methode einer Verweisklasse oder eine Wertklasse, sollte"sealed"markiert werden
C4487|"*Typ*": Übereinstimmungen geerbte nicht virtuelle Methode "*Typ*" jedoch nicht explizit "new" gekennzeichnet ist
C4488|"*Typ*": erfordert "*Schlüsselwort*"Schlüsselwort zur Implementierung der Schnittstellenmethode "*Typ*"
C4489|"*Schlüsselwort*': für Schnittstellenmethode unzulässig"*Namen*"; Override-Bezeichner nur auf Ref hardwareinventurklassen- und Klassenmethoden dürfen
C4490|"*Schlüsselwort*": falsche Verwendung von Überschreibungsspezifizierer; "*Typ*" eine Klassenmethode Basis Ref stimmt nicht überein
C4538|"*Typ*": Const/Volatile-Qualifizierer für diesen Typ werden nicht unterstützt.
C4559|"*Typ*": Neudefinition; die Funktion Gewinne __declspec (*Wert*)
C4565|"*Typ*": Neudefinition; Symbol wurde zuvor mit __declspec deklariert (*Wert*)
C4566|Universelle Zeichennamen dargestellte Zeichen "*Zeichen*" kann nicht in der aktuellen Codepage dargestellt werden (*Anzahl*)
C4568|"*Typ*': keine Elemente mit der Signatur der expliziten Überschreibung überein.
C4569|"*Typ*': keine Elemente mit der Signatur der expliziten Überschreibung überein.
C4570|"*Typ*': nicht explizit deklariert als abstrakte abstrakte Funktionen hat
C4571|Information: catch(...)-Semantik seit Visual C++ 7.1 geändert; strukturierte Ausnahmen (SEH) werden nicht mehr abgefangen.
C4572|[ParamArray]-Attribut unter/CLR veraltet sind, verwenden Sie "..." stattdessen
C4580|[Attribut] ist veraltet. Geben Sie stattdessen *angegebenen*Attribut als Basisklasse
C4581|Verhalten veraltet: ' "*Namen*" "ersetzt durch"*Namen*' zur Verarbeitung des Attributs
C4606|#pragma-Warnung: "*Anzahl*" ignoriert. Codeanalysewarnungen sind nicht mit Warnstufen verknüpft.
C4631|MSXML oder XPath ist nicht verfügbar. XML-Dokumentkommentare werden nicht verarbeitet. *Beschreibung*
C4632|XML-Dokumentkommentar: *Beschreibung* -Zugriff verweigert: *Beschreibung*
C4633|XML-Dokumentkommentar*Beschreibung*: Fehler: *Beschreibung*
C4634|XML-Dokumentkommentar*Beschreibung*: kann nicht angewendet werden: *Beschreibung*
C4635|XML-Dokumentkommentar*Beschreibung*: falsch formatierte XML: *Beschreibung*
C4636|XML-Dokumentkommentar*Beschreibung*: Tag erfordert ein nicht leeres '*Beschreibung*"Attribut.
C4637|XML-Dokumentkommentar*Beschreibung*: <include> -Tag wurde verworfen. *Beschreibung*
C4638|XML-Dokumentkommentar*Beschreibung*: Verweis auf unbekanntes Symbol '*Beschreibung*".
C4639|MSXML Fehler, XML-Dokumentkommentare werden nicht verarbeitet. *Beschreibung*
C4641|XML-Dokumentkommentar hat eine mehrdeutige Referenz: 
C4678|Basisklasse*Deklaration*"ist weniger zugreifbar als"*Namen*"
C4679|"*Beschreibung*": Schnittstellenmember konnte nicht importiert
C4687|"*Typ*': eine versiegelte abstrakte Klasse kann nicht zu eine Schnittstelle implementieren"*Typ*"
C4688|"*Namen*": Einschränkungsliste enthält den privaten Assemblytyp "*Deklaration*"
C4690|[ Emitidl ( Pop ) ]: mehr POP-als Push-Vorgänge
C4691|"*Typ*': Typ verwiesen wurde erwartet. im nicht referenzierten *Modul* "*Beschreibung*", in der aktuellen Übersetzungseinheit verwendet stattdessen definierten Typs
C4692|"*Namen*": die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp '*Deklaration*"
C4693|"*Typ*': eine versiegelte abstrakte Klasse kann nicht Instanzmember aufweisen*Namen*"
C4694|"*Typ*': eine versiegelte abstrakte Klasse keine Basisklasse sind keine*Typ*"
C4720|Inline-Assembler-Berichte: "*Beschreibung*"
C4721|"*Beschreibung*': nicht als systeminterne Funktion verfügbar
C4722|"*Beschreibung*": Destruktor gibt nie Werte zurück, mögliche Speicherverluste
C4726|ARM-arch4/4 t unterstützt nur ' < Cpsr_f > oder < Spsr_f >' mit unmittelbaren nutzen
C4727|Mit dem Namen PCH *Name* mit dem gleichen Zeitstempel gefunden *Name* und *Namen*.  Verwenden erste PCH an.
C4729|Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.
C4730|"*Beschreibung*": Kombinieren von _m64 und Ausdrücke möglicherweise falsche Code führen
C4731|"*Beschreibung*": Framezeigerregister "*registrieren*" geändert von Inline-Assemblycode
C4732|systeminterne Funktion "*systeminterne*" wird in diese Architektur nicht unterstützt
C4733|Inline-Asm weist "fs": 0: Handler ist nicht als sicherer Handler registriert.
C4734|Mehr als 64 KB Debuggen Zeilennummern in einem COFF-Abschnitt Info; Ausgeben von COFF-Debug-Zeilennummern für Modul beenden "*Modul*"
C4738|Das 32-Bit-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust
C4739|Verweis auf Variable "*Variable*' überschreitet ihre Speicherplätze
C4740|Datenfluss für oder gegen Inline-Asm-Code unterdrückt Globale Optimierung
C4742|"*Variable*'verfügt über andere Ausrichtung '*Speicherort*'und'*Speicherort*": *Anzahl* und *Anzahl*
C4743|"*Namen*'hat eine unterschiedliche Größe '*Speicherort*'und'*Speicherort*": *Anzahl* und *Anzahl* Bytes
C4744|"*Namen*"hat einen anderen Typ "*Speicherort*'und'*Speicherort*": "*Typ*'und'*Typ*"
C4747|Aufrufen von verwalteten "*Typ*": verwalteter Code kann nicht ausgeführt werden, unter der Loadersperre, einschließlich des DLL-Einstiegspunkts und aufrufen, die aus der DLL-Einstiegspunkt wurde erreicht
C4761|ganzzahlige Größe übereinstimmende Datentypen in der Argument; Datenkonvertierung angegeben
C4764|Die Ausrichtung von catch-Objekten kann nicht mehr als 16 Bytes betragen.
C4788|"*Bezeichner*': Bezeichner wurde auf gekürzt"*Anzahl*' Zeichen
C4789|Puffer "*Namen*" Größe *Anzahl* Bytes werden überlaufen; *Anzahl* Bytes geschrieben, die ab dem Offset *Anzahl*
C4801|Zurück nach Verweis ist nicht überprüfbar: *Beschreibung*
C4819|Die Datei enthält ein Zeichen, das in der aktuellen Codepage dargestellt werden kann (*Anzahl*). Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden
C4826|Konvertierung von '*Typ*'to'*Typ*' ist signaturerweitert. Dies kann zu unerwartetem Laufzeitverhalten führen.
C4829|Möglicherweise falsche Parameter für Main-Funktion. Betrachten Sie ' Int main (Platform:: Array\<Platform:: String ^ > ^ Argv)'
C4835|"*Typ*": Initialisierer für die exportierten Daten wird nicht ausgeführt werden, bis verwalteter Code in der Hostassembly zuerst ausgeführt wird
C4867|"*Typ*': nicht standardmäßige Syntax; verwenden Sie '&', um einen Zeiger auf Member erstellen
C4936|__declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.
C4937|"*Namen*'und'*Namen*"sind nicht als Argumente für"*Option*"
C4938|"*Typ*": Reduction-Gleitkommavariable kann dazu führen, dass inkonsistente Ergebnissen bei/fp: strict oder #pragma fenv_access führen
C4939|#pragma vtordisp ist veraltet und wird in einem der nächsten Releases von Visual C++ entfernt.
C4947|"*Typ*': als veraltet markiert
C4949|Pragmas "managed" und "nicht verwaltet" sind sinnvoll, nur beim Kompilieren mit "/ Clr [: Option]"
C4950|"*Typ*': als veraltet markiert
C4955|"*Beschreibung*': Import wird ignoriert; bereits importiert aus"*Quelle*"
C4956|"*Typ*': Dieser Typ ist nicht überprüfbar
C4957|"*Ausdruck*": explizite Umwandlung von '*Typ*'to'*Typ*"ist nicht überprüfbar
C4958|"*Ausdruck*': Zeigerarithmetik ist nicht überprüfbar
C4959|keine nicht verwalteten definieren *Klasse* "*Typ*" in/CLR: safe, da nicht überprüfbaren Code den Zugriff auf ihre Member ausgegeben wird.
C4960|"*Beschreibung*" ist zu groß, um ein Profil
C4961|Keine Profildaten zusammengeführt "*Speicherort*", Profilgesteuerte Optimierungen werden deaktiviert.
C4962|"*Beschreibung*': Profilgesteuerte Optimierungen wurden deaktiviert, da Optimierungen Profildaten Profildaten verursacht hat.
C4963|"*Beschreibung*': keine Profildaten"; "ist in den instrumentierten Build verschiedene Compileroptionen verwendet wurden
C4964|Es wurden keine Optimierungsoptionen angegeben. Profilinformationen werden nicht gesammelt werden
C4965|Implizites Feld der Ganzzahl 0; Nullptr oder explizite Typumwandlung verwenden
C4970|Delegatkonstruktor: Zielobjekt ignoriert, da "*Deklaration*" ist statisch
C4971|Argument Order: \<Zielobjekt >, \<Funktion als Ziel > für Delegatkonstruktor veraltet ist, verwenden Sie \<Ziel Funktion >, \<Zielobjekt >
C4972|Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing-Vorgangs als L-Wert kann nicht überprüft werden.

## <a name="warnings-introduced-in-visual-c-2003-compiler-version-13103077"></a>Warnungen, die in Visual C++ 2003 (Compilerversion 13.10.3077) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:13.00.9466__.

|||
|-|-|
C4343|Optimieren von #pragma (*Beschreibung*, off) überschreibt/Og-Option
C4344|Verändertes Programmverhalten: Verwenden der expliziten Vorlagenergebnisse, Argumente im Aufruf von "*Deklaration*"
C4346|"*Typ*': abhängiger Name ist kein Typ
C4348|"*Deklaration*": Neudefinition des Standardparameters: Parameter *Anzahl*
C4356|"*Typ*': statische Datenmember kann nicht über eine abgeleitete Klasse initialisiert werden
C4408|anonyme *Struktur* wurden keine Datenmember deklariert
C4544|"*Deklaration*': Standardvorlagenargument wird für diese Vorlagendeklaration ignoriert
C4545|Ausdruck vor dem Komma wird als Funktion ausgewertet, der eine Argumentliste fehlt
C4546|Funktionsaufruf vor dem Komma ohne Argumentliste
C4547|"*Ausdruck*': Operator vor dem Komma keine Auswirkungen hat; Operator mit Nebeneffekten erwartet
C4548|Ausdruck vor dem Komma hat keine Auswirkung; es wurde ein Ausdruck mit Nebeneffekt erwartet
C4549|"*Ausdruck*': Operator vor dem Komma hat keine Auswirkungen; wollten Sie"*Ausdruck*"?
C4628|'digraphs' werden mit '-Ze' nicht unterstützt. Zeichenfolge "*Sequenz*"nicht als alternativer Token für interpretiert"*token*"
C4629|wurde verwendet, Zeichensequenz "*Sequenz*"interpretiert als Token"*token*" (Fügen Sie kein Leerzeichen zwischen den beiden Zeichen aus, wenn dies nicht beabsichtigt ist)
C4671|"*Beschreibung*": der Kopierkonstruktor ist nicht möglich
C4676|"*Beschreibung*": der Destruktor wird nicht zugegriffen werden kann
C4677|"*Namen*": die Signatur des nicht privaten Members enthält den privaten Assemblytyp "*Deklaration*"
C4686|"*Typ*': mögliche Änderung im Verhalten in der UDT gibt Aufrufkonvention zurück
C4812|Veralteter Deklarationsstil: Verwenden Sie "*Typ*::*Namen*" stattdessen
C4813|"*Typ*': eine Friend-Funktion einer lokalen Klasse muss bereits deklariert
C4821|Kann nicht zum Ermitteln von Unicode-Codierungstyp, speichern Sie die Datei mit Signatur (BOM)
C4822|"*Typ*": Lokale Klassenmemberfunktion keinen Text enthalten.
C4823|"*Typ*': verwendet, die feste Zeiger, aber entladen nicht aktiviert. Erwägen Sie/EHa
C4913|Benutzerdefinierter binärer Operator "," ist vorhanden, die Überladung konnte aber alle Operanden nicht konvertieren. Es wurde der standardmäßig enthaltene binäre Operator "," verwendet.
C4948|Rückgabetyp "*Deklaration*" entspricht nicht den letzten Parametertyp der entsprechenden Setter-Methode
C4951|"*Beschreibung*" wurde bearbeitet, seit die Profildaten Daten erfasst wurden, funktionsprofildaten werden nicht verwendet.
C4952|"*Beschreibung*': keine Profildaten gefunden wird, in der Programmdatenbank '*Beschreibung*"
C4953|Inlinee "*Beschreibung*" wurde bearbeitet, seit die Profildaten Daten erfasst wurden, nicht verwendet Profildaten
C4954|"*Beschreibung*": ein Profil nicht erstellt (__int64 Schalterausdruck enthält)

## <a name="warnings-introduced-in-visual-c-2002-compiler-version-13009466"></a>Warnungen, die in Visual C++ 2002 (Compilerversion 13.00.9466) eingeführt wurden

Diese Warnungen und alle Warnungen in höheren Versionen werden mit der Compileroption unterdrückt __/Wv:12__.

|||
|-|-|
C4096|"*Typ*": Schnittstelle "ist eine COM-Schnittstelle;" nicht auf IDL ausgegeben werden
C4097|Erwarteter pragma-Parameter sollte "restore" oder "off" sein
C4165|'HRESULT' wird "Bool" konvertiert sind Sie sicher, dass dies gewünscht ist?
C4183|"*Namen*": Rückgabetyp fehlt; davon ausgegangen, dass eine Memberfunktion, die Rückgabe von "Int" sein
C4199|*Beschreibung*
C4255|"*Namen*': Kein Funktionsprototyp angegeben: '()', '(void)' konvertieren
C4256|"*Deklaration*': Konstruktor für die Klasse mit virtuellen Basen besitzt"..."; Aufrufe möglicherweise nicht kompatibel mit früheren Versionen von Visual C++
C4258|"*Namen*': Definition von der for-Schleife ignoriert wird; die Definition des einschließenden Bereichs verwendet
C4263|"*Deklaration*': Memberfunktion überschreibt keine virtuelle Memberfunktion Basisklasse nicht
C4264|"*Deklaration*': keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar"*Klasse*"; die Funktion wird ausgeblendet
C4265|"*Typ*': Klasse verfügt über virtuelle Funktionen, aber der Destruktor ist nicht virtuell Instanzen dieser Klasse können nicht ordnungsgemäß zerstört
C4266|"*Deklaration*': keine Überschreibung für virtuelle Memberfunktion der Basis verfügbar"*Klasse*"; die Funktion wird ausgeblendet
C4267|"*Ausdruck*': Konvertierung von 'Size_t' nach '*Typ*', möglicher Datenverlust
C4274|#ident ignoriert. finden Sie in der Dokumentation für #pragma-Kommentar (Exestr, 'String')
C4277|importierten Element "*Typ*::*Namen*" vorhanden ist, als Datenmember und Funktionselement; Datenmember ignoriert
C4278|"*Namen*': Bezeichner in der Typbibliothek"*Beschreibung*"ist bereits ein Makro; verwenden Sie den Qualifizierer"Umbenennen"
C4279|"*Namen*': Bezeichner in der Typbibliothek"*Beschreibung*"ist ein Schlüsselwort, verwenden Sie den Qualifizierer"Umbenennen"
C4287|"*Ausdruck*": vorzeichenloser und negativer Konstante Konflikt
C4288|nicht dem Standard entsprechende Erweiterung: '*Namen*": Loop-Steuerelementvariable, die in der for-Schleife deklariert wird, außerhalb des for-Schleife; sie steht in Konflikt mit der Deklaration im äußeren Gültigkeitsbereich
C4289|nicht dem Standard entsprechende Erweiterung: '*Namen*": Loop-Steuerelementvariable, die in der for-Schleife deklariert wird, außerhalb des for-Schleife
C4293|"*Ausdruck*": Verschiebung negativ oder zu groß, ein nicht definiertes Verhalten
C4295|"*Typ*': Array ist zu klein, um ein abschließendes Nullzeichen enthalten.
C4296|"*Ausdruck*": Ausdruck ist immer *Wert*
C4297|"*Typ*': Funktion nicht zu einer Ausnahme jedoch davon ausgegangen, dass
C4298|"*Namen*': Bezeichner in der Typbibliothek"*Beschreibung*"ist bereits ein Makro; zum Umbenennen von ' __*Namen*"
C4299|"*Namen*': Bezeichner in der Typbibliothek"*Beschreibung*"ist ein Schlüsselwort; zum Umbenennen von ' __*Namen*"
C4302|"*Ausdruck*': Verkürzung von '*Typ*'to'*Typ*"
C4303|*Konvertierung* aus "*Typ*'to'*Typ*" ist veraltet, verwenden Sie Static_cast, __try_cast oder Dynamic_cast
C4314|Pragma-Parameter erwartet '32' oder '64' sein.
C4315|"*Typ*": "this-Zeiger für das Element"*Typ*"möglicherweise nicht ausgerichtet *Anzahl* wie vom Konstruktor erwartet
C4318|übergeben Konstante 0 (null) als Länge an memset
C4319|"*Ausdruck*": Null erweitern "*Typ*'to'*Typ*" größerem
C4321|generiert automatisch eine IID für die Schnittstelle "*Typ*"
C4322|automatische Generierung von CLSID für die Klasse*Typ*"
C4323|erneute Verwendung der registrierten CLSID für die Klasse*Typ*"
C4324|"*Typ*': Struktur wurde aufgrund von Ausrichtung Bezeichner aufgefüllt.
C4325|Attribute für Standardabschnitt "*Beschreibung*" ignoriert
C4326|Rückgabetyp "*Namen*'muss'*Typ*"anstelle von"*Typ*"
C4327|"*Ausdruck*': Dereferenzierungsausrichtung von LHS (*Anzahl*) ist größer als RHS (*Anzahl*)
C4328|"*Beschreibung*': Dereferenzierungsausrichtung des formalen Parameters *Anzahl* (*Anzahl*) ist größer als die tatsächliche Argument Ausrichtung (*Anzahl*)
C4329|Spezifizierer Ausrichtung wird für Enum ignoriert.
C4336|Importieren der übergreifenden Typbibliothek "*Bibliothek*"vor dem Import"*Beschreibung*"
C4337|übergreifenden Typbibliothek "*Bibliothek*'in'*Beschreibung*" wird automatisch importiert
C4338|#pragma *Beschreibung*: Standardabschnitt "*Abschnitt*" verwendet wird
C4339|"*Typ*': Verwendung eines undefinierten Typs erkannt werden in CLR/WinRT - Metadaten verwenden dieses Typs führt möglicherweise zu einer Laufzeitausnahme
C4353|nicht dem Standard entsprechende Erweiterung: Konstante 0 als Funktionsausdruck.  Verwenden Sie stattdessen die systeminterne '__noop'-Funktion
C4370|"*Deklaration*": Layout der Klasse wurde von einer früheren Version des Compilers aufgrund bessere Verpackung geändert
C4371|"*Deklaration*": Layout der Klasse möglicherweise geändert haben, von einer früheren Version des Compilers aufgrund bessere Verpackung des Members '*Member*"
C4373|"*Typ*": virtuelle Funktion überschreibt*Deklaration*", frühere Versionen des Compilers nicht überschrieben, wenn der Parameter nur durch Const/Volatile-Qualifizierer beinhalteten
C4387|"*Beschreibung*": wurde als
C4389|"*Ausdruck*': Konflikt zwischen signed/unsigned
C4391|"*Deklaration*': Falscher Rückgabetyp für systeminterne Funktion erwartet"*Typ*"
C4392|"*Deklaration*': falsche Anzahl von Argumenten für die systeminterne Funktion erwartet"*Anzahl*"Argumente
C4407|eine Umwandlung zwischen verschiedenen Zeiger auf Member-Darstellungen, möglicherweise Compiler fehlerhaftem Code generieren
C4420|"*Namen*': Operator nicht verfügbar ist, mit"*Namen*"stattdessen; laufzeitüberprüfung beeinträchtigt werden
C4440|Neudefinition der Aufrufkonvention von "*Beschreibung*'to'*Beschreibung*" ignoriert
C4442|eingebettete null-Terminator im __annotation-Argument.  Wert wird abgeschnitten.
C4444|"*Namen*": der obersten Ebene '__unaligned' ist in diesem Kontext nicht implementiert.
C4526|"*Typ*": virtuelle Funktion kann nicht statische Memberfunktion überschreiben "*Deklaration*" Außerkraftsetzung ignoriert, virtuelle Funktion wird ausgeblendet
C4531|C++-Ausnahmebehandlung ist nicht verfügbar für Windows CE. Verwenden Sie die strukturierte Ausnahmebehandlung
C4532|"*Beschreibung*":-Anweisungsblock Herausspringen *schließlich* Block verfügt über ein nicht definiertes Verhalten während der Abbruchbehandlung
C4533|Initialisierung von "*Deklaration*" wird übersprungen, indem Sie "Goto *Deklaration*"
C4534|"*Deklaration*" können nicht auf ein Standardkonstruktor für *Klasse* "*Typ*" aufgrund der Standardargument
C4535|calling _set_se_translator() requires /EHa
C4536|"*Beschreibung*': Typ größer als das Metadatenlimit von '*Anzahl*' Zeichen
C4537|"*Deklaration*': '.' auf nicht-UDT-Typ angewendet wird
C4542|Überspringen die Generierung von zusammengeführten eingefügter Text-Datei kann nicht geschrieben werden *Typ* Datei: "*Filename*": *Fehler*
C4543|Eingefügten Text wurde vom Attribut "keine\_Injected_text"
C4555|Der Ausdruck hat keine Auswirkungen; Ausdruck mit Nebeneffekten erwartet
C4557|"__assume' enthält den Effekt '*Effekt*"
C4558|Wert des Operanden "*Anzahl*"liegt außerhalb des Bereichs"*Anzahl* - *Anzahl*"
C4561|"__fastcall" nicht kompatibel mit der "/ Clr" Option: '__stdcall' konvertieren
C4562|vollständige Prototypen Funktionen sind erforderlich, mit der "/ Clr" Option: Konvertieren von "()", "(void)"
C4564|Methode "*Namen*" der *Klasse* "*Typ*'definiert den nicht unterstützten Standardparameter'*Parameter*"
C4584|"*Typ*': Basisklasse*Deklaration*"ist bereits eine Basisklasse, von"*Deklaration*"
C4608|Initialisieren mehrere Elemente von "Union": "*Typ*'und'*Typ*"
C4619|#pragma-Warnung: Es ist keine Warnungsnummer '*Anzahl*"
C4623|"*Typ*': Standardkonstruktor wurde implizit als gelöscht definiert.
C4624|"*Typ*": Destruktor wurde implizit als gelöscht definiert.
C4625|"*Typ*': Kopierkonstruktor wurde implizit als gelöscht definiert.
C4626|"*Typ*': Zuweisungsoperator wurde implizit als gelöscht definiert.
C4645|mit "Noreturn" deklarierte Funktion verfügt über eine return-Anweisung
C4646|mit "Noreturn" deklarierte Funktion verfügt über nicht-Void-Rückgabetyp
C4659|#pragma "*Beschreibung*': Verwendung von reservierten Segment"*Namen*"weist ein nicht definiertes Verhalten, verwenden Sie #pragma-Kommentar (Linker,...)
C4667|"*Deklaration*': keine Funktionsvorlage definiert, die entspricht erforderlichen Instanziierung
C4668|"*Namen*'ist nicht definiert als ein Präprozessormakro, ersetzen durch '0' für'*Wert*"
C4669|"*Ausdruck*': unsichere Konvertierung:"*Typ*"ist ein Objekt verwaltet/WinRT-Typ
C4674|"*Namen*" sollte als "static" deklariert werden und nur einen Parameter haben
C4680|"*Typ*': Co-Klasse gibt keine Standardschnittstelle
C4681|"*Typ*': Co-Klasse gibt eine Standardschnittstelle an, die eine Ereignisquelle ist keine
C4682|"*Typ*': kein direktionales Parameterattribut angegeben, Standardwert [in]
C4683|"*Deklaration*": Ereignisquelle hat einen 'Out'-Parameter, seien Sie äußerst vorsichtig, wenn mehrere Ereignishandler einbinden
C4684|"*Beschreibung*": Warnung!! Attribut kann dazu führen, dass ungültige codegenerierung: mit Vorsicht verwenden
C4685|"> >" erwartet. ">>" wurde beim Verarbeiten der Vorlagenparameter gefunden
C4700|nicht initialisierten lokalen Variablen '*Namen*"verwendet
C4701|möglicherweise nicht initialisierten lokalen Variablen '*Namen*"verwendet
C4702|unerreichbarer code
C4711|Funktion "*Namen*" für die automatische Inlineerweiterung ausgewählt
C4714|Funktion "*Deklaration*" als __forceinline markiert nicht inline
C4715|"*Funktion*': nicht alle Steuerelementpfade geben einen Wert zurück.
C4716|"*Funktion*': muss einen Wert zurückgeben
C4717|"*Funktion*': rekursiv für alle Steuerelementpfade Funktion führt dazu, dass Laufzeit Stapelüberlauf
C4718|"*Funktion*': rekursiver Aufruf besitzt keine Nebeneffekte, wird gelöscht
C4719|Doppelte Konstante gefunden wird, wenn Qfast angegeben - Verwendung "f" als Suffix an, dass einfache Genauigkeit
C4723|Mögliche Division durch 0
C4724|Mögliches Modulo durch 0 (Null)
C4725|Anweisung kann auf einigen Pentium-Prozessoren ungenau sein
C4757|Index ist ein großer Wert ohne Vorzeichen, wollten Sie eine negative Konstante?
C4772|#import auf einen Typ aus einer fehlenden Typbibliothek verwiesen wird; "*Beschreibung*" als Platzhalter verwendet
C4792|Funktion "*Funktion*" unter Verwendung von Sysimport deklariert und auf die verwiesen wird von systemeigenem Code; Importbibliothek ist zum Verknüpfen erforderlich
C4794|Segment der Variable für Thread-lokalen Speicher "*Namen*"geändert von"*Segment*'to'*Segment*"
C4798|systemeigener Code für p-Code-Funktion generiert "*Namen*" mit einem Ausnahmehandler oder entladungssemantik
C4799|Funktion "*Namen*' hat keine EMMS-Anweisung
C4803|"*Deklaration*': Die Raise-Methode wurde eine anderen Speicherklasse aus, der das Ereignis"*Deklaration*"
C4810|Wert von Pragma pack(show) == *Anzahl*
C4811|Wert von Pragma conform (ForScope, Show) == *Wert*
C4820|"*Typ*": "*Anzahl*' Bytes Abstand nach dem hinzugefügt *Typ* "*Typ*"
C4905|Breites Zeichenfolgenliteral umgewandelt "*Typ*"
C4906|Zeichenfolgenliteral umgewandelt "*Typ*"
C4912|"*Attribut*": Attribut weist ein nicht definiertes Verhalten für ein geschachteltes UDT
C4916|Um einen Dispid haben "*Typ*': eine Schnittstelle eingeführt werden müssen
C4917|"*Typ*': eine GUID kann nur eine Klasse, Schnittstelle oder ein Namespace zugeordnet werden
C4918|"*Zeichen*': Ungültiges Zeichen in der Pragma-Optimierungsliste
C4920|Enum *Namen* Member *Namen*=*Anzahl* bereits in Enumeration *Namen* als *Namen* = *Anzahl*
C4921|"*Namen*":-Attributwert "*Wert*" sollte nicht mehrfach angegeben werden
C4925|"*Deklaration*': Dispinterface-Methode kann nicht aus einem Skript aufgerufen werden
C4926|"*Deklaration*": Symbol ist bereits definiert: Attribute werden ignoriert
C4927|Unzulässige Konvertierung. mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen.
C4928|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen
C4929|"*Beschreibung*": Typbibliothek enthält eine Union; den Qualifizierer 'Embedded_idl' ignorieren
C4930|"*Deklaration*': Funktion mit Prototyp nicht aufgerufen (war eine Variablendefinition vorgesehen?)
C4931|Es wird angenommen, die Typbibliothek wurde erstellt für *Anzahl*-bit-Zeiger
C4932|__identifier (*Beschreibung*) und __identifier (*Beschreibung*) sind nicht differenzierbar.
C4934|"__delegate(multicast)" ist veraltet, verwenden Sie "stattdessen __delegate"
C4935|Assembly-Zugriffsspezifizierer geändert von "*Beschreibung*"
C4944|"*Namen*": Symbol aus kann nicht importiert "*Quelle*': als*Deklaration*" ist im aktuellen Gültigkeitsbereich bereits vorhanden.
C4945|"*Namen*": Symbol aus kann nicht importiert "*Quelle*': als*Deklaration*'wurde bereits importiert aus einer anderen Assembly'*Quelle*"
C4946|reinterpret_cast used between related classes: '*declaration*' and '*declaration*'
C4995|"*Namen*": Name wurde als veraltet #pragma markiert
C4996|"*Problem*": *Beschreibung*
C4997|"*Typ*': Coclass implementiert keine COM- oder Pseudoschnittstelle
C4998|Erwartung fehlgeschlagen: *Beschreibung*(*Anzahl*)

## <a name="see-also"></a>Siehe auch
[Compileroption WV](../../build/reference/compiler-option-warning-level.md)
[Compilerwarnungen, die standardmäßig deaktiviert sind](../../preprocessor/compiler-warnings-that-are-off-by-default.md)
[Warnung](../../preprocessor/warning.md)
