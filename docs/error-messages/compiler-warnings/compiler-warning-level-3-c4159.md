---
title: Compilerwarnung (Stufe 3) C4159 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4159
dev_langs:
- C++
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 139a21f5fbb7ce279d96f9df8be6008c2f092287
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291670"
---
# <a name="compiler-warning-level-3-c4159"></a>Compilerwarnung (Stufe 3) C4159
\#Pragma-pragma(pop,...): wurde per pop ausgelesen zuvor per push abgelegten Bezeichner "Identifier"  
  
 Enthält der Quellcode einem **Push** -Anweisung mit einem Bezeichner für ein Pragma, gefolgt von einer **pop** -Anweisung ohne Bezeichner. Folglich ***Bezeichner*** wird per pop ausgelesen, und nachfolgende Verwendungen von ***Bezeichner*** führen möglicherweise zu unerwartetem Verhalten.  
  
 Um diese Warnung zu vermeiden, geben Sie einen Bezeichner der **pop** Anweisung. Zum Beispiel:  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```