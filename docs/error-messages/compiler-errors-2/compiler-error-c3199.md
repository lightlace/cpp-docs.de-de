---
title: Compiler-Fehler C3199 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cddad2218e81603f59cad51e3a684303e144171e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246570"
---
# <a name="compiler-error-c3199"></a>Compiler-Fehler C3199 generiert
Ungültige Verwendung eines Gleitkommapragmas: Ausnahmen werden in nicht-präzisen Modus nicht unterstützt.  
  
 Die [Float_control](../../preprocessor/float-control.md) Pragma wurde zur Gleitkommaausnahme-Modell unter Angabe einer [/fp](../../build/reference/fp-specify-floating-point-behavior.md) andere Einstellung als **/fp: präzise**.  
  
 Im folgende Beispiel wird C3199 generiert:  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```