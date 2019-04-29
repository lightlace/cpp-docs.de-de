---
title: Typsystem (C++/CX)
ms.date: 02/03/2017
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
ms.openlocfilehash: fbc7a178621624e396c80509703ce1b5b4c19162
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392088"
---
# <a name="type-system-ccx"></a>Typsystem (C++/CX)

Die Windows-Runtime-Architektur, Sie können mithilfe C++ / CX-, Visual Basic, Visual C#- und JavaScript zu schreiben, apps und Komponenten, die direkt auf die Windows-API zugreifen und mit anderen Windows-Runtime-apps und-Komponenten zusammenarbeiten. Apps der universellen Windows-Plattform, die in C++ geschrieben sind, Kompilieren in systemeigenen Code, der direkt in der CPU ausgeführt wird. Apps der universellen Windows-Plattform, die in c# oder Visual Basic geschrieben werden Microsoft intermediate Language (MSIL) kompiliert, und führen in der common Language Runtime (CLR). Apps der universellen Windows-Plattform, die in JavaScript geschrieben sind, die in einer Laufzeit-Umgebung ausführen werden. Die Windows-Runtime--Betriebssystemkomponenten selbst sind in C++ geschrieben und als systemeigener Code ausgeführt. Alle diese Komponenten und apps der universellen Windows-Plattform kommunizieren direkt über die Windows-Runtime-anwendungsbinärdateischnittstelle (ABI).

Microsoft entwickelt, um Unterstützung für die Windows-Runtime in einem modernen C++-Idiom zu aktivieren, C++ / CX. C++ / CX stellt integrierte Basistypen und Implementierungen von grundlegenden Windows-Runtime-Typen, mit denen C++-apps und-Komponenten über die ABI mit apps zu kommunizieren, die in anderen Sprachen geschrieben wurden. Sie können alle Windows-Runtime nutzen oder Erstellen von Klassen, Strukturen, Schnittstellen und andere benutzerdefinierte Typen, die von anderen apps der universellen Windows-Plattform und den Komponenten genutzt werden können. eine universelle Windows-Plattform-app, die in C++ geschrieben ist c++ / CX kann auch verwenden reguläre C++-Klassen und Strukturen, solange sie nicht über öffentliche Barrierefreiheit verfügen.

Eine ausführliche Diskussion der C++/CX-Sprachprojektion und ihrer Funktionsweise finden Sie in folgenden Blogbeiträgen:

1. [C++ / CX Teil 0 von \[n\]: Eine Einführung in](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction)

1. [C++ / CX Teil 1 von \[n\]: Eine einfache Klasse](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class)

1. [C++ / CX Teil 2 von \[n\]: Typen, die mit Hut](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats)

1. [C++ / CX Teil 3 von \[n\]: Im Bau](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)

1. [C++ / CX Teil 4 von \[n\]: Statische Memberfunktionen](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions)

## <a name="windows-metadata-winmd-files"></a>Windows-Metadatendateien (.winmd)

Wenn Sie eine universelle Windows-Plattform-app, die in C++ geschrieben ist kompilieren, der Compiler erzeugt die ausführbare Datei im systemeigenen Computercode und generiert auch eine separate Windows-Metadatendatei (.winmd)-Datei mit Beschreibungen der öffentlichen Windows-Runtime-Typen, die Klassen, Strukturen, Enumerationen, Schnittstellen, parametrisierte Schnittstellen und Delegaten enthalten. Das Format der Metadaten ähnelt dem Format, das in den .NET Framework-Assemblys verwendet wird.  In einer C++-Komponente enthält die WinMD-Datei nur Metadaten. Der ausführbare Code befindet sich in einer separaten Datei. Dies ist der Fall für die Windows-Runtime-Komponenten, die in Windows enthalten sind. Der WinMD-Dateiname muss übereinstimmen oder ein Präfix des Stammnamenspace im Quellcode sein. (Für die .NET Framework-Sprachen sind in einer WinMD-Datei wie in einer .NET Framework-Assembly sowohl Code als auch Metadaten enthalten.)

Die Metadaten in der WinMD-Datei stellen die veröffentlichte Oberfläche des Codes dar. Veröffentlichte Typen werden für andere universelle Windows-Plattformen unabhängig davon, welcher Sprache diese anderen apps geschrieben sind. Aus diesem Grund kann die Metadaten oder der veröffentlichte Code nur Typen, die durch die Windows-Runtime-Typsystem angegebene enthalten. C++-spezifische Sprachkonstrukte wie reguläre Klassen, Arrays, Vorlagen oder STL-Container können nicht in Metadaten veröffentlicht werden, da eine JavaScript- oder C#-Clientapp sie nicht verwenden kann.

