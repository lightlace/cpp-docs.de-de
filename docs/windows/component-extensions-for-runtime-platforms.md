---
title: Komponentenerweiterungen für .NET- und UWP
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
ms.openlocfilehash: e9586244c9e2293ba6b484efb158fc3a2529c0ea
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57814487"
---
# <a name="component-extensions-for-net-and-uwp"></a>Komponentenerweiterungen für .NET- und UWP

Der C++-Standard ermöglicht Compileranbieter-standarderweiterungen für die Sprache angeben. Microsoft bietet Erweiterungen, mit denen Sie die systemeigenen C++-Code, Code zu verbinden, die auf .NET Framework oder universelle Windows-Plattform (UWP) ausgeführt wird. Die Erweiterungen für .NET heißen C++ / CLI und erzeugt Code, der in .NET ausgeführt wird, verwaltete ausführungsumgebung, die die Common Language Runtime (CLR) aufgerufen wird. Die UWP-Erweiterungen heißen C++ / CX und erzeugen Sie nativen Code.

> [!NOTE]
> Für neue Anwendungen empfehlen wir mithilfe C++ / WinRT statt C++ / CX. C++ / WinRT ist eine neue "," standard C ++ 17-sprachprojektion für Windows-Runtime-APIs. Wir weiterhin zur Unterstützung von C++ / CX- und WRL, jedoch dringend empfohlen, neue Anwendungen C++ mithilfe / WinRT. Weitere Informationen finden Sie unter [C++ / WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).

### <a name="two-runtimes-one-set-of-extensions"></a>Zwei Laufzeiten, ein Satz von Erweiterungen

