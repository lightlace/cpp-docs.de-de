---
title: Letzte Zeichen in einer Zeichenfolge | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88cde1d2eb30103462f7ae8f8c06274a2977fc36
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="last-character-in-a-string"></a>Letztes Zeichen einer Zeichenfolge
Verwenden Sie die folgenden Tipps:  
  
-   Nachfolgendes Byte Adressbereiche überlappen den ASCII-Zeichensatz in vielen Fällen. Sie können problemlos byteweise Scanvorgänge für alle Steuerzeichen (kleiner als 32) verwenden.  
  
-   Betrachten Sie die folgende Codezeile, die überprüft werden kann, um festzustellen, ob das letzte Zeichen in einer Zeichenfolge ein umgekehrter Schrägstrich ist:  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     Da `strlen` ist nicht MBCS-fähig ist, wird die Anzahl der Bytes, nicht die Anzahl von Zeichen in einem multibyte-Zeichenfolge zurückgegeben. Beachten Sie auch, die in einigen Codepages (z. B. 932) "\\" (0x5c) ist ein gültiges nachfolgendes Byte (`sz` ist eine C-Zeichenfolge).  
  
     Eine mögliche Lösung besteht darin, den Code auf diese Weise umzuschreiben:  
  
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