Ob ein Typ oder eine Methode in den Metadaten sichtbar ist, hängt davon ab, welche Zugriffsmodifizierer auf diesen Typ oder diese Methode angewendet werden. Um sichtbar zu sein, muss ein Typ sowohl in einem Namespace als auch als öffentlich deklariert werden. Eine nicht öffentliche Verweisklasse ist als interner Hilfsprogrammtyp im Code zugelassen, wird jedoch nicht in den Metadaten angezeigt. Es sind jedoch auch in einer öffentlichen Verweisklasse nicht unbedingt alle Member sichtbar. Die folgende Tabelle enthält die Beziehung zwischen C++-zugriffsspezifizierern in einer öffentlichen Verweisklasse und Sichtbarkeit der Windows-Runtime-Metadaten:

|||
|-|-|
|**In Metadaten veröffentlicht**|**Nicht in Metadaten veröffentlicht**|
|public|private|
|protected|internal|
|public protected|private protected|

Mit dem **Objektkatalog** können Sie den Inhalt von WinMD-Dateien anzeigen. Die Windows-Runtime-Komponenten, die in Windows enthalten sind, sind in der Datei Windows.winmd. Die Datei default.winmd enthält die grundlegenden Typen, die in C++ verwendet werden c++ / CX und platform.winmd enthält zusätzliche Typen von der Plattform-Namespace. Standardmäßig sind diese drei winmd-Dateien in jedem C++-Projekt für universelle Windows-Plattform-apps enthalten.

> [!TIP]
> Die im [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md) vorhandenen Typen sind in der WinMD-Datei nicht sichtbar, da sie nicht öffentlich sind. Es sind private C++-spezifische Implementierungen der Schnittstellen, die in `Windows::Foundation::Collections`definiert sind. Eine Windows-Runtime-app, die in JavaScript oder c# geschrieben ist nicht wissen, was eine [:: Vector Class](../cppcx/platform-collections-vector-class.md) ist, aber sie kann eine `Windows::Foundation::Collections::IVector`. Die `Platform::Collections` -Typen werden in der Datei collection.h definiert.

## <a name="windows-runtime-type-system-in-ccx"></a>Windows-Runtime-Typsystem in C++ / CX

Die folgenden Abschnitte beschreiben die wichtigsten Funktionen von der Windows-Runtime-Typsystem und wie diese unterstützt werden, in C++ / CX.

### <a name="namespaces"></a>Namespaces

Alle Windows-Runtime-Typen müssen innerhalb eines Namespace deklariert werden. die Windows-API selbst ist nach Namespaces organisiert. Eine WinMD-Datei muss denselben Namen wie der Stammnamespace haben. Zum Beispiel kann eine Klasse namens A.B.C.MyClass nur instanziiert werden, wenn sie in einer Metadatendatei definiert ist, die A.winmd oder A.B.winmd oder A.B.C.winmd heißt. Der Name der DLL muss nicht mit dem Namen der WINMD-Datei übereinstimmen.

Die Windows-API selbst wurde überarbeitet und präsentiert sich nun als gut gestaltete Klassenbibliothek, die nach Namespaces organisiert ist.  Alle Windows-Runtime-Komponenten werden in den Windows-Namespaces deklariert.

Weitere Informationen finden Sie unter [Namespaces und Typsichtbarkeit](../cppcx/namespaces-and-type-visibility-c-cx.md).

### <a name="fundamental-types"></a>Grundlegende Typen

Die Windows-Runtime definiert die folgenden grundlegenden Typen, UInt8, Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, Double, Char16, Boolean und Zeichenfolge. C++ / CX unterstützt die elementaren numerischen Typen im Standardnamespace als uint16, uint32, uint64, int16, int32, int64, float32, float64 und char16. Boolean und String werden auch im Plattformnamespace definiert.

C++ / CX definiert auch uint8, gleich `unsigned char`, die in der Windows-Runtime nicht unterstützt und kann nicht in öffentlichen APIs verwendet werden.

Ein elementarer Typ kann auf NULL festlegbar gemacht werden, indem er in einer [Platform::IBox Interface](../cppcx/platform-ibox-interface.md) -Schnittstelle umgebrochen wird. Weitere Informationen finden Sie unter [Wertklassen und Strukturen](../cppcx/value-classes-and-structs-c-cx.md)definiert sind.

Weitere Informationen über grundlegende Typen finden Sie unter [Grundlegende Typen](../cppcx/fundamental-types-c-cx.md)

### <a name="strings"></a>Zeichenfolgen

