---
title: Compilerwarnung (Stufe 1) C4087 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4087
dev_langs:
- C++
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5b9962abc29b94425f96c978f3dd7e8d3f7c251
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278443"
---
# <a name="compiler-warning-level-1-c4087"></a>Compilerwarnung (Stufe 1) C4087
"Funktion": Mit "void"-Parameterliste deklariert  
  
 Die Funktionsdeklaration hat keine formalen Parameter, aber der Funktionsaufruf hat tatsächlich Parameter. Zusätzliche Parameter werden entsprechend der Aufrufkonvention der Funktion übergeben.  
  
 Diese Warnung gilt für den C-Compiler.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4087.c  
// compile with: /W1  
int f1( void ) {  
}  
  
int main() {  
   f1( 10 );   // C4087  
}  
```