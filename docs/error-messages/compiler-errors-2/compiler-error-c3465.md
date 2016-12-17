---
title: "Compilerfehler C3465"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3465"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3465"
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3465
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um den Typ 'typ' zu verwenden, müssen Sie auf die Assembly 'assembly' verweisen.  
  
 Typweiterleitung funktioniert im Fall einer Clientanwendung bis zur erneuten Kompilierung des Clients. Bei der erneuten Kompilierung benötigen Sie einen Verweis auf jede Assembly, die die Definition eines in Ihrer Clientanwendung verwendeten Typs enthält.  
  
 Weitere Informationen finden Sie unter [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Beispiel  
 Das folgende Beispiel erstellt eine Assembly, die den neuen Speicherort eines Typs enthält.  
  
```  
// C3465.cpp // compile with: /clr /LD public ref class R { public: ref class N {}; };  
```  
  
## Beispiel  
 Im folgenden Beispiel wird eine Assembly erstellt, die ursprünglich die Definition des Typs enthielt, jetzt jedoch Weiterleitungssyntax für den Typ enthält.  
  
```  
// C3465_b.cpp // compile with: /clr /LD #using "C3465.dll" [ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3465 generiert:  
  
```  
// C3465_c.cpp // compile with: /clr // C3465 expected #using "C3465_b.dll" // Uncomment the following line to resolve. // #using "C3465.dll" int main() { R^ r = gcnew R(); }  
```