---
title: "_nolock Functions | Microsoft Docs"
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
helpviewer_keywords: 
  - "_nolock-Funktionen"
  - "nolock-Funktionen"
ms.assetid: 7d651d87-38d2-4303-9897-fdb5f7a3e899
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _nolock Functions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dies sind Funktionen, die keine Sperre ausführen.  Sie werden für Benutzer bereitgestellt, die Höchstleistung benötigen.  Weitere Informationen finden Sie unter [Leistung von Multithreadbibliotheken](../c-runtime-library/multithreaded-libraries-performance.md).  
  
 Verwenden Sie \_nolock Funktionen nur, wenn das Programm tatsächlich singlethreaded ist, oder wenn es eine eigene Sperre erreichen.  
  
 [\_fclose\_nolock](../c-runtime-library/reference/fclose-nolock.md)  
  
 [\_fflush\_nolock](../c-runtime-library/reference/fflush-nolock.md)  
  
 [\_fgetc\_nolock, \_fgetwc\_nolock](../c-runtime-library/reference/fgetc-nolock-fgetwc-nolock.md)  
  
 [\_fread\_nolock](../c-runtime-library/reference/fread-nolock.md)  
  
 [\_fseek\_nolock, \_fseeki64\_nolock](../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)  
  
 [\_ftell\_nolock, \_ftelli64\_nolock](../c-runtime-library/reference/ftell-nolock-ftelli64-nolock.md)  
  
 [\_fwrite\_nolock](../c-runtime-library/reference/fwrite-nolock.md)  
  
 [\_getc\_nolock, \_getwc\_nolock](../c-runtime-library/reference/getc-nolock-getwc-nolock.md)  
  
 [\_getch\_nolock, \_getwch\_nolock](../c-runtime-library/reference/getch-nolock-getwch-nolock.md)  
  
 [\_getchar\_nolock, \_getwchar\_nolock](../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md)  
  
 [\_getche\_nolock, \_getwche\_nolock](../c-runtime-library/reference/getche-nolock-getwche-nolock.md)  
  
 [\_getdcwd\_nolock, \_wgetdcwd\_nolock](../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)  
  
 [\_putc\_nolock, \_putwc\_nolock](../c-runtime-library/reference/putc-nolock-putwc-nolock.md)  
  
 [\_putch\_nolock, \_putwch\_nolock](../c-runtime-library/reference/putch-nolock-putwch-nolock.md)  
  
 [\_putchar\_nolock, \_putwchar\_nolock](../c-runtime-library/reference/putchar-nolock-putwchar-nolock.md)  
  
 [\_ungetc\_nolock, \_ungetwc\_nolock](../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)  
  
 [\_ungetch\_nolock, \_ungetwch\_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)  
  
## Siehe auch  
 [Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)