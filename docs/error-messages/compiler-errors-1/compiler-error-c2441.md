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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 645e06a0685f00359d468a4a4b9bd3522921b511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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