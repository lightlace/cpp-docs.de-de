---
title: "Eine einfache Schleife parallel ausgeführten a. 1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2c6cfe794b9d7f50d7e12b8d2f444628ec6d79f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   Parallele Ausführung einer einfachen Schleife
Im folgende Beispiel wird veranschaulicht, wie eine einfache Schleife mit parallelisiert werden die `parallel for` Richtlinie ([Abschnitt 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) auf Seite "16"). Die Schleifeniterationsvariable ist standardmäßig privat, daher ist es nicht notwendig, explizit in eine private-Klausel angeben.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```