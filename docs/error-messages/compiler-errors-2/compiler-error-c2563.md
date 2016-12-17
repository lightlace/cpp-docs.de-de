---
title: "Compilerfehler C2563"
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
  - "C2563"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2563"
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2563
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Listen der formalen Parameter stimmen nicht überein  
  
 Die Liste der formalen Parameter einer Funktion \(oder eines Funktionszeigers\) stimmt nicht mit der einer anderen Funktion \(bzw. eines Zeigers auf eine Memberfunktion\) überein.  Folglich kann keine Zuweisung von Funktionen oder Zeigern stattfinden.  
  
 Im folgenden Beispiel wird C2563 generiert:  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```