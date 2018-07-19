---
title: Inkrementieren und Dekrementieren von Zeigern | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82a6f792ce622481cbbab821b8a5446186bd692d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857128"
---
# <a name="incrementing-and-decrementing-pointers"></a>Inkrementieren und Dekrementieren von Zeigern
Verwenden Sie die folgenden Tipps:  
  
-   Zeigen Sie auf führende Bytes, die nicht auf nachfolgende Bytes. Es ist in der Regel unsicher, einen Zeiger auf ein nachfolgendes Byte haben. Normalerweise ist es sicherer, eine Zeichenfolge vorwärts statt in umgekehrter Reihenfolge zu scannen.  
  
-   Es gibt Zeiger-Inkrement/Dekrement Funktionen und Makros, die über ein ganzes Zeichen zu verschieben:  
  
    ```  
    sz1++;  
    ```  
  
     wird:  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     Die `_mbsinc` und `_mbsdec` Funktionen ordnungsgemäß Inkrementieren und Dekrementieren `character` Einheiten, unabhängig von der Zeichengröße.  
  
-   Dekrementiert benötigen Sie einen Zeiger an den Anfang der Zeichenfolge, wie im folgenden dargestellt:  
  
    ```  
    sz2--;  
    ```  
  
     wird:  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Alternativ können Sie der Hauptknoten Zeiger könnte darin bestehen, ein gültiges Zeichen in der Zeichenfolge so, dass:  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Sie benötigen einen Zeiger auf eine gültige führenden Bytes.  
  
-   Möglicherweise möchten Sie verwalten einen Zeiger auf das vorherige Zeichen für schnellere Aufrufe `_mbsdec`.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Byte-Indizes](../text/byte-indices.md)