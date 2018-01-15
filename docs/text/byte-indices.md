---
title: Byteindizes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 594acadeedad06e9720180c38bd0bcd657391879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="byte-indices"></a>Byte-Indizes
Verwenden Sie die folgenden Tipps:  
  
-   Arbeiten mit einem byteweisen Index in eine Zeichenfolge zeigt Probleme durch Zeiger Bearbeitung ähnliche an Betrachten Sie dieses Beispiel hat eine Zeichenfolge für einen umgekehrten Schrägstrich überprüft:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Dies unter Umständen ein nachfolgendes Byte ist, kein führendes Byte ist, indiziert und kann daher nicht zum zeigen eine `character`.  
  
-   Verwenden der [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) Funktion zur Behebung des vorangehenden Problems:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Dies wird vorschriftsmäßig auf ein führendes Byte ist, werden daher zu einer `character`. Die `_mbclen` Funktion bestimmt die Größe eines Zeichens (1 oder 2 Bytes).  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Letztes Zeichen einer Zeichenfolge](../text/last-character-in-a-string.md)