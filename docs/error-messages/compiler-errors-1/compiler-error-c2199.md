---
title: Compilerfehler C2199 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2199
dev_langs:
- C++
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 28410dfc8ced15c7c3cddd55b5403f45d1b15e78
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2199"></a>Compilerfehler C2199
Syntaxfehler: gefunden ' Bezeichner ("im globalen Gültigkeitsbereich (war eine Deklaration beabsichtigt?)  
  
 Der angegebene Kontext verursachte einen Syntaxfehler. Es gibt möglicherweise falsche-Deklarationssyntax.  
  
 Im folgenden Beispiel wird C2199 generiert:  
  
```  
// C2199.cpp  
// compile with: /c  
int j = int(1) int(1);   // C2199  
int j = 1;   // OK  
```
