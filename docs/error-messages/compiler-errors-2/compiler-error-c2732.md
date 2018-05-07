---
title: Compiler-Fehler C2732 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2732
dev_langs:
- C++
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef2faf21eb6f0c73d02ea32c7d4ed53f86eec3de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2732"></a>Compiler-Fehler C2732 generiert
Bindungsangaben widersprechen vorheriger Angabe für 'function'  
  
 Die Funktion wurde bereits mit einem anderen Bindungsspezifizierer deklariert.  
  
 Dieser Fehler kann durch das Einbeziehen von Dateien mit unterschiedlichen Bindungsspezifizierern verursacht werden.  
  
 Um diesen Fehler zu beheben, ändern Sie die `extern`-Anweisungen, sodass die Bindungen übereinstimmen. Brechen Sie im Besonderen `#include`-Direktive nicht in `extern "C"`-Blöcke um.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2732 generiert:  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```