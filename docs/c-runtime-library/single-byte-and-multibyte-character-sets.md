---
title: "Einzelbyte- und Multibyte-Zeichensätze| Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.character.multibyte
dev_langs: C++
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9f7f9cfe98e243cb9eaa0252889b61e6c6019d89
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="single-byte-and-multibyte-character-sets"></a>Einzelbyte- und Mehrbyte-Zeichensätze
Mit dem ASCII-Zeichensatz werden Zeichen im Bereich von 0x00 bis 0x7F definiert. Von einigen anderen Zeichensätzen (hauptsächlich europäischer Herkunft) werden wie beim ASCII-Zeichensatz die Zeichen im Bereich von 0x00 bis 0x7F definiert; zusätzlich wird ein erweiterter Zeichensatz im Bereich von 0x80 bis 0xFF definiert. Daher ist ein Einzelbyte-Zeichensatz (Single-Byte Character Set, `SBCS`) mit 8 Bit ausreichend, um den ASCII-Zeichensatz sowie viele andere Zeichensätze für europäische Sprachen darzustellen. Einige außereuropäische Zeichensätze, z.B. das japanische Kanji, enthalten jedoch so viele Zeichen, dass sie nicht mehr in Einzelbytecodierung dargestellt werden können. Sie müssen daher mit einem Multibyte-Zeichensatz (Multibyte Character Set, `MBCS`) codiert werden.  
  
> [!NOTE]
>  Viele `SBCS`-Routinen in der Microsoft-Laufzeitbibliothek behandeln Multibyte-Bytes, Zeichen und Zeichenfolgen entsprechend. Viele Multibyte-Zeichensätze definieren den ASCII-Zeichensatz als Teilmenge. In vielen Multibyte-Zeichensätzen sind die Zeichen im Bereich von 0x00 bis 0x7F mit den gleichwertigen Zeichen des ASCII-Zeichensatzes identisch. Das ein Byte lange `NULL`-Zeichen ('\0') in `ASCII`- und `MBCS`-Zeichenfolgen hat z.B. den Wert 0x00 und steht für das abschließende NULL-Zeichen.  
  
 Ein Multibyte-Zeichensatz kann aus 1-Byte- und 2-Byte-Zeichen bestehen. Daher kann eine Multibyte-Zeichenfolge eine Mischung aus Einzelbyte- und Doppelbytezeichen enthalten. Ein 2-Byte-Multibytezeichen verfügt über ein führendes Byte und ein nachfolgendes Byte. In einem bestimmten Mehrbyte-Zeichensatz liegen die führenden Bytes ebenso wie die nachfolgenden Bytes innerhalb eines bestimmten Bereichs. Wenn sich diese Bereiche überschneiden, muss unter Umständen anhand des Kontexts ermittelt werden, ob ein bestimmtes Byte als führendes oder als nachfolgendes Byte verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)