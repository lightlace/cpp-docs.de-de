---
title: Compilerwarnung (Stufe 4) C4366 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4366
dev_langs:
- C++
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12410a567cb55d6dea74b8e5e595009e56b1071f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293701"
---
# <a name="compiler-warning-level-4-c4366"></a>Compilerwarnung (Stufe 4) C4366
Das Ergebnis des Operators "Operator" unärer möglicherweise nicht ausgerichteten sein.  
  
 Wenn ein Strukturmember jemals nicht ausgerichteten aufgrund der Komprimierung werden konnte, werden der Compiler beim informiert, dass die Adresse des Mitglieds einer ausgerichtete Zeiger zugewiesen ist. Standardmäßig werden alle Zeiger ausgerichtet.  
  
 Um C4366 zu beheben, ändern Sie die Ausrichtung der Struktur oder deklarieren den Zeiger mit dem [__unaligned](../../cpp/unaligned.md) Schlüsselwort.  
  
 Weitere Informationen finden Sie unter __unaligned und [Pack](../../preprocessor/pack.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4366 generiert.  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```