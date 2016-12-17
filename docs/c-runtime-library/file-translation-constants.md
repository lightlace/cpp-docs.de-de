---
title: "Datei&#252;bersetzungskonstanten"
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
  - "c.constants.file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Konstanten [C++], Dateiübersetzungsmodus"
  - "Dateiübersetzung [C++]"
  - "Dateiübersetzung [C++], Konstanten"
  - "Übersetzungskonstanten"
  - "Verschiebung, Konstanten"
  - "Verschiebung, Dateiübersetzungskonstanten"
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Datei&#252;bersetzungskonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <stdio.h>  
```  
  
## Hinweise  
 Diese Konstanten geben den Modus der Übersetzung an \(**"b"** oder **"t"**\).  Der Modus wird in der Zeichenfolge enthalten, die den erlaubten Zugriffstyp anzeigt \(**"r"**, **"w"**, **"a"**, **"r\+"**, **"w\+"**, **"a\+"**\).  
  
 Die Übersetzungsmodi sind, wie folgt:  
  
 **t**  
 Öffnet sich im Modus des Texts \(übersetzt\).  In diesem Modus werden Wagenrückkehr\-\/Zeilenvorschub\(CR\-LF\) in einzelne Kombinationen Zeilenvorschübe \(LF\) auf Eingaben übersetzt, und Zeilenvorschubzeichen werden in CR\-LF Kombinationen auf Ausgabe übersetzt.  Außerdem wird STRG\+Z bei der Eingabe als EOF\-Zeichen interpretiert.  In den Dateien, die zum Lesen oder das Lesen und Schreiben geöffnet sind, überprüft `fopen` für STRG\+Z am Ende der Datei und entfernt sie, sofern möglich.  Dies geschieht, da die Anwendung u der Funktionen `fseek` und `ftell`, die innerhalb eines Dateiendes mit STRG\+Z blättern `fseek` bewirkt, dass sie nahe dem Ende der Datei nicht ordnungsgemäß verhält.  
  
> [!NOTE]
>  Die **t** Option ist nicht Teil des ANSI\-Standards für `fopen` und `freopen`.  Es ist eine Microsoft\-Erweiterung und sollte nicht verwendet werden, wo ANSI\-Portabilität gewünscht wird.  
  
 **b**  
 Öffnet im binären \(unübersetzten Modus\).  Die oben erwähnten Übersetzungen unterdrückt werden.  
  
 Wenn **t** oder **b** nicht *im Modus* angegeben ist, wird der Übersetzungsmodus durch die StandardModusvariable [\_fmode](../c-runtime-library/fmode.md) definiert.  Weitere Informationen zur Verwendung von Text\- und Binärdateimodi, finden Sie unter [Text Binärdatei\-Modus\-Datei\-E\/A](../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## Siehe auch  
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)