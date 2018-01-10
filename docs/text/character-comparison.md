---
title: Vergleich Zeichen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28c2cd3a2e868a595d73d06b5cae8e71ec8cc313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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