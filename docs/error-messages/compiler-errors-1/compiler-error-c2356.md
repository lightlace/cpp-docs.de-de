---
title: "Compilerfehler C2356"
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
  - "C2356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2356"
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialisierungssegment darf während der Übersetzungseinheit nicht geändert werden  
  
 Mögliche Ursachen:  
  
-   Vor `#pragma init_seg` seht Segmentinitialisierungscode  
  
-   `#pragma init_seg` steht hinter einem anderen `#pragma init_seg`  
  
 Verschieben Sie den Segmentinitialisierungscode an den Anfang des Moduls.  Wenn mehrere Bereiche initialisiert werden müssen, verschieben Sie sie in gesonderte Module.  
  
 Im folgenden Beispiel wird C2356 generiert:  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```