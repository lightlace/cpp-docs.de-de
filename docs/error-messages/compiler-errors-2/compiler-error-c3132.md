---
title: Compiler-Fehler C3132 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3132
dev_langs:
- C++
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb2ecc863bc06542e4bb2e78e71ce95279c004f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252386"
---
# <a name="compiler-error-c3132"></a>Compiler-Fehler C3132 generiert
'Funktion-Parameter': Parameterarrays können nur auf einem formalen Argument vom Typ "eindimensionalem verwalteten Arrays" angewendet werden  
  
 Die [ParamArray](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx) Attribut auf einen Parameter, die keine eindimensionale Arrays angewendet wurde.  
  
 Im folgende Beispiel wird C3132 generiert:  
  
```  
// C3132.cpp  
// compile with: /clr /c  
using namespace System;  
void f( [ParamArray] Int32[,] );   // C3132  
void g( [ParamArray] Int32[] );   // C3132  
  
void h( [ParamArray] array<Char ^> ^ MyArray );   // OK  
  
```