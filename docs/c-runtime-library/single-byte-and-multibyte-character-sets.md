---
title: "Einzelbyte- und Mehrbyte-Zeichens&#228;tze | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichensätze [C++], Mehrbyte"
  - "Zeichensätze [C++], Einzelbyte"
  - "MBCS [C++], Informationen über MBCS"
  - "SBCS (Einzelbyte-Zeichensatz)"
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Einzelbyte- und Mehrbyte-Zeichens&#228;tze
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der ASCII\-Zeichensatz werden Zeichen im Bereich 0x00 \- 0x7F.  Es gibt mehrere andere Zeichensätze, hauptsächlich europäisch, die die Zeichen im Bereich 0x00 \- 0x7F identisch dem ASCII\-Zeichensatz und definieren Sie auch ein erweiterter Zeichensatz von 0x80 \- 0xFF definieren.  Daher ist ein äußerst, Einzelbyte\-Zeichensatz \(`SBCS`\) aus, um den ASCII\-Zeichensatz sowie die Zeichensätze für viele europäischen Sprachen darzustellen.  Einige außereuropäische Zeichensätze, z das japanische Kanji, viel mehr Zeichen als in einem Einzelbytecodierungsschema dargestellt werden kann, und benötigen daher Codierung \(Mehrbyte\-Zeichensätze `MBCS`\).  
  
> [!NOTE]
>  Viele `SBCS` Routinen in der Microsoft\-Laufzeitbibliothek behandeln Mehrbyte\-Bytes, \- Zeichen und \- Zeichenfolgen je nach Bedarf.  Viele Mehrbyte\-Zeichensätze definieren den ASCII\-Zeichensatz als Teilmenge.  In vielen Mehrbyte\-Zeichensätzen sind die Zeichen im Bereich 0x00 – 0x7F mit den entsprechenden Zeichen des ASCII\-Zeichensatzes identisch.  In `ASCII` und `MBCS` Zeichenfolgen, hat das EinByte\- `NULL` Zeichen \("\\ 0 "\) den Wert 0x00 und NULL an.  
  
 Ein Mehrbyte\-Zeichensatz besteht möglicherweise aus EinByte\- und 2\-Byte\-Zeichen.  Daher enthält möglicherweise einer Mehrbyte\-Zeichenfolge eine Mischung von Einzelbyte\- und Doppelbytezeichen.  Ein zwei\-Bytemehrbytezeichen hat ein führendes Byte und ein nachfolgendes Byte.  In einem bestimmten Mehrbyte\-Zeichensatz liegen die führenden Bytes ebenso wie die nachfolgenden Bytes innerhalb eines bestimmten Bereichs.  Wenn diese Bereiche überschneiden, ist möglicherweise notwendig, die bestimmten Kontext auszuwerten, um zu bestimmen, ob ein bestimmtes Byte als führendes oder als nachfolgendes Byte verwendet wird.  
  
## Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)