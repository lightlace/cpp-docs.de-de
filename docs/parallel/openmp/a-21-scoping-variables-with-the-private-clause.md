---
title: A.21 Bereichsdefinition von Variablen mit der private-Klausel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ad2258da592bb68c5eae9e52e85e63a161a24b5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690506"
---
# <a name="a21---scoping-variables-with-the-private-clause"></a>A.21   Bereichsauswahl für Variablen mit der private-Klausel
Die Werte der `i` und `j` im folgenden Beispiel werden nicht auf die Beendigung des parallelen Bereichs definiert:  
  
```  
int i, j;  
i = 1;  
j = 2;  
#pragma omp parallel private(i) firstprivate(j)  
{  
  i = 3;  
  j = j + 2;  
}  
printf_s("%d %d\n", i, j);  
```  
  
 Weitere Informationen zu den `private` -Klausel finden Sie unter [Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf der Seite "25".