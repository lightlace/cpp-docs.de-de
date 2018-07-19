---
title: Compilerwarnung (Stufe 1) C4103 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4103
dev_langs:
- C++
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f072db4a260d2c83d1dd4b373630cd6e585efc2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284731"
---
# <a name="compiler-warning-level-1-c4103"></a>Compilerwarnung (Stufe 1) C4103 generiert
'Dateiname': Ausrichtung, die geändert, nachdem die Header, einschließlich möglicherweise aufgrund fehlender #pragma pack(pop)  
  
 Der Verpackung beeinflusst das Layout der Klassen und häufig, wenn Änderungen in Headerdateien packen, treten möglicherweise Probleme.  
  
 Verwenden Sie #pragma [Pack](../../preprocessor/pack.md)(pop) vor dem Beenden der Headerdatei, um diese Warnung zu beheben.  
  
 Im folgende Beispiel wird C4103 generiert:  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 und anschließend  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```