---
title: "Compilerfehler C2835"
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
  - "C2835"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2835"
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2835
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Benutzerdefinierte Konvertierung 'Typ' unterstützt keine formalen Parameter  
  
 Benutzerdefinierte Typumwandlungen können keine formalen Parameter übernehmen.  
  
 Im folgenden Beispiel wird C2835 generiert:  
  
```  
// C2835.cpp  
class A {  
public:  
   char v_char;  
  
   A() {   
      v_char = 'A';   
   };  
   operator char(char a) {   // C2835  
   // try the following line instead  
   // operator char() {     
      return v_char + 1;   
   };  
};  
  
int main() {  
   A a;  
}  
```