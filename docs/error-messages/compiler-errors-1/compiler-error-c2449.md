---
title: Compilerfehler C2449 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2449
dev_langs:
- C++
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3a32347d4c03f191e2984e99b5098c2fe80bd08d
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2449"></a>Compilerfehler C2449
gefunden ' {' im Dateigültigkeitsbereich (fehlende Funktionsheader?)  
  
 Eine öffnende geschweifte Klammer tritt im Dateigültigkeitsbereich.  
  
 Dieser Fehler kann durch ein Semikolon zwischen einem Funktionsheader und die öffnende geschweifte Klammer der Funktionsdefinition verursacht werden.  
  
 Im folgenden Beispiel wird C2499 generiert:  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```
