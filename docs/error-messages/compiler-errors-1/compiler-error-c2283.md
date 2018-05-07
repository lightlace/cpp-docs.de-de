---
title: Compilerfehler C2283 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2283
dev_langs:
- C++
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb602d1fa330876820cc7e1fe75fcfe7b736b81e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2283"></a>Compilerfehler C2283
"Bezeichner": Ein reiner Spezifizierer oder ein abstrakter Überschreibungsspezifizierer ist für "Struktur" (unbenannt) nicht zulässig.  
  
 Eine Memberfunktion einer unbenannten Klasse oder Struktur wird mit einem reinen Spezifizierer deklariert, was nicht zulässig ist.  
  
 Im folgenden Beispiel wird C2283 generiert:  
  
```  
// C2283.cpp  
// compile with: /c  
struct {  
   virtual void func() = 0;   // C2283  
};  
struct T {  
   virtual void func() = 0;   // OK  
};  
```