Eine Windows-Runtime-Zeichenfolge ist eine unveränderliche Sequenz von 16-Bit-UNICODE-Zeichen. Eine Windows-Runtime-Zeichenfolge wird als projiziert `Platform::String^`. Diese Klasse stellt Methoden zum Erstellen und Bearbeiten von Zeichenfolgen zur Verfügung und ermöglicht, Zeichenfolgen in und aus `wchar_t`zu konvertieren.

Weitere Informationen finden Sie unter [Zeichenfolgen](../cppcx/strings-c-cx.md)definiert sind.

### <a name="arrays"></a>Arrays

Die Windows-Runtime unterstützt 1-dimensionale Arrays beliebigen Typs. Arrays von Arrays werden nicht unterstützt.  In C++ / CX werden Windows-Runtime-Arrays werden als projiziert die [Platform:: Array-Klasse](../cppcx/platform-array-class.md).

Weitere Informationen finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)

### <a name="ref-classes-and-structs"></a>Referenzklassen und Strukturen

Eine Windows-Runtime-Klasse wird voraussichtlich in C++ / CX als Verweisklasse oder Referenzstruktur, da diese nach Verweis kopiert werden. Die Speicherverwaltung für Verweisklassen und Referenzstrukturen erfolgt mittels der Verweiszählung transparent. Wenn der letzte Verweis auf ein Objekt außerhalb des gültigen Bereichs ist, wird das Objekt vernichtet. Eine Verweisklasse oder Referenzstruktur

- kann als Member Konstruktoren, Methoden, Eigenschaften und Ereignisse enthalten. Diese Member können einen öffentlichen, privaten, geschützten oder internen Zugriff aufweisen.

- kann private geschachtelte Enumerations-, Struktur- oder Klassendefinitionen enthalten.

- kann direkt von einer Basisklasse erben und eine beliebige Anzahl von Schnittstellen implementieren. Alle Verweisklassen sind implizit konvertierbar in die [Platform::Object Class](../cppcx/platform-object-class.md) und können ihre virtuellen Methoden wie [Object::ToString](../cppcx/platform-object-class.md#tostring)überschreiben.

Eine Verweisklasse, die über einen öffentlichen Konstruktor verfügt, muss als versiegelt deklariert werden, um eine weitere Ableitung zu verhindern.

Weitere Informationen finden Sie unter [Referenzklassen und Strukturen](../cppcx/ref-classes-and-structs-c-cx.md)

### <a name="value-classes-and-structs"></a>Wertklassen und Strukturen

Eine Wertklasse oder Wertstruktur stellt eine grundlegende Datenstruktur dar und enthält nur Felder, die Wertklassen, Wertstrukturen oder vom Typ `Platform::String^`sein können.  Wertstrukturen und Wertklassen werden nach Wert kopiert.

Eine Wertstruktur kann auf NULL festlegbar gemacht werden, indem sie in einer IBox-Schnittstelle umgebrochen wird.

Weitere Informationen finden Sie unter [Wertklassen und Strukturen](../cppcx/value-classes-and-structs-c-cx.md)definiert sind.

### <a name="partial-classes"></a>Teilklassen

Mit der Funktion der Teilklassen kann eine Klasse für mehrere Dateien definiert werden. Sie wird hauptsächlich dazu verwendet, um es Codegenerierungstools wie dem XAML-Editor ermöglichen, eine Datei zu ändern, ohne dass die Datei, die Sie bearbeiten, angefasst werden muss.

Weitere Informationen finden Sie unter [Teilklassen](../cppcx/partial-classes-c-cx.md)

### <a name="properties"></a>Eigenschaften

Eine Eigenschaft einen öffentlichen Datenmember eines beliebigen Windows-Runtime-Typs ist, und es wird als eine get-/Set-Methodenpaar implementiert. Clientcode interpretiert eine Eigenschaft beim Zugriff als öffentliches Feld. Eine Eigenschaft, die keinen benutzerdefinierten GET- oder SET-Code erfordert, wird als *trivial-Eigenschaft* bezeichnet und kann ohne explizite GET- oder SET-Methoden deklariert werden.

Weitere Informationen finden Sie unter [Eigenschaften](../cppcx/properties-c-cx.md)definiert sind.

### <a name="windows-runtime-collections-in-ccx"></a>Windows-Runtime-Auflistungen in C++ / CX

Die Windows-Runtime definiert einen Satz von Schnittstellen für Auflistungstypen, die jede Sprache auf eigene Weise implementiert. C++ / CX bietet Implementierungen in der [:: Vector Class](../cppcx/platform-collections-vector-class.md), [Platform::Collections::Map Klasse](../cppcx/platform-collections-map-class.md), und anderen ähnlichen konkreten Auflistungstypen, die mit kompatibel sind ihre Standard Entsprechungen der Standardvorlagenbibliothek (STL).

Weitere Informationen finden Sie unter [Sammlungen](../cppcx/collections-c-cx.md).

### <a name="template-ref-classes"></a>Vorlagenverweisklassen

Private und interne Verweisklassen können vorlagenbasiert und spezialisiert sein.

Weitere Informationen finden Sie unter [Vorlagenverweisklassen](../cppcx/template-ref-classes-c-cx.md)definiert sind.

### <a name="interfaces"></a>Schnittstellen

Eine Windows-Runtime-Schnittstelle definiert einen Satz von öffentlichen Eigenschaften, Methoden und Ereignisse, die eine Verweisklasse oder Referenzstruktur implementieren muss, wenn es von der Schnittstelle erbt.

Weitere Informationen finden Sie unter [Schnittstellen](../cppcx/interfaces-c-cx.md).

### <a name="enums"></a>Enumerationen

Eine Enumerationsklasse in Windows-Runtime ähnelt eine Bereichsbezogene Enumeration in C++. Der zugrunde liegende Typ ist int32, es sei denn, das Attribut [Flags] kommt zur Anwendung. Dann ist der zugrunde liegende Typ uint32.

Weitere Informationen finden Sie unter [Enumerationen](../cppcx/enums-c-cx.md)definiert sind.

### <a name="delegates"></a>Delegaten

Ein Delegat in der Windows-Runtime ist analog zu einem Std:: Function-Objekt in C++. Es ist eine spezielle Verweisklasse, mit deren Hilfe vom Client bereitgestellte Funktionen aufgerufen werden, die kompatible Signaturen enthalten.  Delegaten werden am häufigsten als Typ eines Ereignisses in der Windows-Runtime verwendet.

Weitere Informationen finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md).

