---
title: Compiler-Fehler C2640 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2640
dev_langs:
- C++
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6951d6d56fa0e93e75725c5ce5b13fec7f3d78f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2640"></a>Compiler-Fehler C2640 generiert
'Bezeichner': __based-Modifizierer auf Verweis unzulässig  
  
 Die `__based` Modifizierer kann nur für Zeiger verwendet werden.  
  
 Im folgende Beispiel wird C2640 generiert:  
  
```  
// C2640.cpp  
void f(int i) {  
    void *vp;  
    int _based(vp) &vr = I;  // C2640  
}  
```