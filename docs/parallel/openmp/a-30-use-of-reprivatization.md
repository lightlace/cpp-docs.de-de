---
title: A.30 Verwendung von Reprivatization | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 26529090-6c39-40f2-b806-e12374d6b5f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b8a6bedad37e9edd70edd014a9dd8f70143bbe5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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