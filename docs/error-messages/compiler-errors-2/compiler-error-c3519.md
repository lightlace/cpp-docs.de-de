---
title: Compilerfehler C3519 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3519
dev_langs:
- C++
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 740fef32484164e7439335686adce0a4aa8027f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257197"
---
# <a name="compiler-error-c3519"></a>Compilerfehler C3519
'Invalid_param': Ungültiger Parameter für Embedded_idl-Attribut  
  
 Ein Parameter wurde übergeben, um die `embedded_idl` Attribut des [#import](../../preprocessor/hash-import-directive-cpp.md), aber der Compiler hat den Parameter nicht erkannt.  
  
 Der einzige Parameter, die für zulässig sind `embedded_idl` sind `emitidl` und `no_emitidl`.  
  
 Im folgende Beispiel wird C3519 generiert:  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```