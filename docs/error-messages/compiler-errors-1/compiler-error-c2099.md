---
title: Compilerfehler C2099 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2099
dev_langs: C++
helpviewer_keywords: C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44e5faccc28877793aa42c5fb765e6d21eb19a1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2099"></a>Compilerfehler C2099
Initialisierung ist keine Konstante  
  
 Dieser Fehler wird nur vom C-Compiler ausgegeben und tritt nur für nicht automatische Variablen auf.  Der Compiler initialisiert beim Programmstart nicht automatische Variablen und die Werte, mit denen sie initialisiert werden, müssen konstant sein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2099 generiert.  
  
```  
// C2099.c  
int j;  
int *p;  
j = *p;   // C2099 *p is not a constant  
```  
  
## <a name="example"></a>Beispiel  
 C2099 kann auch auftreten, da der Compiler keine Konstantenfaltung für einen Ausdruck unter **/fp:strict** ausführen kann, da die Umgebungseinstellung für die Gleitkommagenauigkeit (weitere Informationen finden Sie unter [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) ) möglicherweise zwischen Kompilierungs- und Laufzeit abweichen.  
  
 Wenn bei der Konstantenfaltung ein Fehler auftritt, ruft der Compiler die dynamische Initialisierung auf, die in C nicht zulässig ist.  
  
 Kompilieren Sie das Modul als CPP-Datei, oder vereinfachen Sie den Ausdruck, um diesen Fehler zu beheben.  
  
 Weitere Informationen finden Sie unter [/fp (Specify Floating-Point Behavior)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
 Im folgenden Beispiel wird C2099 generiert.  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```