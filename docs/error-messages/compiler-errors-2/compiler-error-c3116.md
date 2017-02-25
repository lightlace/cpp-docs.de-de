---
title: "Compilerfehler C3116 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3116"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3116"
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3116
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Speicherspezifizierer': Ungültige Speicherklasse für Schnittstellenmethode  
  
 Sie haben `typedef`, `register` oder `static` als Speicherklasse für eine Schnittstellenmethode verwendet.  Diese Speicherklassen sind bei Schnittstellenmembern nicht zulässig.  
  
 Im folgenden Beispiel wird C3116 generiert:  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```