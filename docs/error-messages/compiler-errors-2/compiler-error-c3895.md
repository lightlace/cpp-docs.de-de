---
title: Compilerfehler C3895 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3895
dev_langs:
- C++
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9343a7d6f85864de809aea5d83965e65e9f5b70b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3895"></a>Compilerfehler C3895
'Var': Typ-Datenmember können nicht 'volatile' sein  
  
 Bestimmte Arten von Datenelementen, z. B. [literal](../../windows/literal-cpp-component-extensions.md) oder [Initonly](../../dotnet/initonly-cpp-cli.md), nicht mit [volatile](../../cpp/volatile-cpp.md).  
  
 Im folgende Beispiel wird C3895 generiert:  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```