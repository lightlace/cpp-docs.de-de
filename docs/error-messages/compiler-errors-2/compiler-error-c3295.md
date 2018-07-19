---
title: Compilerfehler C3295 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25fd1a04e0be46943b4fd183b470b369f810a0d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253956"
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