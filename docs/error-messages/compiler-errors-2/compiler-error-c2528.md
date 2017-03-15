---
title: "Compilerfehler C2528 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2528"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2528"
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2528
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name': Zeiger auf Verweis ungültig  
  
 Sie können keinen Zeiger auf einen Verweis deklarieren.  Dereferenzieren Sie die Variable, bevor Sie einen Zeiger darauf deklarieren.  
  
 Im folgenden Beispiel wird C2528 generiert:  
  
```  
// C2528.cpp  
int i;  
int &ir = i;  
int & (*irptr) = ir;    // C2528  
```