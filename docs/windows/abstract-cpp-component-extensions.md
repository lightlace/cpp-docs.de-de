---
title: "abstrakt (Komponentenerweiterungen für C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- abstract
- abstract_cpp
dev_langs: C++
helpviewer_keywords: abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b935aabeb048d955941a41f6a50735897a53009
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="abstract--c-component-extensions"></a>abstract (Komponentenerweiterungen für C++)
Das `abstract`-Schlüsselwort nimmt eine der folgenden Deklarationen vor:  
  
-   Ein Typ kann als Basistyp verwendet werden, aber der Typ selbst kann nicht instanziiert werden.  
  
-   Eine Typmemberfunktion kann nur in einem abgeleiteten Typ definiert werden.  
  
## <a name="all-platforms"></a>Alle Plattformen  
 **Syntax**  
  
```  
  
      class-declaration  
      class-identifier  
      abstract {}  
virtualreturn-typemember-function-identifier() abstract ;  
  
```  
  
 **Hinweise**  
  
 Die erste Beispielsyntax deklariert eine Klasse als abstrakt. Die *Klassendeklaration* Komponente kann entweder eine systemeigene C++-Deklaration (`class` oder `struct`), oder eine C++-erweiterungsdeklaration (`ref class` oder `ref struct`) Wenn die **/Zw** oder **"/ CLR"** -Compileroption angegeben ist.  
  
 Die zweite Beispielsyntax deklariert eine virtuelle Memberfunktion als abstrakt. Das Deklarieren einer Funktion als abstrakt ist mit dem Deklarieren als rein virtuelle Funktion identisch. Das Deklarieren einer Memberfunktion als abstrakt bewirkt, dass auch die einschließende Klasse als abstrakt deklariert wird.  
  
 Die `abstract` Schlüsselwort wird im systemeigenen und plattformspezifischen Code unterstützt; d. h. kompiliert werden können, mit oder ohne die **/Zw** oder **"/ CLR"** -Compileroption.  
  
 Sie können zur Kompilierzeit erkennen, wenn ein Typ abstrakt mit ist der `__is_abstract(type)` Merkmal "Typ". Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Das `abstract`-Schlüsselwort ist ein kontextbezogener Überschreibungsspezifizierer. Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md). Weitere Informationen zu überschreibungsspezifizierern finden Sie unter [wie: Deklarieren Sie Überschreibungsspezifizierer in nativen Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Das folgende Codebeispiel generiert einen Fehler, da Klasse `X` als `abstract` gekennzeichnet ist.  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel generiert einen Fehler, da es eine systemeigene Klasse instanziiert, die als `abstract` gekennzeichnet ist. Dieser Fehler tritt auf, mit oder ohne die **"/ CLR"** -Compileroption.  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel generiert einen Fehler, da Funktion `f` eine Definition enthält, aber als `abstract` gekennzeichnet ist. Die letzte Anweisung im Beispiel zeigt, dass das Deklarieren einer abstrakten virtuellen Funktion dem Deklarieren einer rein virtuellen Funktion entspricht.  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)