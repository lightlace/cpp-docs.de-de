---
title: Compilerwarnung (Stufe 3) C4159 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4159
dev_langs:
- C++
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f335dedddd3e5c948a009f49c925c7d59901de1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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