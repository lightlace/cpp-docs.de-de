---
title: Compilerfehler C2388 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2388
dev_langs:
- C++
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38ce3de47355dea18f2c2deca8cfe07cde4d313f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2388"></a>Compilerfehler C2388
'Symbol': ein Symbol kann nicht mit beiden __declspec(appdomain) deklariert werden und \__declspec(process)  
  
 Die Modifizierer `appdomain` und `process` `__declspec` können nicht für dasselbe Symbol verwendet werden. Der Speicher für eine Variable ist pro Prozess- oder Anwendungsdomäne vorhanden.  
  
 Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).  
  
 Im folgenden Beispiel wird C2388 generiert:  
  
```  
// C2388.cpp  
// compile with: /clr /c  
__declspec(process) __declspec(appdomain) int i;   // C2388  
__declspec(appdomain) int i;   // OK  
```