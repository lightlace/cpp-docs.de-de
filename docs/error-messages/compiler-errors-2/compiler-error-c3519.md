---
title: Compilerfehler C3519 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3519
dev_langs: C++
helpviewer_keywords: C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a558225717fecc216d0b2411c5f3d611256d30fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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