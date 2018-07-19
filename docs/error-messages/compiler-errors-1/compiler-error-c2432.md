---
title: Compilerfehler C2432 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfbadf2c7d53cce799efbd5f10286b31bb3cd3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196934"
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