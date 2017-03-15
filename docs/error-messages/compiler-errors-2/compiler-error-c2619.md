---
title: "Compilerfehler C2619 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2619"
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„identifier“: Ein statisches Datenmember ist in einer anonymen Struktur oder Union nicht zulässig.  
  
 Ein Member einer anonymen Struktur oder Union ist als `static` deklariert.  
  
 Im folgenden Beispiel wird C2619 generiert und veranschaulicht, wie Sie diesen Fehler beheben, indem Sie das statische\-Schlüsselwort entfernen.  
  
```  
// C2619.cpp  
int main() {  
   union { static int j; };  // C2619  
   union { int j; };  // OK  
}  
```