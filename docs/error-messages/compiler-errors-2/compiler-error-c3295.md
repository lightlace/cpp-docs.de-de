---
title: Compilerfehler C3295 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b72e4839341006d2058c21a1523b0d7567f51696
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3295"></a>Compilerfehler C3295
"#pragma Pragma" kann nur im globalen Gültigkeitsbereich oder im Namespace-Gültigkeitsbereich verwendet werden.  
  
 Einige Pragmas können nicht in einer Funktion verwendet werden.  Finden Sie unter [Pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3295 generiert:  
  
```  
// C3295.cpp  
int main() {  
   #pragma managed   // C3295  
}  
```