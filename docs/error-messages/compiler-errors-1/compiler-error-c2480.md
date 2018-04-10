---
title: Compilerfehler C2480 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8b350c8f9098c56c503041614a4e68c780af5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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