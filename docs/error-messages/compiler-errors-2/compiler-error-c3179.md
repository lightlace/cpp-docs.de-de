---
title: Compilerfehler Fehler C3179 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3179
dev_langs:
- C++
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6234eceb35bda37a3616113d3010fe09cb669c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246029"
---
# <a name="compiler-error-c3179"></a>Compilerfehler Fehler C3179
Ein unbenannter verwalteter oder WinRT-Typ ist nicht zulässig.  
  
Alle CLR- und WinRT-Klassen und -Strukturen müssen Namen haben.  
  
Im folgenden Beispiel wird C3179 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3179a.cpp  
// compile with: /clr /c  
typedef value struct { // C3179  
// try the following line instead  
// typedef value struct MyStruct {  
   int i;  
} V;  
```  
