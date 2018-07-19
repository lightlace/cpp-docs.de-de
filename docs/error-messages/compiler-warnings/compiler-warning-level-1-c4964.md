---
title: Compilerwarnung (Stufe 1) C4964 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4964
dev_langs:
- C++
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98226b2da465d2301356939273d370d76edcb64e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290315"
---
# <a name="compiler-warning-level-1-c4964"></a>Compilerwarnung (Stufe 1) C4964
Es wurden keine Optimierungsoptionen angegeben. Profilinformationen werden nicht gesammelt werden  
  
 [/ GL](../../build/reference/gl-whole-program-optimization.md) und [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) angegeben wurden, aber keine Optimierungen angefordert wurden, damit keine PGC-Dateien generiert werden und daher keine Profilgesteuerte Optimierungen ist möglich.  
  
 Wenn PGC-Dateien generiert werden, wenn Sie die Anwendung ausgeführt werden soll, geben Sie einen von der [/o](../../build/reference/o-options-optimize-code.md) Compileroptionen.  
  
 Im folgenden Beispiel wird C4964 generiert:  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```