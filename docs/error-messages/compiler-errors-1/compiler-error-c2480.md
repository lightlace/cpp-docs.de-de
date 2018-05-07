---
title: Compilerfehler C2480 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987cefa42b3f3f8d9588e446ca181c0b7cd48f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2480"></a>Compilerfehler C2480
'Bezeichner': 'Thread' ist nur für statische Datenelemente gültig  
  
 Sie können keine der `thread` -Attribut mit einer automatischen Variablen, die nicht statischen Datenmember, die Funktionsparameter oder in Funktionsdeklarationen oder-Definitionen.  
  
 Verwenden der `thread` Attribut für globale Variablen, statische Datenmember und nur lokale statische Variablen.  
  
 Im folgende Beispiel wird C2480 generiert:  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```