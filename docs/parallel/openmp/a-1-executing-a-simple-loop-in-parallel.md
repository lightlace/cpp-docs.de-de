---
title: "Eine einfache Schleife parallel ausgeführten a. 1 | Microsoft Docs"
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
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8e425363b81954a72d0eb08491c384c47c695d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   Parallele Ausführung einer einfachen Schleife
Im folgende Beispiel wird veranschaulicht, wie eine einfache Schleife mit parallelisiert werden die `parallel for` Richtlinie ([Abschnitt 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) auf Seite "16"). Die Schleifeniterationsvariable ist standardmäßig privat, daher ist es nicht notwendig, explizit in eine private-Klausel angeben.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```