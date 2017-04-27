---
title: "Übersetzungsmoduskonstanten | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
dev_langs:
- C++
helpviewer_keywords:
- O_BINARY constant
- O_TEXT constant
- O_RAW constant
- _O_TEXT constant
- _O_RAW constant
- translation constants
- _O_BINARY constant
- translation, constants
- translation, modes
- translation modes (file I/O)
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 2522ccf3c35a52141d3164bd2a35535a4068893e
ms.lasthandoff: 04/01/2017

---
# <a name="translation-mode-constants"></a>Übersetzungsmoduskonstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Manifestkonstanten `_O_BINARY` und `_O_TEXT` geben den Übersetzungsmodus von Dateien (`_open` und `_sopen`) oder von Streams (`_setmode`) an.  
  
 Folgende Werte sind zulässig:  
  
 `_O_TEXT`  
 Öffnet eine Datei im Textmodus (übersetzt). Kombinationen aus Wagenrücklauf und Zeilenvorschub (CR-LF) werden bei der Eingabe in ein einzelnes Zeilenvorschubzeichen (LF) umgewandelt. Zeilenvorschubzeichen werden bei der Ausgabe in Kombinationen aus Wagenrücklauf und Zeilenvorschub (CR-LF) übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In den Dateien, die für das Lesen oder Lesen/Schreiben geöffnet sind, überprüft `fopen` die Datei auf STRG + Z am Dateiende, und entfernt sofern möglich die Markierung. Dies geschieht, da ein Verwenden der Funktionen `fseek` und `ftell` zum Navigieren innerhalb einer Datei, die mit STRG + Z endet, dazu führen kann, dass sich `fseek` in der Nähe des Dateiendes nicht ordnungsgemäß verhält.  
  
 `_O_BINARY`  
 Öffnet eine Datei im binären (unübersetzten) Modus. Die oben genannten Übersetzungen werden unterdrückt.  
  
 `_O_RAW`  
 Wie in `_O_BINARY`. Für Kompatibilität mit C 2.0 unterstützt.  
  
 Weitere Informationen finden Sie unter [Text- und Binärmodus-Datei-E-A](../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Dateiübersetzung](../c-runtime-library/file-translation-constants.md).  
  
## <a name="see-also"></a>Siehe auch  
 [_open, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_pipe](../c-runtime-library/reference/pipe.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_setmode](../c-runtime-library/reference/setmode.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)
