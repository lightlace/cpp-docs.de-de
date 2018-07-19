---
title: Schwerwiegender Fehler C1016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1016
dev_langs:
- C++
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8a07f1fc36293b483772087b3325c7e0d0529e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226133"
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