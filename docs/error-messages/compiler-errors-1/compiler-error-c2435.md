---
title: Compilerfehler C2435 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44c4dec71cdf077dc8fbd1ba81b555090b524007
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2435"></a>Compilerfehler C2435
"Var": dynamische Initialisierung verwalteten CRT erfordert, kann nicht mit/clr: safe kompiliert werden  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Initialisierung des globalen pro-AppDomain-Variablen erfordert kompilierte die CRT mit `/clr:pure`, die ein überprüfbares Image erstellt.  
  
 Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2435 generiert:  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```