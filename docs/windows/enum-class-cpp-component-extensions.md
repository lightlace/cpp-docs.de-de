---
title: "enum class (Komponentenerweiterungen f&#252;r C++)"
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
ms.assetid: 8010fa8c-bad6-45b4-8214-b4db64d7ffe1
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# enum class (Komponentenerweiterungen f&#252;r C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert eine Enumeration im Namespacebereich, die ein benutzerdefinierter Typ ist, der aus einem Satz von benannten Konstanten besteht, die als Enumeratoren bezeichnet werden.  
  
## Alle Laufzeiten  
 **Hinweise**  
  
 C\+\+\/CX und C\+\+\/CLI unterstützen `public enum class` und `private enum class`, die der standardmäßigen C\+\+\-`enum class` ähneln, jedoch einen Zugriffsspezifizierer haben. Unter **\/clr** ist der C\+\+11\-`enum class`\-Typ zulässig, jedoch wird die Warnung C4472 generiert, die sicherstellen soll, dass Sie tatsächlich den ISO\-Enumerationstyp und nicht den C\+\+\/CX\- und C\+\+\/CLI\-Typ verwenden möchten. Weitere Informationen zum C\+\+\-Schlüsselwort nach ISO\-Standard \(`enum`\) finden Sie unter [Enumerationen](../cpp/enumerations-cpp.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Syntax**  
  
```  
  
access  
enum class  
enumeration-identifier  
[:underlying-type] { enumerator-list } [var]; accessenum structenumeration-identifier[:underlying-type] { enumerator-list } [var];  
```  
  
 **Parameter**  
  
 *Zugriff*  
 Der Zugriff auf die Enumeration, die `public` oder `private` sein kann.  
  
 *enumeration\-identifier*  
 Der Name der Enumeration.  
  
 *underlying\-type*  
 \(Optional\) Der zugrunde liegende Typ der Enumeration.  
  
 \(Optional. Nur [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\) Der zugrunde liegende Enumerationstyp, der `bool`, `char`, `char16`, `int16`, `uint16`, `int`, `uint32`, `int64` oder `uint64` sein kann.  
  
 *enumerator\-list*  
 Eine durch Komma getrennte Liste mit Enumeratornamen.  
  
 Der Wert jedes Enumerators ist ein konstanter Ausdruck, der entweder implizit vom Compiler oder explizit durch die Notation *enumerator* `=` *constant\-expression* definiert wird. Standardmäßig ist der Wert des ersten Enumerators Null, wenn er implizit definiert ist. Der Wert jedes folgenden implizit definierten Enumerators ist der Wert des vorherigen Enumerators \+ 1.  
  
 *var*  
 \(Optional\) Der Name einer Variablen des Enumerationstyps.  
  
 **Hinweise**  
  
 Weitere Informationen und Beispiele finden Sie unter [Enums](http://msdn.microsoft.com/%20library/windows/apps/hh755820.aspx).  
  
 Beachten Sie, dass der Compiler Fehlermeldungen ausgibt, wenn der konstante Ausdruck, der den Wert eines Enumerators definiert, nicht durch den *underlying\-type* dargestellt werden kann.  Der Compiler meldet jedoch keinen Fehler für einen Wert, der für den zugrunde liegenden Typ ungeeignet ist. Zum Beispiel:  
  
-   Wenn der *underlying\-type* numerisch ist und ein Enumerator den maximalen Wert für diesen Typ angibt, kann der Wert der folgenden implizit definierten Enumeration nicht dargestellt werden.  
  
-   Wenn der *underlying\-type*`bool` ist und mehr als zwei Enumeratoren implizit definiert werden, können die Enumeratoren, die auf die ersten beiden folgen, nicht dargestellt werden.  
  
-   Wenn der *underlying\-type*`char16` ist und der Enumerationswert von 0xD800 bis 0xDFFF reicht, kann der Wert dargestellt werden. Der Wert ist jedoch logisch falsch, da er die Hälfte ein Unicode\-Ersatzzeichenpaars darstellt und nicht isoliert angezeigt werden soll.  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntax**  
  
```  
  
access  
enum class  
name [:type] { enumerator-list } var; accessenum structname [:type] { enumerator-list } var;  
```  
  
 **Parameter**  
  
 `access`  
 Die Zugriff der Enumeration.  Er kann entweder **öffentlich** oder `private` sein.  
  
 `enumerator-list`  
 Eine durch Komma getrennte Liste der Bezeichner \(Enumeratoren\) in der Enumeration.  
  
 `name`  
 Der Name der Enumeration.  Anonyme verwaltete Enumerationen sind nicht zulässig.  
  
 `type` \(optional\)  
 Der zugrunde liegende Typ der *Bezeichner*.  Dabei kann es sich um einen beliebigen skalaren Typ handeln, wie Versionen von „int“, „short“ oder „long“ mit oder ohne Vorzeichen.`bool` oder `char` ist ebenfalls zulässig.  
  
 `var` \(optional\)  
 Der Name einer Variablen des Enumerationstyps.  
  
 **Hinweise**  
  
 **enum class** und **enum struct** sind entsprechende Deklarationen.  
  
 Es gibt zwei Typen von Enumerationen: C\+\+\/CX und Standard.  
  
 Eine verwaltete oder C\+\+\/CX\-Enumeration kann wie folgt definiert sein:  
  
```cpp  
public enum class day {sun, mon };  
```  
  
 und ist semantisch äquivalent zu:  
  
```cpp  
ref class day { public: static const int sun = 0; static const int mon = 1; };  
```  
  
 Eine Standard\-Enumeration kann wie folgt definiert sein:  
  
```cpp  
enum day2 { sun, mon };  
```  
  
 und ist semantisch äquivalent zu:  
  
```cpp  
static const int sun = 0; static const int mon = 1;  
```  
  
 Verwaltete Enumeratornamen \(*Bezeichner*\) werden nicht in den Bereich injiziert, in dem die Enumeration definiert ist. Alle Verweise auf Enumeratoren müssen vollständig qualifiziert sein \(*Name*`::`*Bezeichner*\).  Aus diesem Grund können Sie keine anonyme verwaltete Enumeration definieren.  
  
 Die Enumeratoren einer Standardenumeration werden stark in den einschließenden Bereich eingefügt.  Das heißt, wenn es ein anderes Symbol mit dem gleichen Namen wie ein Enumerator im einschließenden Bereich gibt, generiert der Compiler einen Fehler.  
  
 In Visual C\+\+ 2002 und Visual C\+\+ 2003 wurden Enumeratoren schwach eingefügt \(sichtbar im einschließenden Bereich, es sei denn, es gibt einen anderen Bezeichner mit demselben Namen\).  
  
 Wenn eine standardmäßige C\+\+\-Enumeration \(ohne **class** oder `struct`\) definiert ist, wird die Enumeration beim Kompilieren mit **\/clr** als verwaltete Enumeration kompiliert.  Die Enumeration hat weiterhin die Semantik einer nicht verwalteten Enumeration.  Hinweis: Der Compiler fügt ein Attribut \([Microsoft::VisualC::NativeEnumAttribute](assetId:///Microsoft::VisualC::NativeEnumAttribute?qualifyHint=False&autoUpgrade=True)\) ein, das der Visual C\+\+\-Compiler erkennt. So wird gekennzeichnet, dass der Programmierer möchte, dass die Enumeration eine systemeigene Enumeration ist.  Andere Compiler erkennen einfach die Standardenumeration als verwaltete Enumeration.  
  
 Eine benannte, Standardenumeration, die mit \/clr kompiliert wurde, ist in der Assembly als verwaltete Enumeration sichtbar und kann von einem anderen verwalteten Compiler genutzt werden.   Eine unbenannte Standardenumeration ist jedoch nicht öffentlich aus der Assembly sichtbar.  
  
 In Visual C\+\+ 2002 und Visual C\+\+ 2003 würde eine Standardenumeration, die als Typ in einem Funktionsparameter verwendet wird, wie folgt aussehen:  
  
```cpp  
// mcppv2_enum.cpp // compile with: /clr enum E { a, b }; void f(E) {System::Console::WriteLine("hi");} int main() { E myi = b; f(myi); }  
```  
  
 die folgende in MSIL für die Funktionssignatur ausgeben:  
  
```  
void f(int32);  
```  
  
 In den aktuellen Versionen des Compilers, wird die Standardenumeration als verwaltete Enumeration mit einem \[NativeEnumAttribute\] und dem folgenden in MSIL für die Funktionssignatur ausgegeben:  
  
```  
void f(E)  
```  
  
 Weitere Informationen zu systemeigenen Enumerationen finden Sie unter [Deklarationen von C\+\+\-Enumerationen](../cpp/enumerations-cpp.md).  
  
 Weitere Informationen zu CLR\-Enumerationen finden Sie unter:  
  
-   [Zugrunde liegender Typ eines Enumerators](../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)  
  
-   [Verwaltete und Standardenumerationen](../misc/how-to-convert-between-managed-and-standard-enumerations.md)  
  
-   [Operatoren und Enumerationen](../misc/operators-and-enumerations.md)  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 desc  
  
```cpp  
// mcppv2_enum_2.cpp // compile with: /clr // managed enum public enum class m { a, b }; // standard enum public enum n { c, d }; // unnamed, standard enum public enum { e, f } o; int main() { // consume managed enum m mym = m::b; System::Console::WriteLine("no automatic conversion to int: {0}", mym); System::Console::WriteLine("convert to int: {0}", (int)mym); // consume standard enum n myn = d; System::Console::WriteLine(myn); // consume standard, unnamed enum o = f; System::Console::WriteLine(o); }   
```  
  
 **Ausgabe**  
  
```Output  
Keine automatische Konvertierung zu int: b  
 Konvertierung zu: 1  
 1  
 1  
  
```  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)