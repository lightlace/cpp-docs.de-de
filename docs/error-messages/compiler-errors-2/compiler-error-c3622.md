---
title: Compilerfehler C3622 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d8c7ab18bfba899c2df41becb457ed2e7725f81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3622"></a>Compilerfehler C3622
'Klasse': eine Klasse deklariert, wie 'Schlüsselwort' kann nicht instanziiert werden  
  
Es wurde versucht, beim Instanziieren einer Klasse, die als gekennzeichnete [abstrakte](../../windows/abstract-cpp-component-extensions.md). Eine Klasse als markiert `abstract` können eine Basisklasse sein, aber nicht instanziiert werden.  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird C3622 generiert.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
