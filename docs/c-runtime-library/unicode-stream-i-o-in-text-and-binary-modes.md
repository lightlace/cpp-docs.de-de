---
title: "Unicodestream-E/A im Text- und Binärmodus | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.io
dev_langs: C++
helpviewer_keywords:
- stream I/O routines
- I/O [CRT], unicode stream
- Unicode, stream I/O routines
- Unicode stream I/O
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df81013b497c0be939ceb3afd44d8a3e9e28ce18
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-stream-io-in-text-and-binary-modes"></a>Unicodestream-E/A im Text- und Binärmodus
Wenn eine Unicodestream-E/A-Routine (z.B. `fwprintf`, `fwscanf`, `fgetwc`, `fputwc`, `fgetws` oder `fputws`) mit einer im Textmodus (Standard) geöffneten Datei arbeitet, finden zwei Arten von Zeichenkonvertierungen statt:  
  
-   Konvertierung von Unicode zu MBCS oder von MBCS zu Unicode. Wenn eine Unicodestream-E/A-Funktion im Textmodus arbeitet, wird angenommen, dass es sich bei Quell- oder Zielstream um eine Sequenz von Multibytezeichen handelt. Daher konvertieren die Unicode Streameingabefunktionen Multibytezeichen in Breitzeichen (wie bei einem Aufruf der `mbtowc`-Funktion). Aus demselben Grund konvertieren die Unicode-Streamausgabefunktionen Breitzeichen in Multibytezeichen (wie bei einem Aufruf der `wctomb`-Funktion).  
  
-   Übersetzung von Wagenrücklauf-Zeilenvorschub (CR-LF). Diese Übersetzung findet vor der MBCS-Unicode-Konvertierung (für Unicode-Streameingabefunktionen) und nach der Unicode-MBCS-Konvertierung (für Unicode-Streamausgabefunktionen) statt. Bei der Eingabe wird jede Wagenrücklauf-Zeilenvorschub-Kombination in ein einzelnes Zeilenvorschubzeichen übersetzt. Bei der Ausgabe wird jedes Zeilenvorschubzeichen in eine Wagenrücklauf-Zeilenvorschub-Kombination übersetzt.  
  
 Wenn jedoch eine Unicodestream-E/A-Funktion im binären Modus arbeitet, wir von einer Unicode-Datei ausgegangen und es erfolgt keine CR-LF-Übersetzung oder Zeichenkonvertierung während der Ein- und Ausgabe. Verwenden Sie die Anweisung _setmode( _fileno( stdin ), _O_BINARY );, um wcin ordnungsgemäß auf einer UNICODE-Textdatei zu verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)