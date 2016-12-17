---
title: "Compilerfehler C3116"
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
  - "C3116"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3116"
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
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