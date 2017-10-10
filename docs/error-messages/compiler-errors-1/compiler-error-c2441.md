---
title: Compilerfehler C2441 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6868feadda4c0c0f3d65a86c77a403b8965fded5
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2441"></a>Compilerfehler C2441
'Variable': ein Symbol mit __declspec(process) deklariertes muss const in/CLR: pure-Modus  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Standardmäßig sind Variablen pro Anwendungsdomäne unter **/CLR: pure**. Markiert eine Variable `__declspec(process)` unter **/CLR: pure** fehleranfällig, wenn in einer Anwendungsdomäne geändert und in einer anderen gelesen wird.  
  
 Aus diesem Grund erzwingt der Compiler prozessspezifische Variablen `const` unter **/CLR: pure**, machen sie lesen nur in allen Anwendungsdomänen.  
  
 Weitere Informationen finden Sie unter [Prozess](../../cpp/process.md) und [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2441 generiert.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```
