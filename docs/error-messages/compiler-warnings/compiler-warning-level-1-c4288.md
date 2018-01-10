---
title: Compilerwarnung (Stufe 1) C4288 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4288
dev_langs: C++
helpviewer_keywords: C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a10a7573df5986ed20475b34208a1e0f301d9bb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4288"></a>Compilerwarnung (Stufe 1) C4288
nicht dem Standard entsprechende Erweiterung: 'Var': Loop-Steuerelementvariable, die in der for-Schleife deklariert wird, außerhalb des for-Schleife; Es steht in Konflikt mit der Deklaration im äußeren Gültigkeitsbereich  
  
 Beim Kompilieren mit ["/ Ze"](../../build/reference/za-ze-disable-language-extensions.md) und **/Zc: forScope**, eine Variable deklariert, die einer **für** Schleife verwendet wurde, nach der [für](../../cpp/for-statement-cpp.md)-Schleife-Bereich. Eine Microsoft-Erweiterung der Programmiersprache C++ ermöglicht dieser Variablen im Gültigkeitsbereich bleibt und C4288 erinnert Sie daran, dass die erste Deklaration der Variablen nicht verwendet wird.  
  
 Finden Sie unter [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) Informationen an den Microsoft-Erweiterung in **für** Schleifen mit "/ Ze".  
  
 Im folgenden Beispiel wird C4288 generiert:  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```