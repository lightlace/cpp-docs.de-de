---
title: Compilerfehler C3896 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3896
dev_langs:
- C++
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4aa98283d3c83f64ba461bf818a88599f97434e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3896"></a>Compilerfehler C3896
'Member': Fehlerhafte Initialisierung: diesem literal-Datenmember kann nur mit "Nullptr" initialisiert werden  
  
 Ein [literal](../../windows/literal-cpp-component-extensions.md) Datenmember wurde nicht ordnungsgemäß initialisiert.  Finden Sie unter [Nullptr](../../windows/nullptr-cpp-component-extensions.md) für Weitere Informationen.  
  
 Im folgende Beispiel wird C3896 generiert:  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```