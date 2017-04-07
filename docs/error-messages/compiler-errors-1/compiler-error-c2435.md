---
title: Compilerfehler C2435 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 53a3144fe8e87f36a1a5149d292130a9913b646a
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-error-c2435"></a>Compilerfehler C2435
"Var": dynamische Initialisierung verwalteten CRT erfordert, kann nicht mit/clr: safe kompiliert werden  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Initialisierung des globalen pro-AppDomain-Variablen erfordert kompilierte die CRT mit `/clr:pure`, die ein überprüfbares Image erstellt.  
  
 Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md) und [Prozess](../../cpp/process.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2435 generiert:  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
