---
title: Compilerfehler C2099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28f525676f6d9238838f0dbc245d9771f99ebeb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170816"
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