---
title: Byteindizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5beb69ef7d9d3356eddef40c6bce6483079d934a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590799"
---
# <a name="byte-indices"></a>Byte-Indizes
Verwenden Sie die folgenden Tipps:  
  
-   Arbeiten mit einem byteweisen Index in einer Zeichenfolge stellt detaillierteste zeigermanipulation ähnliche Probleme. Betrachten Sie dieses Beispiel, das eine Zeichenfolge für einen umgekehrten Schrägstrich überprüft:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Dies kann ein nachfolgendes Byte, kein führendes Byte ist, indizieren und kann daher nicht auf verweist eine `character`.  
  
-   Verwenden der [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) Funktion, um das vorherige Problem zu lösen:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Dies richtig indiziert, um ein führendes Byte ist, werden daher auf eine `character`. Die `_mbclen` Funktion bestimmt die Größe eines Zeichens (1 oder 2 Bytes).  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Letztes Zeichen einer Zeichenfolge](../text/last-character-in-a-string.md)