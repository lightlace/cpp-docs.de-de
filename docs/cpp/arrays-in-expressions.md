---
title: "Arrays in Ausdrücken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ec97fba837ffae0a03ff8d4fc3d85c4011aa59c6
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="arrays-in-expressions"></a>Arrays in Ausdrücken
Wenn ein Bezeichner eines Arraytyps tritt in einem Ausdruck außer `sizeof`, Adresse des (**&**), oder Initialisieren eines Verweises, konvertiert es in einen Zeiger auf das erste Arrayelement. Zum Beispiel:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 Der Zeiger `psz` zeigt auf das erste Element des Arrays `szError1`. Beachten Sie, dass Arrays, im Gegensatz zu Zeigern, nicht veränderbare l-Werte sind. Daher ist die folgende Zuordnung ungültig:  
  
```  
szError1 = psz;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../cpp/arrays-cpp.md)
