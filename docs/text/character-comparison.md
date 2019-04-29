---
title: Zeichenvergleich
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 075a22634f254c2ea634a1171ee157971fe5918e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410693"
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
