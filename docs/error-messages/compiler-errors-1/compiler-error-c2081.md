---
title: Compiler-Fehler C2081 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 165217b3ea4d50dc965927419786a01a6cc92af3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166860"
---
# <a name="compiler-error-c2081"></a>Compiler-Fehler C2081 generiert
'Bezeichner': Name in der formalen Parameter ist ungültig  
  
 Der Bezeichner verursacht einen Syntaxfehler.  
  
 Dieser Fehler kann verursacht werden, mithilfe des alten Stils für die Liste der formalen Parameter. Sie müssen den Typ des formalen Parameter in der Liste der formalen Parameter angeben.  
  
 Im folgende Beispiel wird C2081 generiert:  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 Mögliche Lösung:  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```