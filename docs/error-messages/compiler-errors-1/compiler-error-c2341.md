---
title: Compilerfehler C2341 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18cc222129f3f12b5e7b5c6cb66e090907ff42a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197376"
---
# <a name="compiler-error-c2341"></a>Compilerfehler C2341
'Abschnittsname': Segment muss definiert werden, mithilfe von #pragma Data_seg, Code_seg oder vorherigen Abschnitt verwendet  
  
 Ein [zuordnen](../../cpp/allocate.md) Anweisung verweist auf ein Segment, das noch nicht durch definiert [Code_seg](../../preprocessor/code-seg.md), [Data_seg](../../preprocessor/data-seg.md), oder [Abschnitt](../../preprocessor/section.md) Pragmas.  
  
 Im folgende Beispiel wird C2341 generiert:  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 Mögliche Lösung:  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```