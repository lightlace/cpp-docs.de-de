---
title: Compilerwarnung (Stufe 3) C4316 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4316
dev_langs:
- C++
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8aaa769ddab0f0fc297a153a3d12cacd23e3c12e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4316"></a>Compilerwarnung (Stufe 3) C4316
Das Objekt, das auf dem Heap zugewiesen wird, ist für diesen Typ möglicherweise nicht ausgerichtet.  
  
 Ein über-ausgerichtetes Objekt, das mithilfe von `operator new` zugeordnet wird, hat möglicherweise nicht die angegebene Ausrichtung. Überschreiben Sie [new-Operator](../../c-runtime-library/operator-new-crt.md) und [Delete-Operator](../../c-runtime-library/operator-delete-crt.md) für ausgerichtete Typen, sodass sie die ausgerichteten Reservierungsroutinen verwenden – z. B. [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) und [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Im folgenden Beispiel wird C4316 generiert:  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```