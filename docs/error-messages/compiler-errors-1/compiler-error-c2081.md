---
title: "Compilerfehler C2081 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2081"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2081"
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2081
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Name in der formalen Parameterliste ist ungültig  
  
 Der Bezeichner hat einen Syntaxfehler verursacht.  
  
 Dieser Fehler kann bei Verwendung des alten Formats für die formale Parameterliste auftreten.  Sie müssen den Typ des formalen Parameters in der Liste der formalen Parameter angeben.  
  
 Im folgenden Beispiel wird C2081 generiert:  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 Mögliche Lösung:  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```