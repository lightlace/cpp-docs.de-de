---
title: Lesen von Bereichen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 96748c24fbf1e5adfebb72ba809533afeafebe38
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="reading-ranges"></a>Lesen von Bereichen
**ANSI 4.9.6.2** Die Interpretation eines Bindestriches (-), der weder das erste noch das letzte Zeichen in der Suchliste der „% [“-Konvertierung in der `fscanf`-Funktion ist  
  
 Die folgende Zeile  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 liest eine beliebige Anzahl von Zeichen im Bereich von A-Z in der Zeichenfolge, auf die `strptr` zeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
