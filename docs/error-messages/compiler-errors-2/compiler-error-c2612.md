---
title: Compiler-Fehler C2612 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2612
dev_langs:
- C++
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88053cde81e7eea8bc9e9280cf235d5eccc6704
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226947"
---
# <a name="compiler-error-c2612"></a>Compiler-Fehler C2612 generiert
nachfolgende 'Char' in der Initialisiererliste Base bzw. dieses Element nicht zulässig  
  
 Ein Zeichen, die nach der letzten Basis oder ein Member in einer Initialisiererliste angezeigt werden.  
  
 Im folgende Beispiel wird C2612 generiert:  
  
```  
// C2612.cpp  
class A {  
public:  
   int i;  
   A( int ia ) : i( ia ) + {};   // C2612  
};  
```