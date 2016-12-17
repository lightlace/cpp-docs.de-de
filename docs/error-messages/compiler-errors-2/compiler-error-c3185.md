---
title: "Compilerfehler C3185"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3185"
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"TypeId" verwendet für verwalteten oder WinRT\-Typ "Typ"; verwenden Sie stattdessen "Operator".  
  
 [TypeId](../../cpp/typeid-operator.md) Operator kann nicht bei einem verwalteten oder WinRT\-Typ angewendet werden; verwenden Sie stattdessen [typeid](../../windows/typeid-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3185 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3185a.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
  
int main() {  
   Derived ^ pd = gcnew Derived;  
   Base ^pb = pd;  
   const type_info & t1 = typeid(pb);   // C3185  
   System::Type ^ MyType = Base::typeid;   // OK  
};  
```  
  
 **Verwaltete Erweiterungen für C\+\+**  
  
 [TypIid](../../cpp/typeid-operator.md) kann nicht bei einem verwalteten Typ angewendet werden; verwenden Sie stattdessen [\_\_typeof](../../misc/typeof.md).  
  
 Im folgenden Beispiel wird C3185 generiert:  
  
```  
// C3185b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class Base {};  
__gc class Derived : public Base {};  
  
int main() {  
   Derived *pd = new Derived;  
   Base *pb = pd;  
   const type_info & t1 = typeid(*pb);   // C3185  
  
   // OK  
   Type * t = __typeof(Base);  
   Type * t1 = __typeof(Derived);  
};  
```