---
title: Schwerwiegender Fehler C1016 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1016
dev_langs:
- C++
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ef8e1547b636ec6722daca3f73639d8e1db42d5f
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1016"></a>Schwerwiegender Fehler C1016
\##ifdef erwartet ein Bezeichner #ifndef ein Bezeichner erwartet.  
  
 In der Direktive für die bedingte Kompilierung ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) oder `#ifndef`) fehlt ein Bezeichner für die Auswertung. Geben Sie einen Bezeichner an, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C1016 generiert:  
  
```  
// C1016.cpp  
#ifdef   // C1016  
#define FC1016  
#endif  
  
int main() {}  
```  
  
 Mögliche Lösung:  
  
```  
// C1016b.cpp  
#ifdef X  
#define FC1016  
#endif  
  
int main() {}  
```
