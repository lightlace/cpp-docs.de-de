---
title: Lesen von Bereichen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0892c38d6448ed28a309c8c9864d78dc9aeb4a28
ms.lasthandoff: 04/01/2017

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
