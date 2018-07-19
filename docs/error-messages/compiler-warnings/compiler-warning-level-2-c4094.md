---
title: Compilerwarnung (Stufe 2) C4094 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4094
dev_langs:
- C++
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9deae6a0e21fcb7dd4f09de07e65445dc9595932
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290503"
---
# <a name="compiler-warning-level-2-c4094"></a>Compilerwarnung (Stufe 2) C4094
Unbenanntes 'token' deklariert keine Symbole  
  
 Der Compiler hat eine leere Deklaration einer unbenannten Struktur, Union oder Klasse an. Die Deklaration wird ignoriert.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 Diese Bedingung generiert einen Fehler unter ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)).