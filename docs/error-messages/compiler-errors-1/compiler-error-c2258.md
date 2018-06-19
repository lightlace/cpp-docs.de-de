---
title: Compilerfehler C2258 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2258
dev_langs:
- C++
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d0e976edda871646a5bfa6c994d303a276b2f4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167950"
---
# <a name="compiler-error-c2258"></a>Compilerfehler C2258
Ungültige Syntax für rein virtuelle Methode; "= 0" erforderlich  
  
 Eine reine virtuelle Funktion ist mit einer falschen Syntax deklariert.  
  
 Im folgenden Beispiel wird C2258 generiert:  
  
```  
// C2258.cpp  
// compile with: /c  
class A {  
public:  
   void virtual func1() = 1; // C2258  
   void virtual func2() = 0;   // OK  
};  
```