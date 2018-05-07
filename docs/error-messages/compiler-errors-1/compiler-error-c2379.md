---
title: Compilerfehler C2379 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2379
dev_langs:
- C++
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1016bedfa9df0e9dfacb56734ee60397108d046
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2379"></a>Compilerfehler C2379
Anzahl der formalen Parameter hat einen anderen Typ heraufgestuft  
  
 Der Typ des angegebenen Parameters ist nicht kompatibel ist, über die Standard-Erweiterungen, mit dem Typ in einer früheren Deklaration. Dies ist ein Fehler in ANSI C (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung mit Microsoft-Erweiterungen (**"/ Ze"**).  
  
 Im folgende Beispiel wird C2379 generiert:  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```