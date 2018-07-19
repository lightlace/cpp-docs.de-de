---
title: Komponentenerweiterungen für Laufzeitplattformen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- Visual C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e60a1285f54de6b1cbfe311d4d9cbbc547785176
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862639"
---
# <a name="component-extensions-for-runtime-platforms"></a>Komponentenerweiterungen für Laufzeitplattformen
Visual C++ bietet Spracherweiterungen zur Unterstützung der Programmierung mit Laufzeitplattformen. Mithilfe von C + c++ / CX, können Sie programmieren, universelle Windows-Plattform-apps und Komponenten, die in systemeigenen Code kompiliert. Obwohl Uwp-apps durch direkten Programmierens mit der Windows-Runtime-COM-Schnittstellen erstellt werden können, mithilfe von C + c++ / CX, Sie können mit Konstruktoren, Ausnahmen und anderen moderner C++-Idiome-Programmierung arbeiten. Um C++-Programmierung in einer verwalteten ausführungsumgebung auf der .NET-Plattform zu aktivieren, können Sie C + c++ / CLI.  
  
 **Zwei Laufzeiten, ein Satz von Erweiterungen**  
  
 C + c++ / CX ist eine Teilmenge von C + c++ / CLI. Für Erweiterungen, die in C + c++ / CX und c++ / CLI und die Semantik davon, ob Sie die common Language Runtime (CLR) oder Windows-Runtime abzielen. Geben Sie zum Kompilieren der app auf Windows-Runtime ausgeführt, die **/Zw** -Compileroption. Geben Sie in der CLR ausgeführt um kompilieren, der **"/ CLR"** -Compileroption. Diese Schalter werden automatisch festgelegt, wenn Sie Visual Studio zur Erstellung eines Projekt verwenden.  
  
 Weitere Informationen zum Erstellen von universellen Windows-Plattform-apps in C++ finden Sie unter [Roadmap für Windows-Runtime-apps mit C++](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx).  
  
 C + c++ / CLI erweitert ISO/ANSI C++-Standard und ist definiert in der Ecma C# + c++ / CLI-Standard. Weitere Informationen finden Sie unter [.NET Framework-Programmierung mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
## <a name="data-type-keywords"></a>Datentyp-Schlüsselworte  
 Die spracherweiterungen schließen *aggregieren Schlüsselwörter*, dem werden Schlüsselwörter, die aus zwei durch Leerraum getrennte Token bestehen. Die Token haben möglicherweise eine bestimmte Bedeutung, wenn sie einzeln verwendet werden, und eine andere Bedeutung, wenn sie zusammen verwendet werden. Beispielsweise ist das Wort "ref" ein normaler Bezeichner und das Wort "class" ein Schlüsselwort, das eine systemeigene Klasse deklariert. Wenn diese Wörter Formular kombiniert werden, aber `ref class`, das resultierende aggregatschlüsselwort einer Entität, die als bekannt ist ein *Laufzeitklasse*.  
  
 Die Erweiterungen enthalten auch *kontextbezogene* Schlüsselwörter. Ein Schlüsselwort wird abhängig von der Art der Anweisung, in der es enthalten ist, und seiner Platzierung in dieser Anweisung als kontextbezogen behandelt. Beispielsweise kann das Token "property" ein Bezeichner sein oder es kann eine spezielle Art eines öffentlichen Klassenmembers deklarieren.  
  
 In der folgenden Tabelle sind Schlüsselwörter in der C++-Spracherweiterung aufgeführt.  
  
