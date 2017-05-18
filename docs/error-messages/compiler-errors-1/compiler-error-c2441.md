---
title: Compiler-Fehler C2441 generiert | Microsoft-Dokumentation
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 1b98c85df0db4e947ceb5722715f5d020e1ecbec
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2441"></a>Compilerfehler C2441
'Variable': ein mit __declspec(process) deklariertes muss konstant sein in/CLR: pure-Modus  
  
 Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 veraltet sind.  
  
 Variablen werden standardmäßig pro Anwendungsdomäne unter **/CLR: pure**. Markiert eine Variable `__declspec(process)` unter **/CLR: pure** fehleranfällig, wenn in einer Anwendungsdomäne geändert und in einer anderen gelesen wird.  
  
 Aus diesem Grund erzwingt der Compiler Variablen `const` unter **/CLR: pure**, machen sie lesen nur in allen Anwendungsdomänen.  
  
 Weitere Informationen finden Sie unter [Prozess](../../cpp/process.md) und [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2441 generiert.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```
