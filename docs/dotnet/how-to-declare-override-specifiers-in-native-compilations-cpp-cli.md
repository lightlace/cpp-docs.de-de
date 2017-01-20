---
title: "Gewusst wie: Deklarieren von &#220;berschreibungsbezeichnern in nativen Kompilierungen (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Überschreibungsbezeichner in nativer Kompilierung, Überschreiben"
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Deklarieren von &#220;berschreibungsbezeichnern in nativen Kompilierungen (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[versiegelt](../windows/sealed-cpp-component-extensions.md), [Zusammenfassung](../windows/abstract-cpp-component-extensions.md) und [überschreiben](../windows/override-cpp-component-extensions.md) sind in den Kompilierungen verfügbar, der nicht **\/ZW** oder [\/clr](../build/reference/clr-common-language-runtime-compilation.md) verwenden.  
  
> [!NOTE]
>  Die Standardsprache ISO C\+\+11 hat den Bezeichner [überschreiben](../cpp/override-specifier.md) und den [Abschließen](../cpp/final-specifier.md) Bezeichner, und beide werden in Visual Studio für die Verwendung `final` anstelle von `sealed` im Code unterstützt, der verwendet wird, kompiliert werden, z systemeigen systemeigen.  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Beispiel zeigt, dass `sealed` in systemeigenen Kompilierungen gültig ist.  
  
### Code  
  
```  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Beispiel zeigt, dass `override` in systemeigenen Kompilierungen gültig ist.  
  
### Code  
  
```  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## Beispiel  
  
### **Beschreibung**  
 Dieses Beispiel zeigt, dass `abstract` in systemeigenen Kompilierungen gültig ist.  
  
### Code  
  
```  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## Siehe auch  
 [Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md)