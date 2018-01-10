---
title: Compiler-Fehler C2732 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2732
dev_langs: C++
helpviewer_keywords: C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aeecaab0fd9faaa6a876aa57781160df6bb26502
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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