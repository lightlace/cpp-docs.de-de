---
title: Compilerfehler C2480 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 06f6c536d5756a19e28df7060373512e3e883a41
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
