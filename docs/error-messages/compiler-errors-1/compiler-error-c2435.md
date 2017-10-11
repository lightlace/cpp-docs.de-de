---
title: Compilerfehler C2435 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b70ebf347e2d5b6af8938e348a5e789412241256
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
