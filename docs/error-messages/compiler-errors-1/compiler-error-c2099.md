---
title: Compilerfehler C2099 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 74fdc75470600c29029c52e38ab2073e484dbde6
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

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
 C2099 kann auch auftreten, da der Compiler keine konstantenfaltung für einen Ausdruck unter Ausführen **/fp: strict** , da die gleitkommagenauigkeit Umgebung (finden Sie unter [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) für Weitere Informationen) unterscheidet sich möglicherweise von der Kompilierung zur Laufzeit.  
  
 Wenn bei der Konstantenfaltung ein Fehler auftritt, ruft der Compiler die dynamische Initialisierung auf, die in C nicht zulässig ist.  
  
 Kompilieren Sie das Modul als CPP-Datei, oder vereinfachen Sie den Ausdruck, um diesen Fehler zu beheben.  
  
 Weitere Informationen finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
 Im folgenden Beispiel wird C2099 generiert.  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```
