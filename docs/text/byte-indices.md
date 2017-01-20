---
title: "Byte-Indizes"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Byteindizes [C++]"
  - "MBCS [C++], Byteindizes"
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "ghogen"
manager: "ghogen"
---
# Byte-Indizes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beachten Sie folgende Tipps:  
  
-   Bei der Verwendung eines byteweisen Index in einer Zeichenfolge treten ähnliche Probleme wie bei der Bearbeitung von Zeigern auf.  Das folgende Beispiel, in dem eine Zeichenfolge nach einem umgekehrten Schrägstrich durchsucht wird, verdeutlicht das Problem:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Dadurch wird unter Umständen ein nachfolgendes und kein führendes Byte indiziert und folglich auf kein `character` verwiesen.  
  
-   Verwenden Sie die Funktion [\_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md), um das obige Problem zu lösen:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Hiermit wird vorschriftsmäßig auf ein führendes Byte, also auf ein `character` verwiesen.  Mit der `_mbclen`\-Funktion wird die Größe des Zeichens ermittelt \(1 Byte oder 2 Bytes\).  
  
## Siehe auch  
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)   
 [Letztes Zeichen einer Zeichenfolge](../text/last-character-in-a-string.md)