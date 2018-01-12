---
title: Compilerwarnung (Stufe 2) C4056 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4056
dev_langs: C++
helpviewer_keywords: C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78b95111e69cdb8b27e65654fbf64756786d2097
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4056"></a>Compilerwarnung (Stufe 2) C4056 generiert
in der Gleitkommaarithmetik Konstanten "Überlauf"  
  
 Konstante Gleitkommazahlen generiert ein Ergebnis, das den maximalen zulässigen Wert überschreitet.  
  
 Diese Warnung kann durch compileroptimierungen, die während der Arithmetik ausgeführt verursacht werden. Sie können diese Warnung gefahrlos ignorieren, wenn er beendet wurde, wenn Sie durch Deaktivieren der Optimierung ([/Od](../../build/reference/od-disable-debug.md)).  
  
 Im folgende Beispiel wird C4056 generiert:  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```