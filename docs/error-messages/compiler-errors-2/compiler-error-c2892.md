---
title: "Compilerfehler C2892"
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
  - "C2892"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2892"
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2892
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lokale Klasse darf keine Membervorlagen haben  
  
 Von Vorlagen gebildete Memberfunktionen sind in einer Klasse, die in einer Funktion definiert ist, nicht gültig.  
  
 Im folgenden Beispiel wird C2892 generiert:  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```