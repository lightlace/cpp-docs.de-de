---
title: Compilerwarnung (Stufe 1) C4618 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4618
dev_langs:
- C++
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e53f8542983a6e15f353ff181efa280815fea9d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282521"
---
# <a name="compiler-warning-level-1-c4618"></a>Compilerwarnung (Stufe 1) C4618
Pragma-Parameter enthalten eine leere Zeichenfolge; Pragma wird ignoriert  
  
 Eine null-Zeichenfolge wurde angegeben, als Argument an einen **#pragma**.  
  
 Das Pragma wurde ohne das Argument verarbeitet.  
  
 Im folgenden Beispiel wird C4618 generiert:  
  
```  
// C4618.cpp  
// compile with: /W1 /LD  
#pragma code_seg("")   // C4618  
```