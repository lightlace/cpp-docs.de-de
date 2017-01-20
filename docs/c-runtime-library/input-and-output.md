---
title: "Eingabe und Ausgabe"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "E/A [CRT]"
  - "E/A [CRT], Routinen"
  - "E/A-Routinen"
  - "Eingaberoutine"
  - "Ausgaberoutine"
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Eingabe und Ausgabe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die E\/A funktioniert Lesen und Schreiben von Daten für Dateien und Geräten.  Datei\-E\/A\-Operationen finden im Textmodus oder im Binärdateimodus statt.  Die Microsoft\-Laufzeitbibliothek hat drei Typen E\/A\-Funktionen:  
  
-   [Stream\-E\/A](../c-runtime-library/stream-i-o.md)\-Funktionsfestlichkeitsdaten als Stream von einzelnen Zeichen.  
  
-   [E\/A auf niedriger Ebene](../c-runtime-library/low-level-i-o.md)\-Funktionen rufen das Betriebssystem direkt für Vorgang auf niedrigerer Ebene als das auf, das von Stream\-E\/A bereitgestellt wird.  
  
-   [Konsole und Port E\/A](../c-runtime-library/console-and-port-i-o.md) funktioniert Lesen oder schreibt direkt an eine Konsole \(Tastatur und Bildschirm\) oder einem E\/A\-Anschluss \(wie ein Druckeranschluss\).  
  
    > [!NOTE]
    >  Da Streamfunktionen gepuffert werden Funktionen und auf niedriger Ebene nicht sind, sind diese beiden Typen von Funktionen im Allgemeinen nicht kompatibel.  Für die Verarbeitung einer bestimmten Datei, verwenden Sie entweder Stream oder Funktionen auf niedriger Ebene ausschließlich.  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)