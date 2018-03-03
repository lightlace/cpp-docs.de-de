---
title: Compilerfehler C3909 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3909
dev_langs:
- C++
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d22341deb7ef6acd8a93ea234be7231a2c59b96e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3909"></a>Compilerfehler C3909
aWinRT oder verwaltete Ereignisdeklaration muss in einem WinRT- oder verwalteten Typ auftreten.  
  
 Ein Windows-Runtime-Ereignis oder verwaltetes Ereignis wurde in einem systemeigenen Typ deklariert. Deklarieren Sie zum Beheben dieses Fehlers Ereignisse in Windows-Runtime-Typen oder verwalteten Typen.  
  
 Weitere Informationen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3909 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```