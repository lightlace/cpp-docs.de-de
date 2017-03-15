---
title: "C-Laufzeitfehler R6028 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6028"
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# C-Laufzeitfehler R6028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Heap kann nicht initialisiert werden.  
  
 Dieser Fehler tritt auf, wenn das Betriebssystem den Speicherpool für die Anwendung nicht erstellen konnte.  Das heißt, CRT \(C Runtime\) hat die Win32\-Funktion `HeapCreate` aufgerufen, die NULL zurückgibt und auf einen Fehler hinweist.  
  
 Wenn dieser Fehler während des Starts der App auftritt, kann das System die Heapanforderungen möglicherweise nicht erfüllen, da fehlerhafte Treiber geladen werden.  Aktualisierte Treiber finden Sie unter Windows Update oder auf der Website des Hardwareherstellers.