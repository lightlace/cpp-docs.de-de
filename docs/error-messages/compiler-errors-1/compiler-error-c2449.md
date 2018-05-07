---
title: Compilerfehler C2449 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2449
dev_langs:
- C++
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2ea92f79125e4e3b96f35229a487a5ab787e1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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