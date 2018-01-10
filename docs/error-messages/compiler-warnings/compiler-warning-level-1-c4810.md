---
title: Compilerwarnung (Stufe 1) C4810 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4810
dev_langs: C++
helpviewer_keywords: C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 652aef44e86e1395ae9faa1d29d3ffe99473c76c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4810"></a>Compilerwarnung (Stufe 1) C4810
Wert von pragma pack(show) == n  
  
 Diese Warnung wird ausgegeben, wenn Sie die **show** -Option des [pack](../../preprocessor/pack.md) -Pragmas verwenden. *n* ist der aktuelle pack-Wert.  
  
 Der folgende Code zeigt z. B. die Funktionsweise der C4810-Warnung mit dem pack-Pragma:  
  
```  
// C4810.cpp  
// compile with: /W1 /LD  
// C4810 expected  
#pragma pack(show)  
#pragma pack(4)  
#pragma pack(show)  
```