---
title: Compilerfehler C3132 | Microsoft-Dokumentation
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
ms.openlocfilehash: bb32d65b119330e49773118e38e1c8b618d03cfc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204757"
---
# <a name="compiler-error-c3132"></a>Compilerfehler C3132
"Funktion-Parameter": Parameterarrays können nur auf formale Argumente vom Typ "eindimensionales verwaltetes Array" angewendet werden  
  
 Die [ParamArray](https://msdn.microsoft.com/library/system.paramarrayattribute.aspx) -Attribut wurde auf einen Parameter, der kein eindimensionales Array war angewendet.  
  
 Im folgende Beispiel wird die C3132 generiert:  
  
```  
// C3132.cpp  
// compile with: /clr /c  
using namespace System;  
void f( [ParamArray] Int32[,] );   // C3132  
void g( [ParamArray] Int32[] );   // C3132  
  
void h( [ParamArray] array<Char ^> ^ MyArray );   // OK  
  
```