### <a name="exceptions"></a>Ausnahmen

In C++/CX können Sie benutzerdefinierte Ausnahmetypen, [std::exception](../standard-library/exception-class.md) -Typen und [Platform::Exception](../cppcx/platform-exception-class.md) -Typen abfangen.

Weitere Informationen finden Sie unter [Ausnahmen](../cppcx/exceptions-c-cx.md)definiert sind.

### <a name="events"></a>Ereignisse

Ein Ereignis ist ein öffentlicher Member in einer Verweisklasse oder einer Referenzstruktur mit einem Delegattyp als Typ. Ein Ereignis kann nur durch die besitzende Klasse aufgerufen, d. h. ausgelöst werden. Clientcode kann jedoch eigene Funktionen bereitstellen, die als Ereignishandler bezeichnet werden. Diese Ereignishandler werden aufgerufen, wenn die besitzende Klasse das Ereignis auslöst.

Weitere Informationen finden Sie unter [Ereignisse](../cppcx/events-c-cx.md)definiert sind.

### <a name="casting"></a>Umwandlung

C++/CX unterstützt die Standard-C++-Umwandlungsoperatoren [static_cast](../cpp/static-cast-operator.md), [dynamic_cast](../cpp/dynamic-cast-operator.md)und [reinterpret_cast](../cpp/reinterpret-cast-operator.md)sowie den Operator **safe_cast** , der C++/CX-spezifisch ist.

Weitere Informationen finden Sie unter [Umwandlung](../cppcx/casting-c-cx.md)definiert sind.

### <a name="boxing"></a>Boxing

Eine geschachtelte Variable ist ein Werttyp, der in einem Referenztyp in Situationen umschlossen wird, in denen eine Verweissemantik erforderlich ist.

Weitere Informationen finden Sie unter [Boxing](../cppcx/boxing-c-cx.md)definiert sind.

### <a name="attributes"></a>Attribute

Ein Attribut ist ein Metadatenwert, der kann auf alle Windows-Runtime-Typ oder Typmember angewendet werden und kann zur Laufzeit überprüft werden. Die Windows-Runtime definiert einen Satz allgemeiner Attribute in der `Windows::Foundation::Metadata` Namespace. Benutzerdefinierte Attribute in öffentlichen Schnittstellen werden nicht in dieser Version von Windows-Runtime unterstützt.

## <a name="api-deprecation"></a>API-Veraltung

Beschreibt, wie öffentliche API als mit dem gleichen Attribut, das von den Windows-Runtime-System-Typen verwendet wird als veraltet markiert.

Weitere Informationen finden Sie unter [einstufen von Typen und Membern als veraltet](../cppcx/deprecating-types-and-members-c-cx.md).

## <a name="see-also"></a>Siehe auch

[Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)
