---
title: Vergleich Zeichen | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b969783a19c0836a8ab81d75820fc688df3ef31e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854950"
---
# <a name="character-comparison"></a>Zeichenvergleich
Verwenden Sie die folgenden Tipps:  
  
-   Vergleichen von einem führenden Bytes mit einem ASCII-Zeichen ordnungsgemäß funktioniert:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   Vergleichen von zwei unbekannte Zeichen erfordert die Verwendung eines Makros in Mbstring.h definiert:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Dadurch wird sichergestellt, dass beide Bytes, der einen Doppelbyte Zeichensatz auf Gleichheit verglichen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Pufferüberlauf](../text/buffer-overflow.md)