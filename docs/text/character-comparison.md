---
title: Vergleich Zeichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 246801abcb04cc8d9c2fd1a005183501bde240d1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612325"
---
# <a name="character-comparison"></a>Zeichenvergleich
Verwenden Sie die folgenden Tipps:  
  
-   Vergleichen von einem führenden Bytes mit einem ASCII-Zeichen ordnungsgemäß funktioniert:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   Vergleichen von zwei-unbekanntes Zeichen erfordert die Verwendung eines die Makros im Mbstring.h definiert:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Dadurch wird sichergestellt, dass beide Bytes von Double-Byte-Zeichen auf Gleichheit verglichen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Pufferüberlauf](../text/buffer-overflow.md)