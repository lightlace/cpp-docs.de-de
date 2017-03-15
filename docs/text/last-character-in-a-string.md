---
title: "Letztes Zeichen einer Zeichenfolge | Microsoft Docs"
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
  - "Letztes Zeichen in der Zeichenfolge"
  - "MBCS [C++], Letztes Zeichen in der Zeichenfolge"
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Letztes Zeichen einer Zeichenfolge
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beachten Sie folgende Tipps:  
  
-   Für nachfolgende Bytes reservierte Bereiche überschneiden sich häufig mit dem ASCII\-Zeichensatz.  Für beliebige Steuerzeichen \(kleiner als 32\) können Sie problemlos byteweise Scanvorgänge verwenden.  
  
-   Sehen Sie sich die folgende Codezeile an, von der überprüft werden soll, ob es sich beim letzten Zeichen in einer Zeichenfolge um einen umgekehrten Schrägstrich handelt:  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     Da `strlen` nicht MBCS\-kompatibel ist, wird in einer Mehrbyte\-Zeichenfolge die Anzahl der Bytes, nicht die Anzahl der Zeichen zurückgegeben.  Beachten Sie auch, dass in bestimmten Codepages \(z. B. 932\) das Zeichen '\\' \(0x5c\) als gültiges nachfolgendes Byte definiert ist \(bei `sz` handelt es sich um eine C\-Zeichenfolge\).  
  
     Eine Lösung besteht darin, den Code wie folgt umzuschreiben:  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     Dieser Code verwendet die MBCS\-Funktionen `_mbsrchr` und `_mbsinc`.  Da diese Funktionen "MBCS\-kompatibel" sind, können Sie das Zeichen '\\' und das nachfolgende Byte '\\' voneinander unterscheiden.  Der obige Code führt bestimmte Aktionen durch, falls das letzte Zeichen der Zeichenfolge ein **NULL**\-Zeichen \('\\0'\) ist.  
  
## Siehe auch  
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)   
 [Zeichenzuweisungen](../text/character-assignment.md)