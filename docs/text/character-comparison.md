---
title: Zeichenvergleich
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 206910d4b76f93a92ee5230a227d6f0346a85e61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615409"
---
# <a name="character-comparison"></a>Zeichenvergleich

Verwenden Sie die folgenden Tipps:

- Vergleichen von einem führenden Bytes mit einem ASCII-Zeichen ordnungsgemäß funktioniert:

    ```cpp
    if( *sz1 == 'A' )
    ```

- Vergleichen von zwei-unbekanntes Zeichen erfordert die Verwendung eines die Makros im Mbstring.h definiert:

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   Dadurch wird sichergestellt, dass beide Bytes von Double-Byte-Zeichen auf Gleichheit verglichen werden.

## <a name="see-also"></a>Siehe auch

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)<br/>
[Pufferüberlauf](../text/buffer-overflow.md)