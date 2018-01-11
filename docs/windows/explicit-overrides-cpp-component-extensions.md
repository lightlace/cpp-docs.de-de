---
title: "Explizite Überschreibungen (Komponentenerweiterungen für C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 346dd73952934d514b2741c41d5a27816b7152ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-overrides--c-component-extensions"></a>Explizite Überschreibungen (Komponentenerweiterungen für C++)
In diesem Thema erläutert, wie einen Member einer Basisklasse oder Schnittstelle explizit zu überschreiben. Eine benannte (explizite) überschreiben, sollte nur verwendet werden, um eine Methode mit einer abgeleiteten Methode überschreiben, die einen anderen Namen aufweist.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 **Syntax**  
  
```  
  
      overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Parameter**  
  
 *Überschreiben von funktionsdeklarator*  
 Der Typ, Namen und die Argumentliste Rückgabeliste der überschreibenden Funktion.  Beachten Sie, dass die überschreibende Funktion keinen haben den gleichen Namen wie die Funktion, die überschrieben wird.  
  
 *Typ*  
 Der Basistyp, die eine Funktion zum Außerkraftsetzen enthält.  
  
 *function*  
 Eine durch Trennzeichen getrennte Liste von mindestens einem Funktionsnamen überschreiben.  
  
 *Überschreiben von Funktionsdefinition*  
 Die Funktion Text-Anweisungen, die die überschreibende Funktion definieren.  
  
 **Hinweise**  
  
 Explizite verwenden Sie Außerkraftsetzungen, um einen Alias für die Signatur einer Methode zu erstellen, oder um unterschiedliche Implementierungen für Methoden Witht die gleiche Signatur bereitzustellen.  
  
 Informationen zum Ändern des Verhaltens von geerbten Typen geerbte Typ- und Typmemberdeklarationen finden Sie unter [Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Hinweise**  
  
 Für Informationen zu expliziten in systemeigenem Code überschreibt oder Code kompiliert mit **/CLR: oldSyntax**, finden Sie unter [explizite Überschreibungen](../cpp/explicit-overrides-cpp.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt einen einfachen, implizite "Override" und Implementierung eines Elements in eine Basisschnittstelle nicht über explizite überschreibungen.  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **Ausgabe**  
  
```Output  
X::f override of I1::f  
```  
  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie alle Schnittstellenmember mit einer allgemeinen Signatur, die mit expliziten Überschreibungssyntax zu implementieren.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **Ausgabe**  
  
```Output  
X::f override of I1::f and I2::f  
X::f override of I1::f and I2::f  
```  
  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Funktion zum Überschreiben von der Funktion einen anderen Namen verwenden kann, die implementiert wird.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **Ausgabe**  
  
```Output  
X::g  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt eine explizite schnittstellenimplementierung, die eine sichere typauflistung implementiert.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)