C++ / CLI erweitert den ISO/ANSI C++-Standard und ist definiert unter ECMA-C++ / CLI-Standard. Weitere Informationen finden Sie unter [.NET-Programmierung mit C++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

C++ / CX-Erweiterungen sind eine Teilmenge der C++ / CLI. Obwohl die Erweiterungssyntax in den meisten Fällen identisch ist, der Code, der generiert wird, hängt von, ob Sie angeben der `/ZW` -Compileroption verwenden, um die auf UWP, ausgerichtet oder `/clr` Option aus, um die .NET als Ziel. Diese Schalter werden automatisch festgelegt, wenn Sie Visual Studio zur Erstellung eines Projekt verwenden.

## <a name="data-type-keywords"></a>Datentyp-Schlüsselworte

Die spracherweiterungen schließen *aggregieren Schlüsselwörter*, die aus zwei durch Leerraum getrennte Token bestehen. Die Token haben möglicherweise eine bestimmte Bedeutung, wenn sie einzeln verwendet werden, und eine andere Bedeutung, wenn sie zusammen verwendet werden. Beispielsweise ist das Wort "ref" ein normaler Bezeichner und das Wort "class" ein Schlüsselwort, das eine systemeigene Klasse deklariert. Aber wenn diese Wörter kombiniert werden, um **Verweisklasse**, das resultierende aggregatschlüsselwort einer Entität, die als bekannt ist, eine *-Runtime-Klasse*.

Die Erweiterungen enthalten auch *kontextbezogene* Schlüsselwörter. Ein Schlüsselwort wird abhängig von der Art der Anweisung, in der es enthalten ist, und seiner Platzierung in dieser Anweisung als kontextbezogen behandelt. Beispielsweise kann das Token "property" ein Bezeichner sein oder es kann eine spezielle Art eines öffentlichen Klassenmembers deklarieren.

In der folgenden Tabelle sind Schlüsselwörter in der C++-Spracherweiterung aufgeführt.

|Stichwort|Kontextbezogen|Zweck|Referenz|
|-------------|-----------------------|-------------|---------------|
|**REF-Klasse**<br /><br /> **ref struct**|Nein|Deklariert eine Klasse.|[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)|
|**Wertklasse**<br /><br /> **wertstruktur**|Nein|Deklariert eine Wertklasse.|[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)|
|**Schnittstellenklasse**<br /><br /> **Interface-Struktur**|Nein|Deklariert eine Schnittstelle.|[Schnittstellenklasse](../windows/interface-class-cpp-component-extensions.md)|
|**Enumerationsklasse**<br /><br /> **Enum-Struktur**|Nein|Deklariert eine Enumeration.|[Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md)|
|**Eigenschaft**|Ja|Deklariert eine Eigenschaft.|[Eigenschaft](../windows/property-cpp-component-extensions.md)|
|**delegate**|Ja|Deklariert einen Delegaten.|[Delegat (C++/CLI und C++/CX)](../windows/delegate-cpp-component-extensions.md)|
|**event**|Ja|Deklariert ein Ereignis.|[event](../windows/event-cpp-component-extensions.md)|

## <a name="override-specifiers"></a>Überschreibungsspezifizierer

Sie können die folgenden Schlüsselwörter verwenden, um das Überschreibungsverhalten für Ableitung zu qualifizieren. Obwohl die **neue** Schlüsselwort stellt keine Erweiterung von C++, die es hier aufgeführt, da es in einem zusätzlichen Kontext verwendet werden kann. Einige Bezeichner sind auch für die systemeigene Programmierung gültig. Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren von Überschreibungsbezeichnern in nativen Kompilierungen (C++ / CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

|Stichwort|Kontextbezogen|Zweck|Referenz|
|-------------|-----------------------|-------------|---------------|
|**abstract**|Ja|Gibt an, dass Funktionen oder Klassen abstrakt sind.|[abstract](../windows/abstract-cpp-component-extensions.md)|
|**new**|Nein|Gibt an, dass eine Funktion keine Überschreibung einer Basisklassenversion ist.|[New (neuer Slot in Vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|
|**override**|Ja|Gibt an, dass eine Methode eine Überschreibung einer Basisklassenversion sein muss.|[override](../windows/override-cpp-component-extensions.md)|
|**sealed**|Ja|Verhindert, dass Klassen als Basisklassen verwendet werden.|[sealed](../windows/sealed-cpp-component-extensions.md)|

## <a name="keywords-for-generics"></a>Schlüsselwörter für Generika

Die folgenden Schlüsselwörter wurden hinzugefügt, um generische Typen zu unterstützen. Weitere Informationen finden Sie unter [Generika](../windows/generics-cpp-component-extensions.md).

|Stichwort|Kontextbezogen|Zweck|
|-------------|-----------------------|-------------|
|**generic**|Nein|Definiert einen generischen Typ.|
|**where**|Ja|Gibt die Einschränkungen an, die für einen generischen Typparameter angewendet werden.|

## <a name="miscellaneous-keywords"></a>Sonstige Schlüsselwörter

Die folgenden Schlüsselwörter wurden den C++-Erweiterungen hinzugefügt.

|Stichwort|Kontextbezogen|Zweck|Referenz|
|-------------|-----------------------|-------------|---------------|
|**finally**|Ja|Gibt das Standardausnahmebehandlungsverhalten an.|[Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)|
|**for each in**|Nein|Listet die Elemente einer Auflistung auf.|[for each in](../dotnet/for-each-in.md)|
|**gcnew**|Nein|Ordnet Typen auf dem Heap der Garbage Collection zu. Verwenden Sie anstelle von **neue** und **löschen**.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**neue ref**|Ja|Ordnet einen Windows-Runtime-Typ. Verwenden Sie anstelle von **neue** und **löschen**.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**initonly**|Ja|Gibt an, dass ein Member nur in der Deklaration oder in einem statischen Konstruktor initialisiert werden kann.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|
|**literal**|Ja|Erstellt eine literale Variable.|[literal](../windows/literal-cpp-component-extensions.md)|
|**nullptr**|Nein|Gibt an, dass ein Handle oder ein Zeiger nicht auf ein Objekt zeigt.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|

## <a name="template-constructs"></a>Vorlagenkonstrukte

Die folgenden Sprachkonstrukte werden nicht als Schlüsselwörter, sondern als Vorlagen implementiert. Wenn Sie die `/ZW`-Compileroption angeben, werden sie im `lang`-Namespace definiert. Wenn Sie die `/clr`-Compileroption angeben, werden sie im `cli`-Namespace definiert.

|Stichwort|Zweck|Referenz|
|-------------|-------------|---------------|
|**array**|Deklariert einen Array.|[Arrays](../windows/arrays-cpp-component-extensions.md)|
|**interior_ptr**|(Nur CLR:) Zeigt auf Daten in einem Referenztyp.|[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)|
|**pin_ptr**|(Nur CLR:) Zeigt auf CLR-Referenztypen, um das Garbage Collection-System vorübergehend zu unterdrücken.|[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)|
|**safe_cast**|Bestimmt die optimale Umwandlungsmethode für einen Laufzeittyp und führt diese aus.|[safe_cast](../windows/safe-cast-cpp-component-extensions.md)|
|**typeid**|(Nur CLR:) Ruft ein <xref:System.Type?displayProperty=fullName>-Objekt ab, das den angegebenen Typ oder das angegebene Objekt beschreibt.|[typeid](../windows/typeid-cpp-component-extensions.md)|

## <a name="declarators"></a>Deklaratoren

Die folgenden Typdeklaratoren weisen die Laufzeit an, die Lebensdauer und das Löschen von zugeordneten Objekten automatisch zu verwalten.

|Operator|Zweck|Referenz|
|--------------|-------------|---------------|
|`^`|Deklariert ein Handle für ein Objekt an. d. h. ein Zeiger auf ein Windows-Runtime oder CLR-Objekt, das automatisch gelöscht wird, wenn es nicht mehr verwendbar ist.|[Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|
|`%`|Deklariert ein Nachverfolgungsverweis an; d. h. einen Verweis auf ein Windows-Runtime oder CLR-Objekt, das automatisch gelöscht wird, wenn es nicht mehr verwendbar ist.|[Nachverfolgungsverweisoperator](../windows/tracking-reference-operator-cpp-component-extensions.md)|

## <a name="additional-constructs-and-related-topics"></a>Zusätzliche Konstrukte und verwandte Themen

In diesem Abschnitt werden weitere Programmierungskonstrukte sowie Themen aufgeführt, die die CLR betreffen.

|Thema|Beschreibung|
|-----------|-----------------|
|[__identifier (C++/CLI)](../windows/identifier-cpp-cli.md)|(Windows-Runtime und CLR) Ermöglicht die Verwendung von Schlüsselwörtern als Bezeichner.|
|[Variable Argumentlisten (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows-Runtime und CLR) Aktiviert eine Funktion, die eine Variable Anzahl von Argumenten akzeptieren.|
|[.NET Framework-Entsprechungen der nativen Typen in C++ (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|Listet die CLR-Typen auf, die anstelle von ganzzahligen C++-Typen verwendet werden.|
|[appdomain](../cpp/appdomain.md) **__declspec** modifier|**__declspec** Modifizierer, der vorgibt, dass die statische und globale Variablen vorhanden sind.|
|[C-stilartige Umwandlungen mit/CLR (C++ / CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)|Beschreibt, wie Umwandlungen im C-Stil interpretiert werden.|
|[__clrcall](../cpp/clrcall.md) Aufrufkonvention|Gibt die CLR-kompatible Aufrufkonvention an.|
|`__cplusplus_cli`|[Vordefinierte Makros](../preprocessor/predefined-macros.md)|
|[Benutzerdefinierte Attribute](../windows/custom-attributes-cpp.md)|Beschreibt, wie eigene CLR-Attribute definiert werden.|
|[Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)|Stellt eine Übersicht über die Ausnahmebehandlung bereit.|
|[Explizite Überschreibungen](../windows/explicit-overrides-cpp-component-extensions.md)|Zeigt, wie Memberfunktionen beliebige Member überschreiben können.|
|[Friend-Assemblys (C++)](../dotnet/friend-assemblies-cpp.md)|Erläutert, wie eine Clientassembly auf alle Typen in einer Assemblykomponente zugreifen kann.|
|[Boxing](../windows/boxing-cpp-component-extensions.md)|Veranschaulicht die Bedingungen, unter denen Werttypen geschachtelt werden.|
|[Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Erläutert, wie Eigenschaften von Typen zur Kompilierzeit erkannt werden.|
|[verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) Pragmas|Veranschaulicht, wie verwaltete und nicht verwaltete Funktionen in demselben Modul zusammen verwendet werden können.|
|[Prozess](../cpp/process.md) **__declspec** Modifizierer|**__declspec** Modifizierer, der vorgibt, dass die statische und globale Variablen pro Prozess vorhanden sein.|
|[Reflexion (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Zeigt die CLR-Version von Informationen zum Laufzeittyp.|
|[String](../windows/string-cpp-component-extensions.md)|Erläutert die Compilerkonvertierung von Zeichenfolgenliteralen zu <xref:System.String>.|
|[Typweiterleitung (C++/CLI)](../windows/type-forwarding-cpp-cli.md)|Ermöglicht das Verschieben eines Typs aus einer bereits bereitgestellten Assembly in eine andere Assembly, sodass Clientcode nicht neu kompiliert werden muss.|
|[Benutzerdefinierte Attribute](../windows/user-defined-attributes-cpp-component-extensions.md)|Veranschaulicht benutzerdefinierte Attribute.|
|[#using-Direktive](../preprocessor/hash-using-directive-cpp.md)|Importiert externe Assemblys.|
|[XML-Dokumentation](../build/reference/xml-documentation-visual-cpp.md)|Erläutert, XML-basierte Codedokumentation mithilfe von  [ /doc (Verarbeiten von Dokumentationskommentaren) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)|

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)