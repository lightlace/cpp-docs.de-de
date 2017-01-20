---
title: "Compilerfehler C2061"
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
  - "C2061"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2061"
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2061
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: Bezeichner 'Bezeichner'  
  
 Der Compiler hat an einer unerwarteten Stelle einen Bezeichner gefunden.  Stellen Sie sicher, dass der `identifier` vor der Verwendung deklariert wurde.  
  
 Unter Umständen ist ein Initialisierer in runde Klammern eingeschlossen.  Um dieses Problem zu vermeiden, schließen Sie den Deklarator in runde Klammern ein oder versehen ihn mit dem Typ `typedef`.  
  
 Dieser Fehler kann auch ausgelöst werden, wenn der Compiler einen Ausdruck als Klassenvorlagenargument entdeckt; verwenden Sie [typename](../../cpp/typename.md), um dem Compiler mitzuteilen, dass es sich um einen Typ handelt.  
  
 Im folgenden Beispiel wird C2061 generiert:  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 kann auftreten, wenn Sie einen Instanznamen an [typeid](../../windows/typeid-cpp-component-extensions.md) übergeben:  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```