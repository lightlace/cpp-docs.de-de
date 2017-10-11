---
title: Compilerfehler C2379 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2379
dev_langs:
- C++
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 69be5132451269f7eba9c2e9186a9c25d4629ae7
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
