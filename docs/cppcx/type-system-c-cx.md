---
title: "Typsystem (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
caps.latest.revision: 28
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 28
---
# Typsystem (C++/CX)
Mithilfe der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Architektur können Sie [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], Visual Basic, Visual C\# und JavaScript verwenden, um Apps und Komponenten zu erstellen, die direkt auf die Windows\-API zugreifen und mit anderen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Apps und \-Komponenten zusammenarbeiten. In C\+\+ geschriebene [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps werden in systemeigenen Code kompiliert, der direkt in der CPU ausgeführt wird. In C\# oder Visual Basic geschriebene [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps werden in MSIL \(Microsoft Intermediate Language\) kompiliert und in Common Language Runtime ausgeführt \(CLR\). In JavaScript geschriebene [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps werden in einer Laufzeitumgebung ausgeführt. Die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Betriebssystemkomponenten selbst sind in C\+\+ geschrieben und werden als systemeigener Code ausgeführt. Alle diese Komponenten und [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps kommunizieren direkt über die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-ABI \(Application Binary Interface \= Binärschnittstelle\).  
  
 Damit [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] in einer modernen C\+\+\-Sprache unterstützt werden kann, wurden von Microsoft [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) entwickelt.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] stellt integrierte Basistypen und Implementierungen von grundlegenden [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen zur Verfügung, mit denen C\+\+\-Apps und \-Komponenten über die ABI mit den in anderen Sprachen geschriebenen Apps kommunizieren können. Sie können jeden [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typ nutzen oder Klassen, Strukturen, Schnittstellen und andere benutzerdefinierte Typen erstellen, die von anderen [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps und \-Komponenten verwertet werden können. Eine in [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] geschriebene [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-App kann auch reguläre C\+\+\-Klassen und Strukturen verwenden, solange diese ohne öffentlichen Zugriff sind.  
  
 Eine ausführliche Diskussion der C\+\+\/CX\-Sprachprojektion und ihrer Funktionsweise finden Sie in folgenden Blogbeiträgen:  
  
1.  [C\+\+\/CX Teil 0 von \[n\]: Einführung](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C\+\+\/CX Teil 0 von \[n\]: Einführung](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C\+\+\/CX Teil 2 von \[n\]: Typen mit Hut](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C\+\+\/CX Teil 3 von \[n\]: Baustelle](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C\+\+\/CX Teil 4 von \[n\]: Statische Memberfunktionen](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)  
  
## Windows\-Metadatendateien \(.winmd\)  
 Wenn Sie eine [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App kompilieren, die in C\+\+ geschrieben ist, wird vom Compiler die ausführbare Datei im systemeigenen Computercode generiert. Ferner wird eine separate Windows\-Metadatendatei \(.winmd\) generiert, die die Beschreibungen der öffentlichen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen enthält, zu denen Klassen, Strukturen, Enumerationen, Schnittstellen, parametrisierte Schnittstellen und Delegaten gehören. Das Format der Metadaten ähnelt dem Format, das in den .NET Framework\-Assemblys verwendet wird.  In einer C\+\+\-Komponente enthält die WinMD\-Datei nur Metadaten. Der ausführbare Code befindet sich in einer separaten Datei. Dies ist bei den [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten der Fall, die in Windows enthalten sind. Der WinMD\-Dateiname muss übereinstimmen oder ein Präfix des Stammnamenspace im Quellcode sein. \(Für die .NET Framework\-Sprachen sind in einer WinMD\-Datei wie in einer .NET Framework\-Assembly sowohl Code als auch Metadaten enthalten.\)  
  
 Die Metadaten in der WinMD\-Datei stellen die veröffentlichte Oberfläche des Codes dar. Veröffentlichte Typen werden von anderen Apps mit [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] erkannt, unabhängig davon, in welcher Sprache diese anderen Apps geschrieben sind. Daher können die Metadaten oder der veröffentlichte Code nur Typen enthalten, die vom [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typsystem definiert sind. C\+\+\-spezifische Sprachkonstrukte wie reguläre Klassen, Arrays, Vorlagen oder STL\-Container können nicht in Metadaten veröffentlicht werden, da eine JavaScript\- oder C\#\-Clientapp sie nicht verwenden kann.  
  
 Ob ein Typ oder eine Methode in den Metadaten sichtbar ist, hängt davon ab, welche Zugriffsmodifizierer auf diesen Typ oder diese Methode angewendet werden. Um sichtbar zu sein, muss ein Typ sowohl in einem Namespace als auch als öffentlich deklariert werden. Eine nicht öffentliche Verweisklasse ist als interner Hilfsprogrammtyp im Code zugelassen, wird jedoch nicht in den Metadaten angezeigt. Es sind jedoch auch in einer öffentlichen Verweisklasse nicht unbedingt alle Member sichtbar. In der folgenden Tabelle wird die Beziehung zwischen C\+\+\-Zugriffsspezifizierern in einer öffentlichen Verweisklasse und der Metadatensichtbarkeit von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] aufgeführt:  
  
|||  
|-|-|  
|**In Metadaten veröffentlicht**|**Nicht in Metadaten veröffentlicht**|  
|public|private|  
|protected|internal|  
|public protected|private protected|  
  
 Mit dem **Objektkatalog** können Sie den Inhalt von WinMD\-Dateien anzeigen. Die in Windows enthaltenen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten befinden sich in der Datei Windows.winmd. Die Datei default.winmd enthält die grundlegenden Typen, die in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] verwendet werden. Die Datei platform.winmd enthält zusätzliche Typen von dem Plattform\-Namespace. Diese drei WinMD\-Dateien sind standardmäßig in jedem für [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps zur Verfügung stehenden C\+\+\-Projekt enthalten.  
  
> [!TIP]
>  Die im [Platform::Collections\-Namespace](../cppcx/platform-collections-namespace.md) vorhandenen Typen sind in der WinMD\-Datei nicht sichtbar, da sie nicht öffentlich sind. Es sind private C\+\+\-spezifische Implementierungen der Schnittstellen, die in `Windows::Foundation::Collections` definiert sind. Eine in JavaScript oder C\# geschriebene [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-App kann [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md) nicht interpretieren, aber sie kann `Windows::Foundation::Collections::IVector` nutzen. Die `Platform::Collections`\-Typen werden in der Datei collection.h definiert.  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typsystem in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 In den folgenden Abschnitten werden die Hauptfunktionen des [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typsystems beschrieben. Es wird auch erläutert, wie diese Funktionen in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] unterstützt werden.  
  
### Namespaces  
 Alle [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen müssen innerhalb eines Namespace deklariert werden. Die Windows\-API selbst ist nach Namespaces organisiert. Eine WinMD\-Datei muss denselben Namen wie der Stammnamespace haben. Zum Beispiel kann eine Klasse namens A.B.C.MyClass nur instanziiert werden, wenn sie in einer Metadatendatei definiert ist, die A.winmd oder A.B.winmd oder A.B.C.winmd heißt. Der Name der DLL muss nicht mit dem Namen der WINMD\-Datei übereinstimmen.  
  
 Die Windows\-API selbst wurde überarbeitet und präsentiert sich nun als gut gestaltete Klassenbibliothek, die nach Namespaces organisiert ist.  Alle [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten werden in den Namespaces Windows.\* deklariert.  
  
 Weitere Informationen finden Sie unter [Namespaces und Typsichtbarkeit](../cppcx/namespaces-and-type-visibility-c-cx.md).  
  
### Grundlegende Typen  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] definiert die folgenden grundlegenden Typen: UInt8, Int16, UInt16, Int32, UInt32, Int64, Uint64, Single, Double, Char16, Boolean und String.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] unterstützt die grundlegenden numerischen Typen im Standardnamespace als uint16, uint32, uint64, int16, int32, int64, float32, float64 und char16. Boolean und String werden auch im Plattformnamespace definiert.  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] definiert auch uint8, der dem Typ `unsigned char` entspricht, welcher nicht in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] unterstützt wird und in öffentlichen APIs nicht verwendet werden kann.  
  
 Ein elementarer Typ kann auf NULL festlegbar gemacht werden, indem er in einer[Platform::IBox Interface](../cppcx/platform-ibox-interface.md)\-Schnittstelle umgebrochen wird. Weitere Informationen finden Sie unter [Wertklassen und Strukturen](../cppcx/value-classes-and-structs-c-cx.md).  
  
 Weitere Informationen über grundlegende Typen finden Sie unter [Grundlegende Typen](../cppcx/fundamental-types-c-cx.md).  
  
### Zeichenfolgen  
 Eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Zeichenfolge ist eine unveränderliche Sequenz von 16\-Bit\-UNICODE\-Zeichen. Eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Zeichenfolge wird als `Platform::String^` projiziert. Diese Klasse stellt Methoden zum Erstellen und Bearbeiten von Zeichenfolgen zur Verfügung und ermöglicht, Zeichenfolgen in und aus `wchar_t` zu konvertieren.  
  
 Weitere Informationen finden Sie unter [Zeichenfolgen](../cppcx/strings-c-cx.md).  
  
### Arrays  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] unterstützt eindimensionale Arrays beliebigen Typs. Arrays von Arrays werden nicht unterstützt.  In [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] werden [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Arrays als [Platform::Array\-Klasse](../cppcx/platform-array-class.md) projiziert.  
  
 Weitere Informationen finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
### Referenzklassen und Strukturen  
 Eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Klasse wird in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] als Verweisklasse oder Referenzstruktur projiziert, da diese nach Verweis kopiert werden. Die Speicherverwaltung für Verweisklassen und Referenzstrukturen erfolgt mittels der Verweiszählung transparent. Wenn der letzte Verweis auf ein Objekt außerhalb des gültigen Bereichs ist, wird das Objekt vernichtet. Eine Verweisklasse oder Referenzstruktur  
  
-   kann als Member Konstruktoren, Methoden, Eigenschaften und Ereignisse enthalten. Diese Member können einen öffentlichen, privaten, geschützten oder internen Zugriff aufweisen.  
  
-   kann private geschachtelte Enumerations\-, Struktur\- oder Klassendefinitionen enthalten.  
  
-   kann direkt von einer Basisklasse erben und eine beliebige Anzahl von Schnittstellen implementieren. Alle Verweisklassen sind implizit konvertierbar in die [Platform::Object\-Klasse](../cppcx/platform-object-class.md) und können ihre virtuellen Methoden wie [Object::ToString](../cppcx/object-tostring-method-c-cx.md) überschreiben.  
  
 Eine Verweisklasse, die über einen öffentlichen Konstruktor verfügt, muss als versiegelt deklariert werden, um eine weitere Ableitung zu verhindern.  
  
 Weitere Informationen finden Sie unter [Referenzklassen und Strukturen](../cppcx/ref-classes-and-structs-c-cx.md).  
  
### Wertklassen und Strukturen  
 Eine Wertklasse oder Wertstruktur stellt eine grundlegende Datenstruktur dar und enthält nur Felder, die Wertklassen, Wertstrukturen oder vom Typ `Platform::String^` sein können.  Wertstrukturen und Wertklassen werden nach Wert kopiert.  
  
 Eine Wertstruktur kann auf NULL festlegbar gemacht werden, indem sie in einer IBox\-Schnittstelle umgebrochen wird.  
  
 Weitere Informationen finden Sie unter [Wertklassen und Strukturen](../cppcx/value-classes-and-structs-c-cx.md).  
  
### Teilklassen  
 Mit der Funktion der Teilklassen kann eine Klasse für mehrere Dateien definiert werden. Sie wird hauptsächlich dazu verwendet, um es Codegenerierungstools wie dem XAML\-Editor ermöglichen, eine Datei zu ändern, ohne dass die Datei, die Sie bearbeiten, angefasst werden muss.  
  
 Weitere Informationen finden Sie unter [Partielle Klassen](../cppcx/partial-classes-c-cx.md).  
  
### Eigenschaften  
 Eine Eigenschaft ist ein öffentlicher Datenmember eines beliebigen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typs und wird als GET\/SET\-Methodenpaar implementiert. Clientcode interpretiert eine Eigenschaft beim Zugriff als öffentliches Feld. Eine Eigenschaft, die keinen benutzerdefinierten GET\- oder SET\-Code erfordert, wird als *trivial\-Eigenschaft* bezeichnet und kann ohne explizite GET\- oder SET\-Methoden deklariert werden.  
  
 Weitere Informationen finden Sie unter [Eigenschaften](../cppcx/properties-c-cx.md).  
  
### [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Auflistungen in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] definiert einen Satz von Schnittstellen für Auflistungstypen, der von den verschiedenen Sprachen auf unterschiedliche Weise implementiert wird.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] bietet Implementierungen in [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md), [Platform::Collections::Map\-Klasse](../cppcx/platform-collections-map-class.md) und anderen ähnlichen konkreten Auflistungstypen, die mit den jeweiligen Entsprechungen der Standardvorlagenbibliothek \(STL\) kompatibel sind.  
  
 Weitere Informationen finden Sie unter [Auflistungen](../cppcx/collections-c-cx.md).  
  
### Vorlagenverweisklassen  
 Private und interne Verweisklassen können vorlagenbasiert und spezialisiert sein.  
  
 Weitere Informationen finden Sie unter [Vorlagenverweisklassen](../cppcx/template-ref-classes-c-cx.md).  
  
### Schnittstellen  
 Eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Schnittstelle definiert einen Satz von öffentlichen Eigenschaften, Methoden und Ereignissen, den eine Verweisklasse oder Referenzstruktur implementieren muss, wenn sie von der Schnittstelle erbt.  
  
 Weitere Informationen finden Sie unter [Schnittstellen](../cppcx/interfaces-c-cx.md).  
  
### Enumerationen  
 Eine Enumerationsklasse in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ähnelt einer Enumeration mit Bereichseinschränkung in C\+\+. Der zugrunde liegende Typ ist int32, es sei denn, das Attribut \[Flags\] kommt zur Anwendung. Dann ist der zugrunde liegende Typ uint32.  
  
 Weitere Informationen finden Sie unter [Enumerationen](../cppcx/enums-c-cx.md).  
  
### Delegaten  
 Ein Delegat in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ist analog zu einem std::function\-Objekt in C\+\+. Es ist eine spezielle Verweisklasse, mit deren Hilfe vom Client bereitgestellte Funktionen aufgerufen werden, die kompatible Signaturen enthalten.  Delegaten werden in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] am häufigsten als Typ eines Ereignisses verwendet.  
  
 Weitere Informationen finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md).  
  
### Ausnahmen  
 In C\+\+\/CX können Sie benutzerdefinierte Ausnahmetypen, [std::exception](~/standard-library/exception-class.md)\-Typen und [Platform::Exception](../cppcx/platform-exception-class.md)\-Typen abfangen.  
  
 Weitere Informationen finden Sie unter [Ausnahmen](../cppcx/exceptions-c-cx.md).  
  
### Ereignisse  
 Ein Ereignis ist ein öffentlicher Member in einer Verweisklasse oder einer Referenzstruktur mit einem Delegattyp als Typ. Ein Ereignis kann nur durch die besitzende Klasse aufgerufen, d. h. ausgelöst werden. Clientcode kann jedoch eigene Funktionen bereitstellen, die als Ereignishandler bezeichnet werden. Diese Ereignishandler werden aufgerufen, wenn die besitzende Klasse das Ereignis auslöst.  
  
 Weitere Informationen finden Sie unter [Ereignisse](../cppcx/events-c-cx.md).  
  
### Umwandlung  
 C\+\+\/CX unterstützt die Standard\-C\+\+\-Umwandlungsoperatoren [static\_cast](../cpp/static-cast-operator.md), [dynamic\_cast](../cpp/dynamic-cast-operator.md) und [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) sowie den Operator [safe\_cast](~/windows/safe-cast-cpp-component-extensions.md), der C\+\+\/CX\-spezifisch ist.  
  
 Weitere Informationen finden Sie unter [Umwandlung von Typen](../cppcx/casting-c-cx.md).  
  
### Boxing  
 Eine geschachtelte Variable ist ein Werttyp, der in einem Referenztyp in Situationen umschlossen wird, in denen eine Verweissemantik erforderlich ist.  
  
 Weitere Informationen finden Sie unter [Boxing](../cppcx/boxing-c-cx.md).  
  
### Attribute  
 Ein Attribut ist ein Metadatenwert, der auf jeden beliebigen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typ oder \-Typmember angewendet und zur Laufzeit überprüft werden kann.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] definiert einen Satz allgemeiner Attribute im `Windows::Foundation::Metadata`\-Namespace. Benutzerdefinierte Attribute in öffentlichen Schnittstellen werden in dieser Version nicht von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] unterstützt.  
  
## API\-Veraltung  
 Beschreibt, wie öffentliche API als veraltet markiert werden, indem das gleiche Attribute wie bei den [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Systemtypen verwendet wird.  
  
 Weitere Informationen finden Sie unter [Einstufen von Typen und Membern als veraltet](../cppcx/deprecating-types-and-members-c-cx.md).  
  
## Siehe auch  
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)