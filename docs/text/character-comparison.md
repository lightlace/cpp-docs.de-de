---
title: "Zeichenvergleich"
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
  - "Zeichen [C++], Vergleichen"
  - "Vergleichen von Zeichen"
  - "MBCS [C++], Zeichenvergleich"
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "ghogen"
manager: "ghogen"
---
# Zeichenvergleich
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beachten Sie folgende Tipps:  
  
-   Das Vergleichen eines bekannten führenden Bytes mit einem ASCII\-Zeichen funktioniert fehlerfrei:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   Um zwei unbekannte Zeichen miteinander zu vergleichen, ist ein in Mbstring.h definiertes Makro erforderlich:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     So wird sichergestellt, dass beide Bytes eines Doppelbytezeichens zur Ermittlung der Gleichheit miteinander verglichen werden.  
  
## Siehe auch  
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)   
 [Pufferüberlauf](../text/buffer-overflow.md)