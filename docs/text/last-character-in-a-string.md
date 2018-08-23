---
title: Letzte Zeichen in einer Zeichenfolge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c5783fcdb1bccbfe7e2a316fa1ea4285519bb1b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593557"
---
# <a name="last-character-in-a-string"></a>Letztes Zeichen einer Zeichenfolge
Verwenden Sie die folgenden Tipps:  
  
-   Nachfolgendes Byte-Bereiche überschneiden sich in vielen Fällen den ASCII-Zeichensatz. Sie können problemlos byteweise Scanvorgänge für Steuerzeichen (weniger als 32) verwenden.  
  
-   Beachten Sie die folgende Zeile des Codes, der überprüft werden kann, um festzustellen, ob das letzte Zeichen in einer Zeichenfolge ein umgekehrter Schrägstrich ist:  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     Da `strlen` ist nicht MBCS-fähig ist, wird die Anzahl der Bytes, die nicht die Anzahl der Zeichen in einer multibyte-Zeichenfolge. Beachten Sie auch, die in einigen Codepages (z. B. 932), "\\" (0x5c) ist ein gültiges nachfolgendes Byte (`sz` ist eine C-Zeichenfolge).  
  
     Eine mögliche Lösung ist den Code auf diese Weise neu schreiben:  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     Dieser Code verwendet die MBCS-Funktionen `_mbsrchr` und `_mbsinc`. Da diese Funktionen MBCS-fähig sind, unterscheiden sie zwischen einem "\\'Zeichen und ein nachfolgendes Byte'\\". Der Code führt eine Aktion aus, wenn das letzte Zeichen in der Zeichenfolge ein NULL-Wert ('\0') ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Zeichenzuweisungen](../text/character-assignment.md)