---
title: "&#220;bersetzungsmoduskonstanten"
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
  - "_O_BINARY"
  - "_O_TEXT"
  - "_O_RAW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_BINARY-Konstante"
  - "_O_RAW-Konstante"
  - "_O_TEXT-Konstante"
  - "O_BINARY-Konstante"
  - "O_RAW-Konstante"
  - "O_TEXT-Konstante"
  - "Übersetzungskonstanten"
  - "Übersetzungsmodi (Datei-E/A)"
  - "Verschiebung, Konstanten"
  - "Verschiebung, Modi"
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# &#220;bersetzungsmoduskonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <fcntl.h>  
  
```  
  
## Hinweise  
 `_O_BINARY` und `_O_TEXT` Manifestelementen Konstanten bestimmen den Übersetzungsmodus für Dateien \(`_open` und `_sopen`\) oder den Übersetzungsmodus für Streams \(`_setmode`\).  
  
 Folgende Werte sind zulässig:  
  
 `_O_TEXT`  
 Öffnet Datei im Modus des Texts \(übersetzt\).  Kombinationen von Wagenrücklauf\/Zeilenvorschubs \(CR\-LF\) werden in einem einzelnen Zeilenvorschub \(LF\) auf Eingaben übersetzt.  Zeilenvorschubzeichen werden in CR\-LF Kombinationen auf Ausgabe übersetzt.  Außerdem wird STRG\+Z bei der Eingabe als EOF\-Zeichen interpretiert.  In den Dateien, die für das Lesen und das Lesen und Schreiben geöffnet sind, überprüft `fopen` für STRG\+Z am Ende der Datei und entfernt sie, sofern möglich.  Dies geschieht, da die Anwendung u der Funktionen `fseek` und `ftell`, die innerhalb eines Dateiendes mit STRG\+Z blättern `fseek` bewirkt, dass sie nahe dem Ende der Datei nicht ordnungsgemäß verhält.  
  
 `_O_BINARY`  
 Öffnet Datei im binären \(unübersetzten Modus\).  Die oben erwähnten Übersetzungen unterdrückt werden.  
  
 `_O_RAW`  
 Dieselbe Bedeutung wie `_O_BINARY`.  Unterstützt für Kompatibilität Cs 2,0.  
  
 Weitere Informationen finden Sie unter [Text Binärdatei\-Modus\-Datei\-E\/A](../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Datei\-Übersetzung](../c-runtime-library/file-translation-constants.md).  
  
## Siehe auch  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_pipe](../c-runtime-library/reference/pipe.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_setmode](../c-runtime-library/reference/setmode.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)