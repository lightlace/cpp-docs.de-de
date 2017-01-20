---
title: "Compilerfehler C2092"
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
  - "C2092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2092"
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Arrayname' Arrayelementtyp kann keine Funktion sein  
  
 Funktionsarrays sind nicht zulässig.  Stattdessen sollte ein Array von Funktionszeigern verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2092 generiert:  
  
```  
// C2092.cpp  
typedef void (F) ();  
typedef F AT[10];   // C2092  
```  
  
## Beispiel  
 Mögliche Lösung:  
  
```  
// C2092b.cpp  
// compile with: /c  
typedef void (F) ();  
typedef F * AT[10];  
```