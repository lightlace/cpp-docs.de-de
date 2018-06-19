---
title: Compilerfehler C2423 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2423
dev_langs:
- C++
helpviewer_keywords:
- C2423
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c96408323c7afd9e15fee521c9d20005dfc6da21
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33195853"
---
# <a name="compiler-error-c2423"></a>Compilerfehler C2423
'Anzahl': Ungültige Skalierung  
  
 Inline-Assemblycode verwendet eine Zahl ungleich 1, 2, 4 oder 8, um die Skalierung eines Registers.  
  
 Im folgende Beispiel wird C2423 generiert:  
  
```  
// C2423.cpp  
// processor: x86  
int main() {  
   _asm {  
      lea EAX, [EAX*3]   // C2423  
      lea EAX, [EAX+EAX*2]   // OK  
   }  
}  
```