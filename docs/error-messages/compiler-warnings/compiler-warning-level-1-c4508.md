---
title: Compilerwarnung (Stufe 1) C4508 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53f152c2f3573e5f3bd7b8e9be0603ed6d3f11bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283195"
---
# <a name="compiler-warning-level-1-c4508"></a>Compilerwarnung (Stufe 1) C4508
'Funktion': Funktion sollte einen Wert zurückgeben "void" Rückgabetyp davon ausgegangen, dass  
  
 Die Funktion weist kein Rückgabetyp angegeben. In diesem Fall C4430 ebenfalls ausgelöst, und der Compiler implementiert die Korrektur C4430 (Standardwert ist Int) gemeldet.  
  
 Um diese Warnung zu beheben, müssen deklarieren Sie den Rückgabetyp der Funktionen explizit.  
  
 Im folgenden Beispiel wird C4508 generiert:  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```