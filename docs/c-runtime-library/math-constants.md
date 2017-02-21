---
title: "Math-Konstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.constants"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_USE_MATH_DEFINES-Konstante"
  - "Konstanten, Math"
  - "M_1_PI-Konstante"
  - "M_2_PI-Konstante"
  - "M_2_SQRTPI-Konstante"
  - "M_E-Konstante"
  - "M_LN10-Konstante"
  - "M_LN2-Konstante"
  - "M_LOG10E-Konstante"
  - "M_LOG2E-Konstante"
  - "M_PI-Konstante"
  - "M_PI_2-Konstante"
  - "M_PI_4-Konstante"
  - "M_SQRT1_2-Konstante"
  - "M_SQRT2-Konstante"
  - "math-Konstanten"
  - "USE_MATH_DEFINES-Konstante"
ms.assetid: db533c3f-6ae8-4520-9d35-c8fabbef3529
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Math-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
#define _USE_MATH_DEFINES // for C++  
#include <cmath>  
  
#define _USE_MATH_DEFINES // for C  
#include <math.h>  
```  
  
## Hinweise  
 Die folgenden Symbole werden für die Werte ihrer angegebenen Ausdrücke definiert:  
  
|Symbol|Ausdruck|Wert|  
|------------|--------------|----------|  
|M\_E|e|2.71828182845904523536|  
|M\_LOG2E|log2 \(e\)|1.44269504088896340736|  
|M\_LOG10E|log10 \(e\)|0.434294481903251827651|  
|M\_LN2|ln \(2\)|0.693147180559945309417|  
|M\_LN10|ln \(10\)|2.30258509299404568402|  
|M\_PI|Pi|3.14159265358979323846|  
|M\_PI\_2|pi\/2|1.57079632679489661923|  
|M\_PI\_4|pi\/4|0.785398163397448309616|  
|M\_1\_PI|1\/pi|0.318309886183790671538|  
|M\_2\_PI|2\/pi|0.636619772367581343076|  
|M\_2\_SQRTPI|2\/sqrt\(pi\)|1.12837916709551257390|  
|M\_SQRT2|sqrt \(2\)|1.41421356237309504880|  
|M\_SQRT1\_2|1\/sqrt \(2\)|0.707106781186547524401|  
  
 Mathematische Konstanten werden nicht in Standard\-C\/C\+\+ definiert.  Um sie zu verwenden, müssen Sie zunächst `_USE_MATH_DEFINES` definieren und cmath oder math.h einschließen.  
  
 Die Datei ATLComTime.h enthält math.h, wenn das Projekt integrierter Releasemodus ist.  Wenn Sie eine oder mehrere der mathematischen Konstanten in einem Projekt verwenden, das auch ATLComTime.h enthält, müssen Sie `_USE_MATH_DEFINES` definieren, bevor Sie ATLComTime.h einschließen.  
  
## Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)