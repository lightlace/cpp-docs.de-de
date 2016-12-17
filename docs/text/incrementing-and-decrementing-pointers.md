---
title: "Inkrementieren und Dekrementieren von Zeigern"
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
  - "Dekrementieren von Zeigern"
  - "Inkrementieren von Zeigern"
  - "MBCS [C++], Zeiger"
  - "Zeiger [C++], Mehrbytezeichen"
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "ghogen"
manager: "ghogen"
---
# Inkrementieren und Dekrementieren von Zeigern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beachten Sie folgende Tipps:  
  
-   Verweisen Sie auf führende Bytes, nicht auf nachfolgende Bytes.  Zeiger auf nachfolgende Bytes sind in der Regel unsicher.  Meist ist es sicherer, eine Zeichenfolge vorwärts und nicht rückwärts zu scannen.  
  
-   Es stehen Funktionen und Makros zum Inkrementieren und Dekrementieren von Zeigern zur Verfügung, die sich um ein ganzes Zeichen weiter bewegen:  
  
    ```  
    sz1++;  
    ```  
  
     wird zu:  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     Die `_mbsinc`\-Funktion und die `_mbsdec`\-Funktion inkrementieren und dekrementieren vorschriftsmäßig in `character`\-Einheiten, unabhängig von der Zeichengröße.  
  
-   Zum Dekrementieren benötigen Sie einen Zeiger, der auf den Anfang der Zeichenfolge verweist, wie im folgenden Beispiel:  
  
    ```  
    sz2--;  
    ```  
  
     wird zu:  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Wahlweise kann der Anfangszeiger auch auf ein gültiges Zeichen innerhalb der Zeichenfolge verweisen, z. B.  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Sie müssen über einen Zeiger verfügen, der auf ein bekanntes und gültiges führendes Byte verweist.  
  
-   Es empfiehlt sich, einen Zeiger auf das vorherige Zeichen zu verwalten, um `_mbsdec`\-Aufrufe zu beschleunigen.  
  
## Siehe auch  
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)   
 [Byte\-Indizes](../text/byte-indices.md)