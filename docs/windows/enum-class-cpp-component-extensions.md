---
title: Enumerationsklasse (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 8010fa8c-bad6-45b4-8214-b4db64d7ffe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 54c4e97458e1a7322d84e012ea5609d3e29bfb0a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647312"
---
# <a name="enum-class--c-component-extensions"></a>enum class (Komponentenerweiterungen für C++)
Deklariert eine Enumeration im Namespacebereich, die ein benutzerdefinierter Typ ist, der aus einem Satz von benannten Konstanten besteht, die als Enumeratoren bezeichnet werden.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
### <a name="remarks"></a>Hinweise
  
 C++ / CX und C++ / CLI-Unterstützung **öffentliche Enumerationsklasse** und **private Enumerationsklasse** ähneln sich der c++- **Enumerationsklasse** aber zusätzlich den Zugriff auf Spezifizierer. Unter **"/ CLR"**, C ++ 11 **Enumerationsklasse** -Typ zulässig, jedoch generiert die Warnung C4472, was beabsichtigt ist, um sicherzustellen, dass Sie tatsächlich den ISO-Enumerationstyp und nicht die C++ / CX und C++ / CLI-Typ. Weitere Informationen zu der ISO C++ **Enum** -Schlüsselwort, finden Sie unter [Enumerationen](../cpp/enumerations-cpp.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
### <a name="syntax"></a>Syntax  
  
```cpp  
      access  
      enum class  
      enumeration-identifier  
      [:underlying-type] { enumerator-list } [var];  
accessenum structenumeration-identifier[:underlying-type] { enumerator-list } [var];  
```  
  
### <a name="parameters"></a>Parameter  
 *Zugriff*  
 Der Zugriff der Enumeration, die möglicherweise **öffentliche** oder **private**.  
  
 *enumeration-identifier*  
 Der Name der Enumeration.  
  
 *underlying-type*  
 (Optional) Der zugrunde liegende Typ der Enumeration.  
  
 (Optional. Nur Windows-Runtime) der zugrunde liegende Typ der Enumeration, die möglicherweise **"bool"**, **Char**, `char16`, `int16`, `uint16`, **Int**, `uint32`, `int64`, oder `uint64`.  
  
 *enumerator-list*  
 Eine durch Komma getrennte Liste mit Enumeratornamen.  
  
 Der Wert jedes Enumerators ist ein konstanter Ausdruck, der entweder implizit vom Compiler oder explizit durch die Notation *enumerator*`=`*constant-expression*. Standardmäßig ist der Wert des ersten Enumerators Null, wenn er implizit definiert ist. Der Wert jedes folgenden implizit definierten Enumerators ist der Wert des vorherigen Enumerators + 1.  
  
 *var*  
 (Optional) Der Name einer Variablen des Enumerationstyps.  
  
### <a name="remarks"></a>Hinweise 
  
 Weitere Informationen und Beispiele finden Sie unter [Enums](http://msdn.microsoft.com/%20library/windows/apps/hh755820.aspx).  
  
 Beachten Sie, dass der Compiler Fehlermeldungen ausgibt, wenn der konstante Ausdruck, der den Wert eines Enumerators definiert, nicht durch den *underlying-type*dargestellt werden kann.  Der Compiler meldet jedoch keinen Fehler für einen Wert, der für den zugrunde liegenden Typ ungeeignet ist. Zum Beispiel:  
  
-   Wenn der *underlying-type* numerisch ist und ein Enumerator den maximalen Wert für diesen Typ angibt, kann der Wert der folgenden implizit definierten Enumeration nicht dargestellt werden.  
  
-   Wenn *vom zugrunde liegenden Typ* ist **"bool"**, und mehr als zwei Enumeratoren implizit definiert, die Enumeratoren, die ersten beiden nicht dargestellt werden können.  
  
-   Wenn der *underlying-type* `char16`ist und der Enumerationswert von 0xD800 bis 0xDFFF reicht, kann der Wert dargestellt werden. Der Wert ist jedoch logisch falsch, da er die Hälfte ein Unicode-Ersatzzeichenpaars darstellt und nicht isoliert angezeigt werden soll.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/ZW`  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
### <a name="syntax"></a>Syntax
  
```cpp  
      access  
      enum class  
      name [:type] { enumerator-list } var;  
accessenum structname [:type] { enumerator-list } var;  
```  
  
 ### <a name="parameters"></a>Parameter  
  
 *Zugriff*  
 Die Zugriff der Enumeration. Kann es sich um **öffentliche** oder **private**.  
  
 *enumerator-list*  
 Eine durch Komma getrennte Liste der Bezeichner (Enumeratoren) in der Enumeration.  
  
 *name*  
 Der Name der Enumeration. Anonyme verwaltete Enumerationen sind nicht zulässig.  
  
 *Typ* (optional)  
 Der zugrunde liegende Typ der *Bezeichner*. Dies kann einen beliebigen skalaren Typ, z. B. Versionen mit oder ohne Vorzeichen von sein **Int**, **kurze**, oder **lange**.  **"bool"** oder **Char** ist ebenfalls zulässig.  
  
 *Var* (optional)  
 Der Name einer Variablen des Enumerationstyps.  
  
### <a name="remarks"></a>Hinweise 
  
 **enum class** und **enum struct** sind entsprechende Deklarationen.  
  
 Es gibt zwei Typen von Enumerationen: C++/CX und Standard.  
  
 Eine verwaltete oder C++/CX-Enumeration kann wie folgt definiert sein:  
  
```cpp  
public enum class day {sun, mon };  
```  
  
 und ist semantisch äquivalent zu:  
  
```cpp  
ref class day {  
public:  
   static const int sun = 0;  
   static const int mon = 1;  
};  
```  
  
 Eine Standard-Enumeration kann wie folgt definiert sein:  
  
```cpp  
enum day2 { sun, mon };  
```  
  
 und ist semantisch äquivalent zu:  
  
```cpp  
static const int sun = 0;  
static const int mon = 1;  
```  
  
 Verwaltete Enumeratornamen (*Bezeichner*) werden nicht in den Bereich injiziert, in dem die Enumeration definiert ist. Alle Verweise auf Enumeratoren müssen vollständig qualifiziert sein (*Name*`::`*Bezeichner*).  Aus diesem Grund können Sie keine anonyme verwaltete Enumeration definieren.  
  
 Die Enumeratoren einer Standardenumeration werden stark in den einschließenden Bereich eingefügt.  Das heißt, wenn es ein anderes Symbol mit dem gleichen Namen wie ein Enumerator im einschließenden Bereich gibt, generiert der Compiler einen Fehler.  
  
 In Visual C++ 2002 und Visual C++ 2003 wurden Enumeratoren schwach eingefügt (sichtbar im einschließenden Bereich, es sei denn, es gibt einen anderen Bezeichner mit demselben Namen).  
  
 Wenn eine standardmäßige C++-Enumeration definiert ist (ohne **Klasse** oder **Struktur**) kompilieren mit `/clr` wird die Enumeration als verwaltete Enumeration kompiliert werden.  Die Enumeration hat weiterhin die Semantik einer nicht verwalteten Enumeration.  Hinweis: Der Compiler fügt ein Attribut ( `Microsoft::VisualC::NativeEnumAttribute`) ein, das der Visual C++-Compiler erkennt. So wird gekennzeichnet, dass der Programmierer möchte, dass die Enumeration eine systemeigene Enumeration ist.  Andere Compiler erkennen einfach die Standardenumeration als verwaltete Enumeration.  
  
 Eine benannte, standardenumeration kompiliert, mit `/clr` werden in der Assembly als verwaltete Enumeration sichtbar und können von einem anderen verwalteten Compiler genutzt werden.   Eine unbenannte Standardenumeration ist jedoch nicht öffentlich aus der Assembly sichtbar.  
  
 In Visual C++ 2002 und Visual C++ 2003 würde eine Standardenumeration, die als Typ in einem Funktionsparameter verwendet wird, wie folgt aussehen:  
  
```cpp  
// mcppv2_enum.cpp  
// compile with: /clr  
enum E { a, b };  
void f(E) {System::Console::WriteLine("hi");}  
  
int main() {  
   E myi = b;  
   f(myi);  
}  
```  
  
 die folgende in MSIL für die Funktionssignatur ausgeben:  
  
```cpp  
void f(int32);  
```  
  
 In den aktuellen Versionen des Compilers, wird die Standardenumeration als verwaltete Enumeration mit einem [NativeEnumAttribute] und dem folgenden in MSIL für die Funktionssignatur ausgegeben:  
  
```cpp  
void f(E)  
```  
  
 Weitere Informationen zu systemeigenen Enumerationen finden Sie unter [Deklarationen von C++-Enumerationen](../cpp/enumerations-cpp.md).  
  
 Weitere Informationen zu CLR-Enumerationen finden Sie unter:  
  
-   [Zugrunde liegender Typ eines Enumerators](../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/clr`  
  
### <a name="examples"></a>Beispiele  
  
```cpp  
// mcppv2_enum_2.cpp  
// compile with: /clr  
// managed enum  
public enum class m { a, b };  
  
// standard enum  
public enum n { c, d };  
  
// unnamed, standard enum  
public enum { e, f } o;  
  
int main()   
{  
   // consume managed enum  
   m mym = m::b;  
   System::Console::WriteLine("no automatic conversion to int: {0}", mym);  
   System::Console::WriteLine("convert to int: {0}", (int)mym);  
  
   // consume standard enum  
   n myn = d;  
   System::Console::WriteLine(myn);  
  
   // consume standard, unnamed enum  
   o = f;  
   System::Console::WriteLine(o);  
}   
```  
  
```Output  
no automatic conversion to int: b  
  
convert to int: 1  
  
1  
  
1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)