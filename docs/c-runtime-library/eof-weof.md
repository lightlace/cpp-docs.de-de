---
title: "EOF, WEOF"
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
  - "EOF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "EOF-Funktion"
  - "WEOF-Funktion"
  - "Ende der Datei"
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# EOF, WEOF
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <stdio.h>  
```  
  
## Hinweise  
 EOF wird durch eine E\/A\-Routine zurückgegeben, wenn die Datei \(oder in einigen Fällen\), ein Fehler auftritt.  
  
 WEOF erzeugt den Rückgabewert, des Typs **wint\_t**, verwendet, um das Ende eines Streams breite zu signalisieren, oder einen Fehlerzustand zu melden.  
  
## Siehe auch  
 [putc, putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../c-runtime-library/reference/fflush.md)   
 [fclose, \_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [\_putch, \_putwch](../c-runtime-library/reference/putch-putwch.md)   
 [Isascii, \_\_isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)