---
title: Compilerfehler C3896 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3896
dev_langs:
- C++
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc60c09d6fd99e56f0261409099e56713604a76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269737"
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