---
title: Compilerwarnung (Stufe 1) C4228 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4228
dev_langs:
- C++
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 023bf60930a53b6bd881680caebb78c151406df4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276789"
---
# <a name="compiler-warning-level-1-c4228"></a>Compilerwarnung (Stufe 1) C4228
nicht dem Standard entsprechende Erweiterung: Qualifizierer nach dem Komma in Deklaratorliste werden ignoriert.  
  
 Die Verwendung der Qualifizierer wie **const** oder `volatile` nachdem ein Komma, wenn es sich bei der Deklaration von Variablen eine Microsoft-Erweiterung ist (["/ Ze"](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>Beispiel  
  
```  
// C4228.cpp  
// compile with: /W1  
int j, const i = 0;  // C4228  
int k;  
int const m = 0;  // ok  
int main()  
{  
}  
```