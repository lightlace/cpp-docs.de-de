---
title: Compilerwarnung (Stufe 1) C4293 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4293
dev_langs:
- C++
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ad588b69db1a0b46efa708b472bfc2218d17c0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277126"
---
# <a name="compiler-warning-level-1-c4293"></a>Compilerwarnung (Stufe 1) C4293
'Operator': Verschiebung negativ oder zu groß, ein nicht definiertes Verhalten  
  
 Wenn eine Schicht Anzahl negativ oder zu groß ist, ist das Verhalten des resultierenden Bildes undefiniert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4293 generiert:  
  
```  
// C4293.cpp  
// compile with: /c /W1  
unsigned __int64 combine (unsigned lo, unsigned hi) {  
  
   return (hi << 32) | lo;   // C4293  
  
   // try the following line instead  
   // return ( (unsigned __int64)hi << 32) | lo;  
}  
```