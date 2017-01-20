---
title: "Explicit Overrides  (C++ Component Extensions)"
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
  - "overriding, override [C++]"
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# Explicit Overrides  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie explizit einen Member einer Basisklasse oder Schnittstelle überschreibt.  Eine benannte \(explizite Überschreibung\) sollte nur verwendet werden, um eine Methode mit einer abgeleiteten Methode zu überschreiben, die einen anderen Namen verfügt.  
  
## Alle Laufzeiten  
 **Syntax**  
  
```  
  
        overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Parameter**  
  
 *overriding\-function\-declarator*  
 Der Rückgabetyp, der Name und die Argumentliste der überschreibenden Funktion.  Beachten Sie, dass die überschreibende Funktion nicht den gleichen Namen wie die Funktion haben muss, die überschrieben wird.  
  
 *type*  
 Der Basistyp, der eine Funktion enthält, um zu überschreiben.  
  
 *function*  
 Eine durch Trennzeichen getrennte Liste mehrere Funktionsnamen zu überschreiben.  
  
 *overriding\-function\-definition*  
 Die Funktionsrumpfanweisungen, die die überschreibende Funktion definieren.  
  
 **Hinweise**  
  
 Explizite Überschreibungen der Verwendung, um einen Alias für eine Methodensignatur zu erstellen, oder von verschiedenen Implementierungen für Methoden mit der gleichen Signatur zuordnen.  
  
 Informationen zum Ändern des Verhaltens der geerbten Typen und der geerbten Typmember, finden Sie unter [Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 Informationen über explizite Überschreibungen systemeigenen Code oder Code, die mit **\/clr:oldSyntax** kompiliert werden, finden Sie unter [Explizite Überschreibungen](../cpp/explicit-overrides-cpp.md).  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird eine einfache, implizite Überschreibung und eine Implementierung eines Members in eine Basisschnittstelle, nicht mit expliziten Überschreibungen an.  
  
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
  
  **X::f override of I1::f** **Beispiel**  
  
 Im folgenden Codebeispiel wird gezeigt, wie alle Schnittstellenmember mit einer allgemeinen Signatur, mithilfe der expliziten Überschreibungssyntax implementiert.  
  
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
  
  **X::f\-Überschreibung von I1::f und von I2::f**  
 **X::f\-Überschreibung von I1::f und von I2::f** **Beispiel**  
  
 Das folgende Codebeispiel zeigt, wie eine Funktionsüberschreibung einen anderen Namen der Funktion verfügen kann, die sie implementiert.  
  
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
  
  **X::g** **Beispiel**  
  
 Im folgenden Codebeispiel wird eine explizite Schnittstellenimplementierung an, die eine typsichere Auflistung implementiert.  
  
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
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)