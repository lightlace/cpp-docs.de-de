---
title: A.30 Verwendung von Reprivatization | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 26529090-6c39-40f2-b806-e12374d6b5f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6026bba31fcc0db4e28ced14b3e847ac0cf8bf58
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689609"
---
# <a name="a30---use-of-reprivatization"></a>A.30   Verwenden der erneuten Privatisierung
Das folgende Beispiel zeigt die Reprivatization von Variablen. Private Variablen können gekennzeichnet werden, `private` erneut in einer geschachtelten-Direktive. Sie müssen nicht in den einschließenden parallelen Bereich gemeinsam genutzt werden.  
  
```  
int i, a;  
...  
#pragma omp parallel private(a)  
{  
  ...  
  #pragma omp parallel for private(a)  
  for (i=0; i<10; i++)  
     {  
       ...  
     }  
}  
```