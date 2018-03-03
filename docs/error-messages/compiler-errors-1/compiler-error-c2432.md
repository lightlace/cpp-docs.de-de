---
title: Compilerfehler C2432 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e921fa0cd2a9c56b6449b554fcee307c1121c598
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2432"></a>Compilerfehler C2432
illegaler Verweis auf 16-Bit-Daten in 'Bezeichner'  
  
 Eine 16-Bit-Registrierung wird als ein Index oder ein Basisregister verwendet. Der Compiler unterstützt keine Verweise auf 16-Bit-Daten. 16-Bit-Register können nicht als Index oder Base-Registern verwendet werden, beim Kompilieren für 32-Bit-Code.  
  
 Im folgende Beispiel wird C2432 generiert:  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```