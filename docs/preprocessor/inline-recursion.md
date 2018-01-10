---
title: Inline_recursion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs: C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d749753e7eaf81284de72314f5f940fd2790962c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="inlinerecursion"></a>inline_recursion
Steuert die Inlineerweiterung von direkten oder wechselseitig rekursiven Funktionsaufrufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Pragma Steuerungsfunktionen markiert ist, als [Inline](../cpp/inline-functions-cpp.md) und [__inline](../cpp/inline-functions-cpp.md) oder Funktionen, die der Compiler automatisch unter der/Ob2-Option erweitert. Die Verwendung dieses Pragmas erfordert eine [tatsächlich](../build/reference/ob-inline-function-expansion.md) Einstellung von 1 oder 2. Standardmäßig ist `inline_recursion` deaktiviert. Dieses Pragma tritt mit dem ersten Funktionsaufruf in Kraft, nachdem das Pragma angezeigt wird, und hat keinen Einfluss auf die Definition der Funktion.  
  
 Das `inline_recursion`-Pragma legt fest, wie rekursive Funktionen erweitert werden. Wenn `inline_recursion` deaktiviert ist und eine Inlinefunktion sich selbst aufruft (entweder direkt oder indirekt), wird die Funktion nur einmal erweitert. Wenn `inline_recursion` ist, wird die Funktion mehrmals erweitert, bis er mit festlegen Wert erreicht die [Inline_depth](../preprocessor/inline-depth.md) Pragma, der Standardwert für rekursive Funktionen, die von definiert ist die `inline_depth` Pragma oder Kapazität beschränken .  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_depth](../preprocessor/inline-depth.md)   
 [/ Ob (Inlinefunktionserweiterung)](../build/reference/ob-inline-function-expansion.md)