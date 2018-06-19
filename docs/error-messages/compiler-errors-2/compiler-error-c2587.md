---
title: Compilerfehler C2587 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2587
dev_langs:
- C++
helpviewer_keywords:
- C2587
ms.assetid: 7637a2c7-35d4-4b5a-a8f2-515a7bda98fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 595e14f71f9e1570893111efa38155a6f97e5574
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228326"
---
# <a name="compiler-error-c2587"></a>Compilerfehler C2587
'Bezeichner': Unzulässige Verwendung der lokalen Variablen als Standardparameter  
  
 Lokale Variablen dürfen nicht als Standardparameter.  
  
 Im folgende Beispiel wird C2587 generiert:  
  
```  
// C2587.cpp  
// compile with: /c  
int i;  
void func() {  
   int j;  
   extern void func2( int k = j );  // C2587 -- local variable  
   extern void func3( int k = i );   // OK  
}  
```