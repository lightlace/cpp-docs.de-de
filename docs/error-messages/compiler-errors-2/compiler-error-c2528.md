---
title: Compilerfehler C2528 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2528
dev_langs:
- C++
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 953e3b0c7af59b3358ad2c0b0743cc8d214bf91e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2528"></a>Compilerfehler C2528
'Name': Zeiger auf Verweis ist nicht zulässig  
  
 Einen Zeiger auf einen Verweis nicht deklariert werden. Die Variable vor dem Deklarieren eines Zeigers, dereferenziert werden.  
  
 Im folgende Beispiel wird C2528 generiert:  
  
```  
// C2528.cpp  
int i;  
int &ir = i;  
int & (*irptr) = ir;    // C2528  
```