|Stichwort|Kontextbezogen|Zweck|Referenz|  
|-------------|-----------------------|-------------|---------------|  
|`ref class`<br /><br /> `ref struct`|Nein|Deklariert eine Klasse.|[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|Nein|Deklariert eine Wertklasse.|[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|Nein|Deklariert eine Schnittstelle.|[Schnittstellenklasse](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|Nein|Deklariert eine Enumeration.|[Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|Ja|Deklariert eine Eigenschaft.|[Eigenschaft](../windows/property-cpp-component-extensions.md)|  
|`delegate`|Ja|Deklariert einen Delegaten.|[delegate (Komponentenerweiterungen für C++)](../windows/delegate-cpp-component-extensions.md)|  
|`event`|Ja|Deklariert ein Ereignis.|[event](../windows/event-cpp-component-extensions.md)|  
  
## <a name="override-specifiers"></a>Überschreibungsspezifizierer  
 Sie können die folgenden Schlüsselwörter verwenden, um das Überschreibungsverhalten für Ableitung zu qualifizieren. Obwohl das `new`-Schlüsselwort keine Erweiterung von C++ ist, wird es hier aufgeführt, da es in einem zusätzlichen Kontext verwendet werden kann. Einige Bezeichner sind auch für die systemeigene Programmierung gültig. Weitere Informationen finden Sie unter [wie: Deklarieren Sie Überschreibungsspezifizierer in nativen Kompilierungen (C + c++ / CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
|Stichwort|Kontextbezogen|Zweck|Referenz|  
|-------------|-----------------------|-------------|---------------|  
|`abstract`|Ja|Gibt an, dass Funktionen oder Klassen abstrakt sind.|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|Nein|Gibt an, dass eine Funktion keine Überschreibung einer Basisklassenversion ist.|[New (neuer Slot in Vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|Ja|Gibt an, dass eine Methode eine Überschreibung einer Basisklassenversion sein muss.|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|Ja|Verhindert, dass Klassen als Basisklassen verwendet werden.|[sealed](../windows/sealed-cpp-component-extensions.md)|  
  
## <a name="keywords-for-generics"></a>Schlüsselwörter für Generika  
 Die folgenden Schlüsselwörter wurden hinzugefügt, um generische Typen zu unterstützen. Weitere Informationen finden Sie unter [Generika](../windows/generics-cpp-component-extensions.md).  
  
|Stichwort|Kontextbezogen|Zweck|  
|-------------|-----------------------|-------------|  
|`generic`|Nein|Definiert einen generischen Typ.|  
|`where`|Ja|Gibt die Einschränkungen an, die für einen generischen Typparameter angewendet werden.|  
  
## <a name="miscellaneous-keywords"></a>Sonstige Schlüsselwörter  
 Die folgenden Schlüsselwörter wurden den C++-Erweiterungen hinzugefügt.  
  
|Stichwort|Kontextbezogen|Zweck|Referenz|  
|-------------|-----------------------|-------------|---------------|  
|`finally`|Ja|Gibt das Standardausnahmebehandlungsverhalten an.|[Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|Nein|Listet die Elemente einer Auflistung auf.|[for each in](../dotnet/for-each-in.md)|  
|`gcnew`|Nein|Ordnet Typen auf dem Heap der Garbage Collection zu. Wird anstelle von `new` und `delete` verwendet.|[neue Gcnew ref](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|Ja|Ordnet einen Windows-Runtime-Typ. Wird anstelle von `new` und `delete` verwendet.|[neue Gcnew ref](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|Ja|Gibt an, dass ein Member nur in der Deklaration oder in einem statischen Konstruktor initialisiert werden kann.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|  
|`literal`|Ja|Erstellt eine literale Variable.|[Zeichenfolgenliterale](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|Nein|Gibt an, dass ein Handle oder ein Zeiger nicht auf ein Objekt zeigt.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## <a name="template-constructs"></a>Vorlagenkonstrukte  
 Die folgenden Sprachkonstrukte werden nicht als Schlüsselwörter, sondern als Vorlagen implementiert. Bei Angabe der **/Zw** -Compileroption, die sie definiert sind, der `lang` Namespace. Bei Angabe der **"/ CLR"** -Compileroption, die sie definiert sind, der `cli` Namespace.  
  
|Stichwort|Zweck|Referenz|  
|-------------|-------------|---------------|  
|`array`|Deklariert einen Array.|[Arrays](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|(Nur CLR:) Zeigt auf Daten in einem Referenztyp.|[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|(Nur CLR:) Zeigt auf CLR-Referenztypen, um das Garbage Collection-System vorübergehend zu unterdrücken.|[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)|  
|`safe_cast`|Bestimmt die optimale Umwandlungsmethode für einen Laufzeittyp und führt diese aus.|["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|(Nur CLR:) Ruft ein <xref:System.Type?displayProperty=fullName>-Objekt ab, das den angegebenen Typ oder das angegebene Objekt beschreibt.|[typeid](../windows/typeid-cpp-component-extensions.md)|  
  
## <a name="declarators"></a>Deklaratoren  
 Die folgenden Typdeklaratoren weisen die Laufzeit an, die Lebensdauer und das Löschen von zugeordneten Objekten automatisch zu verwalten.  
  
|Operator|Zweck|Referenz|  
|--------------|-------------|---------------|  
|`^`|Deklariert ein Handle für ein Objekt an. d. h. ein Zeiger auf ein Windows-Runtime oder CLR-Objekt, das automatisch gelöscht wird, wenn er nicht mehr verwendet werden.|[Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|Deklariert ein Nachverfolgungsverweis; d. h. einen Verweis auf ein Windows-Runtime oder CLR-Objekt, das automatisch gelöscht wird, wenn er nicht mehr verwendet werden.|[Nachverfolgungsverweisoperator](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## <a name="additional-constructs-and-related-topics"></a>Zusätzliche Konstrukte und verwandte Themen  
 In diesem Abschnitt werden weitere Programmierungskonstrukte sowie Themen aufgeführt, die die CLR betreffen.  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[__identifier (C++/CLI)](../windows/identifier-cpp-cli.md)|(Windows-Runtime und CLR) Ermöglicht die Verwendung von Schlüsselwörtern als Bezeichner an.|  
|[Variable Argumentlisten (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows-Runtime und CLR) Ermöglicht es einer Funktion, eine Variable Anzahl von Argumenten akzeptieren.|  
|[.NET Framework-Entsprechungen der nativen Typen in C++ (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|Listet die CLR-Typen auf, die anstelle von ganzzahligen C++-Typen verwendet werden.|  
|[AppDomain](../cpp/appdomain.md) `__declspec` Modifizierer|`__declspec`-Modifizierer, für den es erforderlich ist, dass anwendungsdomänenspezifische statische und globale Variablen vorhanden sind.|  
|[C-stilartige Umwandlungen mit/CLR (C + c++ / CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)|Beschreibt, wie Umwandlungen im C-Stil interpretiert werden.|  
|[__clrcall](../cpp/clrcall.md) Aufrufkonvention|Gibt die CLR-kompatible Aufrufkonvention an.|  
|`__cplusplus_cli`|[Vordefinierte Makros](../preprocessor/predefined-macros.md)|  
|[Benutzerdefinierte Attribute](../windows/custom-attributes-cpp.md)|Beschreibt, wie eigene CLR-Attribute definiert werden.|  
|[Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)|Stellt eine Übersicht über die Ausnahmebehandlung bereit.|  
|[Explizite Überschreibungen](../windows/explicit-overrides-cpp-component-extensions.md)|Zeigt, wie Memberfunktionen beliebige Member überschreiben können.|  
|[Friend-Assemblys (C++)](../dotnet/friend-assemblies-cpp.md)|Erläutert, wie eine Clientassembly auf alle Typen in einer Assemblykomponente zugreifen kann.|  
|[Boxing](../windows/boxing-cpp-component-extensions.md)|Veranschaulicht die Bedingungen, unter denen Werttypen geschachtelt werden.|  
|[Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Erläutert, wie Eigenschaften von Typen zur Kompilierzeit erkannt werden.|  
|[verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) Pragmas|Veranschaulicht, wie verwaltete und nicht verwaltete Funktionen in demselben Modul zusammen verwendet werden können.|  
|[Prozess](../cpp/process.md) `__declspec` Modifizierer|`__declspec`-Modifizierer, für den es erforderlich ist, dass prozessspezifische statische und globale Variablen vorhanden sind.|  
|[Reflexion (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Zeigt die CLR-Version von Informationen zum Laufzeittyp.|  
|[String](../windows/string-cpp-component-extensions.md)|Erläutert die Compilerkonvertierung von Zeichenfolgenliteralen zu <xref:System.String>.|  
|[Typweiterleitung (C++/CLI)](../windows/type-forwarding-cpp-cli.md)|Ermöglicht das Verschieben eines Typs aus einer bereits bereitgestellten Assembly in eine andere Assembly, sodass Clientcode nicht neu kompiliert werden muss.|  
|[Benutzerdefinierte Attribute](../windows/user-defined-attributes-cpp-component-extensions.md)|Veranschaulicht benutzerdefinierte Attribute.|  
|[#using-Direktive](../preprocessor/hash-using-directive-cpp.md)|Importiert externe Assemblys.|  
|[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)|Erläutert, XML-basierte Codedokumentation mit  [ /doc (Verarbeiten von Dokumentationskommentaren) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [.NET Programmieren mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)