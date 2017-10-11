---
title: Compilerfehler Fehler C2021 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2021
dev_langs:
- C++
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d87775cb88579cae93e4de208b1386ab067a07b8
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2021"></a>Compilerfehler Fehler C2021
Exponentwert erwartet und nicht „character“.  
  
 Das Zeichen als Exponent einer Gleitkommakonstanten verwendet ist keine gültige Zahl. Achten Sie darauf, dass Sie einen Exponenten zu verwenden, der in Reichweite ist.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2021 generiert:  
  
```  
// C2021.cpp  
float test1=1.175494351E;   // C2021  
```  
  
## <a name="example"></a>Beispiel  
 Mögliche Lösung:  
  
```  
// C2021b.cpp  
// compile with: /c  
float test2=1.175494351E8;  
```
