---
title: "Funktionen ohne Prototyp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Funktionen ohne Prototyp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für nicht vollständige Funktionen mit Prototyp werden von der aufrufenden Funktion Ganzzahlwerte als Ganzzahlwerte und Gleitkommawerte als Gleitkommawerte mit doppelter Genauigkeit übergeben.  Nur Gleitkommawerte sind sowohl im Ganzzahl\- als auch im Gleitkommaregister enthalten, wenn von der aufgerufenen Funktion der Wert in den Ganzzahlregistern erwartet wird.  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)