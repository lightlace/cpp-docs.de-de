---
title: Inkrementieren und Dekrementieren von Zeigern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4fff5d7ec20ce052e4d831f1556432186ebc7bb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603359"
---
# <a name="incrementing-and-decrementing-pointers"></a>Inkrementieren und Dekrementieren von Zeigern
Verwenden Sie die folgenden Tipps:  
  
-   Zeigen Sie auf die führende Bytes, die nicht auf nachfolgende Bytes. Es ist in der Regel nicht sicher ist, um einen Zeiger auf ein nachfolgendes Byte zu erhalten. Normalerweise ist es sicherer, eine Zeichenfolge vorwärts und nicht in umgekehrter Reihenfolge zu scannen.  
  
-   Es gibt Zeiger Inkrement/Dekrement-Funktionen und Makros, die über ein ganzes Zeichen zu verschieben:  
  
    ```  
    sz1++;  
    ```  
  
     wird:  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     Die `_mbsinc` und `_mbsdec` Funktionen ordnungsgemäß Inkrement- und Dekrement-im `character` Einheiten, unabhängig von der Zeichengröße.  
  
-   Dekrementiert benötigen Sie einen Zeiger an den Anfang der Zeichenfolge an, wie im folgenden dargestellt:  
  
    ```  
    sz2--;  
    ```  
  
     wird:  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Alternativ dazu Ihre hauptzeiger ist möglicherweise auf ein gültiges Zeichen in der Zeichenfolge, sodass:  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Sie benötigen einen Zeiger auf eine gültige führenden Byte.  
  
-   Möglicherweise möchten Sie einen Zeiger auf das vorherige Zeichen für schnellere Aufrufe verwalten `_mbsdec`.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Byte-Indizes](../text/byte-indices.md)