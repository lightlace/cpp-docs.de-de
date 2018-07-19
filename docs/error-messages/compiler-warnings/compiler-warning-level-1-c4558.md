---
title: Compilerwarnung (Stufe 1) C4558 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4558
dev_langs:
- C++
helpviewer_keywords:
- C4558
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 852e3d3e8bb1c8186232cbed2636ac890b0cd057
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282459"
---
# <a name="compiler-warning-level-1-c4558"></a>Compilerwarnung (Stufe 1) C4558
Wert des Operanden 'Value' ist außerhalb des gültigen Bereichs "Untergrenze - Obergrenze"  
  
 Die an eine Anweisung Assemblysprache übergebene Wert ist außerhalb des Bereichs für den Parameter angegeben. Der Wert wird abgeschnitten.  
  
 Im folgenden Beispiel wird C4558 generiert:  
  
```  
// C4558.cpp  
// compile with: /W1  
// processor: x86  
void asm_test() {  
   __asm pinsrw   mm1, eax, 8;   // C4558  
}  
  
int main() {  
}  
```