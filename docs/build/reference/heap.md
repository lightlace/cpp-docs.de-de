---
title: "/HEAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Heapzuordnung, Festlegen der Heapgröße"
  - "HEAP-editbin-Option"
  - "-HEAP-editbin-Option"
  - "/HEAP-editbin-Option"
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /HEAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Größe des Heaps in Bytes fest.  Diese Option gilt nur für ausführbare Dateien auf.  
  
```  
  
/HEAP:  
reserve[,commit]  
  
```  
  
## Hinweise  
 Das Argument `reserve` gibt die gesamte ursprünglichen Heapreservierung im virtuellen Speicher an.  Standardmäßig ist die Heapgröße 1 MB.  [EDITBIN\-Referenz](../../build/reference/editbin-reference.md) rundet oben den angegebenen Wert zur nächsten Vielfachen von 4 Bytes.  
  
 Wie das optionale `commit`\-Argument interpretiert wird, hängt vom jeweiligen Betriebssystem ab.  Auf einem Windows\-Betriebssystem wird der ersten Menge an physischem Speicher an, zuzuordnenden und die wenig zusätzlichem Arbeitsspeicher, z zuzuordnen, wann der Heap erweitert werden muss.  Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei.  Ein höherer `commit`\-Wert erlaubt System, um weniger häufig Speicher reserviert, wenn die Anwendung mehr Heapspeicher jedoch \-zunahmen die Arbeitsspeicheranforderungen und möglicherweise die App\-Startdauer erfordert.  Der Wert `commit` muss kleiner oder gleich dem Wert `reserve` sein.  
  
 Geben Sie den `reserve` und `commit`\-Werte im Dezimal\- oder Sprache C oder hexadezimal oktale Darstellung an.  Beispielsweise kann ein Wert von 1 MB angegeben werden als 1048576 im Dezimal\- oder als 0x100000 im Hexadezimalformat oder als 04000000 in oktalem.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)