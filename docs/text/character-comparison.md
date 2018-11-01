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
ms.openlocfilehash: c3412939bac9dace6f3abaacda75ed73d6e60f21
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428069"
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