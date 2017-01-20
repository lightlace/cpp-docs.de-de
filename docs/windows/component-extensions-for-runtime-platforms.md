---
title: "Component Extensions for Runtime Platforms"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "what's new [C++], keywords"
  - "what's new [C++], language features"
  - "Visual C++, keywords"
  - "keywords [C++]"
  - "Managed Extensions for C++, replacement syntax"
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
caps.latest.revision: 77
caps.handback.revision: "77"
ms.author: "mblome"
manager: "ghogen"
---
# Component Extensions for Runtime Platforms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ bietet Spracherweiterungen zur Unterstützung der Programmierung mit Laufzeitplattformen.  Mit [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]\) können Sie [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps und \-Komponenten programmieren, die in systemeigenen Code kompilieren.  Obwohl Sie [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps erstellen können, indem Sie direkt für die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-COM\-Schnittstellen programmieren, können Sie mithilfe von [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] mit Konstruktoren, Ausnahmen und anderen Techniken moderner C\+\+\-Programmierung arbeiten.  Um C\+\+\-Programmierung in einer verwalteten Ausführungsumgebung auf der .NET\-Plattform zu aktivieren, können Sie [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] verwenden.  
  
 **Zwei Laufzeiten, ein Satz von Erweiterungen**  
  
 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] ist eine Teilmenge von [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  Für Erweiterungen, die von [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] und von [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] unterstützt werden, hängt die Semantik davon ab, ob Sie die Common Language Runtime \(CLR\) oder die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] als Ziel verwenden.  Um die App für die Ausführung auf der [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] zu kompilieren, geben Sie die **\/ZW**\-Compileroption an.  Um sie für die Ausführung auf der CLR zu kompilieren, geben Sie die **\/clr**\-Compileroption an.  Diese Schalter werden automatisch festgelegt, wenn Sie Visual Studio zur Erstellung eines Projekt verwenden.  
  
 Weitere Informationen über das Erstellen von [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Anwendungen in C\+\+ finden Sie unter [Roadmap für Windows\-Runtime\-Apps mit C\+\+](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx).  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] erweitert den C\+\+\-ISO\/ANSI\-Standard und wird unter dem [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]\-ECMA\-Standard definiert.  Weitere Informationen finden Sie unter [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
## Datentyp\-Schlüsselworte  
 Die Spracherweiterungen schließen *Aggregatschlüsselwörter* ein, bei denen es sich um Schlüsselwörter handelt, die aus zwei durch Leerraum getrennte Token bestehen.  Die Token haben möglicherweise eine bestimmte Bedeutung, wenn sie einzeln verwendet werden, und eine andere Bedeutung, wenn sie zusammen verwendet werden.  Beispielsweise ist das Wort "ref" ein normaler Bezeichner und das Wort "class" ein Schlüsselwort, das eine systemeigene Klasse deklariert.  Wenn diese Wörter jedoch zu `ref class` kombiniert werden, deklariert das resultierende Aggregatschlüsselwort eine Entität, die als eine *Laufzeitklasse* bezeichnet wird.  
  
 Die Erweiterungen enthalten auch *kontextbezogene* Schlüsselwörter.  Ein Schlüsselwort wird abhängig von der Art der Anweisung, in der es enthalten ist, und seiner Platzierung in dieser Anweisung als kontextbezogen behandelt.  Beispielsweise kann das Token "property" ein Bezeichner sein oder es kann eine spezielle Art eines öffentlichen Klassenmembers deklarieren.  
  
 In der folgenden Tabelle sind Schlüsselwörter in der C\+\+\-Spracherweiterung aufgeführt.  
  
|Stichwort|Kontextbezogen|Zweck|Verweis|  
|---------------|--------------------|-----------|-------------|  
|`ref class`<br /><br /> `ref struct`|Nein|Deklariert eine Klasse.|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|Nein|Deklariert eine Wertklasse.|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|Nein|Deklariert eine Schnittstelle.|[interface class](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|Nein|Deklariert eine Enumeration.|[enum class](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|Ja|Deklariert eine Eigenschaft.|[property](../windows/property-cpp-component-extensions.md)|  
|`delegate`|Ja|Deklariert einen Delegaten.|[delegate](../windows/delegate-cpp-component-extensions.md)|  
|`event`|Ja|Deklariert ein Ereignis.|[event](../windows/event-cpp-component-extensions.md)|  
  
## Überschreibungsspezifizierer  
 Sie können die folgenden Schlüsselwörter verwenden, um das Überschreibungsverhalten für Ableitung zu qualifizieren.  Obwohl das `new`\-Schlüsselwort keine Erweiterung von C\+\+ ist, wird es hier aufgeführt, da es in einem zusätzlichen Kontext verwendet werden kann.  Einige Bezeichner sind auch für die systemeigene Programmierung gültig.  Weitere Informationen finden Sie unter [Gewusst wie: Deklarieren von Überschreibungsbezeichnern in nativen Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
|Schlüsselwort|Kontextbezogen|Zweck|Verweis|  
|-------------------|--------------------|-----------|-------------|  
|`abstract`|Ja|Gibt an, dass Funktionen oder Klassen abstrakt sind.|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|Nein|Gibt an, dass eine Funktion keine Überschreibung einer Basisklassenversion ist.|[new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|Ja|Gibt an, dass eine Methode eine Überschreibung einer Basisklassenversion sein muss.|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|Ja|Verhindert, dass Klassen als Basisklassen verwendet werden.|[sealed](../windows/sealed-cpp-component-extensions.md)|  
  
## Schlüsselwörter für Generika  
 Die folgenden Schlüsselwörter wurden hinzugefügt, um generische Typen zu unterstützen.  Weitere Informationen finden Sie unter [Generics](../windows/generics-cpp-component-extensions.md).  
  
|Schlüsselwort|Kontextbezogen|Zweck|  
|-------------------|--------------------|-----------|  
|`generic`|Nein|Definiert einen generischen Typ.|  
|`where`|Ja|Gibt die Einschränkungen an, die für einen generischen Typparameter angewendet werden.|  
  
## Sonstige Schlüsselwörter  
 Die folgenden Schlüsselwörter wurden den C\+\+\-Erweiterungen hinzugefügt.  
  
|Stichwort|Kontextbezogen|Zweck|Verweis|  
|---------------|--------------------|-----------|-------------|  
|`finally`|Ja|Gibt das Standardausnahmebehandlungsverhalten an.|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|Nein|Listet die Elemente einer Auflistung auf.|[for each, in](../dotnet/for-each-in.md)|  
|`gcnew`|Nein|Ordnet Typen auf dem Heap der Garbage Collection zu.  Wird anstelle von `new` und `delete` verwendet.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|Ja|Ordnet einen [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Typ zu.  Wird anstelle von `new` und `delete` verwendet.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|Ja|Gibt an, dass ein Member nur in der Deklaration oder in einem statischen Konstruktor initialisiert werden kann.|[initonly](../dotnet/initonly-cpp-cli.md)|  
|`literal`|Ja|Erstellt eine literale Variable.|[literal](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|Nein|Gibt an, dass ein Handle oder ein Zeiger nicht auf ein Objekt zeigt.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## Vorlagenkonstrukte  
 Die folgenden Sprachkonstrukte werden nicht als Schlüsselwörter, sondern als Vorlagen implementiert.  Wenn Sie die **\/ZW**\-Compileroption angeben, werden sie im `lang`\-Namespace definiert.  Wenn Sie die **\/clr**\-Compileroption angeben, werden sie im `cli`\-Namespace definiert.  
  
|Schlüsselwort|Zweck|Verweis|  
|-------------------|-----------|-------------|  
|`array`|Deklariert einen Array.|[Arrays](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|\(Nur CLR:\) Zeigt auf Daten in einem Referenztyp.|[interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|\(Nur CLR:\) Zeigt auf CLR\-Referenztypen, um das Garbage Collection\-System vorübergehend zu unterdrücken.|[pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)|  
|`safe_cast`|Bestimmt die optimale Umwandlungsmethode für einen Laufzeittyp und führt diese aus.|[safe\_cast](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|\(Nur CLR:\) Ruft ein <xref:System.Type?displayProperty=fullName>\-Objekt ab, das den angegebenen Typ oder das angegebene Objekt beschreibt.|[typeid](../windows/typeid-cpp-component-extensions.md)|  
  
## Deklaratoren  
 Die folgenden Typdeklaratoren weisen die Laufzeit an, die Lebensdauer und das Löschen von zugeordneten Objekten automatisch zu verwalten.  
  
|Operator|Zweck|Verweis|  
|--------------|-----------|-------------|  
|`^`|Deklariert ein Handle zu einem Objekt, d. h. einen Zeiger auf ein [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\- oder CLR\-Objekt, der automatisch gelöscht wird, wenn er nicht mehr verwendet werden kann.|[Handle für Objekt \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|Deklariert einen Nachverfolgungsverweis, d. h., einen Verweis auf ein [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\- oder CLR\-Objekt, der automatisch gelöscht wird, wenn er nicht mehr verwendet werden kann.|[Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## Zusätzliche Konstrukte und verwandte Themen  
 In diesem Abschnitt werden weitere Programmierungskonstrukte sowie Themen aufgeführt, die die CLR betreffen.  
  
|Thema|Beschreibung|  
|-----------|------------------|  
|[\_\_identifier \(C\+\+\/CLI\)](../windows/identifier-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] und CLR:\) Ermöglicht die Verwendung von Schlüsselwörtern als Bezeichner.|  
|[Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] und CLR:\) Ermöglicht es einer Funktion, eine variable Anzahl von Argumenten zu akzeptieren.|  
|[.NET Framework\-Entsprechungen der systemeigenen Typen in C\+\+](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|Listet die CLR\-Typen auf, die anstelle von ganzzahligen C\+\+\-Typen verwendet werden.|  
|[appdomain](../cpp/appdomain.md) `__declspec`\-Modifizierer|`__declspec`\-Modifizierer, für den es erforderlich ist, dass anwendungsdomänenspezifische statische und globale Variablen vorhanden sind.|  
|[C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)|Beschreibt, wie Umwandlungen im C\-Stil interpretiert werden.|  
|[\_\_clrcall](../cpp/clrcall.md)\-Aufrufkonvention|Gibt die CLR\-kompatible Aufrufkonvention an.|  
|`__cplusplus_cli`|[Vordefinierte Makros](../preprocessor/predefined-macros.md)|  
|[Custom Attributes](../windows/custom-attributes-cpp.md)|Beschreibt, wie eigene CLR\-Attribute definiert werden.|  
|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|Stellt eine Übersicht über die Ausnahmebehandlung bereit.|  
|[Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)|Zeigt, wie Memberfunktionen beliebige Member überschreiben können.|  
|[Friend\-Assemblys \(C\+\+\)](../dotnet/friend-assemblies-cpp.md)|Erläutert, wie eine Clientassembly auf alle Typen in einer Assemblykomponente zugreifen kann.|  
|[Boxing](../windows/boxing-cpp-component-extensions.md)|Veranschaulicht die Bedingungen, unter denen Werttypen geschachtelt werden.|  
|[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Erläutert, wie Eigenschaften von Typen zur Kompilierzeit erkannt werden.|  
|[managed, unmanaged](../preprocessor/managed-unmanaged.md) Pragmata|Veranschaulicht, wie verwaltete und nicht verwaltete Funktionen in demselben Modul zusammen verwendet werden können.|  
|[Prozess](../cpp/process.md) `__declspec`\-Modifizierer|`__declspec`\-Modifizierer, für den es erforderlich ist, dass prozessspezifische statische und globale Variablen vorhanden sind.|  
|[Reflektion](../dotnet/reflection-cpp-cli.md)|Zeigt die CLR\-Version von Informationen zum Laufzeittyp.|  
|[String](../windows/string-cpp-component-extensions.md)|Erläutert die Compilerkonvertierung von Zeichenfolgenliteralen zu <xref:System.String>.|  
|[Type Forwarding \(C\+\+\/CLI\)](../windows/type-forwarding-cpp-cli.md)|Ermöglicht das Verschieben eines Typs aus einer bereits bereitgestellten Assembly in eine andere Assembly, sodass Clientcode nicht neu kompiliert werden muss.|  
|[User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md)|Veranschaulicht benutzerdefinierte Attribute.|  
|[\#using\-Direktive](../preprocessor/hash-using-directive-cpp.md)|Importiert externe Assemblys.|  
|[XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)|Erläutert die XML\-basierte Codedokumentation mit [\/doc \(Verarbeiten von Dokumentationskommentaren\)](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)