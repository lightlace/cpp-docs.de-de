---
title: Compilerfehler C3222 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: edc882f340e92defeaa2db92d868680f7791e7b9
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3222"></a>Compilerfehler C3222
'Parameter': Für Memberfunktionen eines verwalteten oder WinRT-Typs oder generische Funktionen können keine Standardargumente deklariert werden.  
  
Es ist nicht zulässig, einen Methodenparameter mit einem Standardargument zu deklarieren. Eine überladene Form der Methode ist eine Möglichkeit, dieses Problem zu umgehen. Das heißt, dass Sie eine Methode mit demselben Namen ohne Parameter definieren und anschließend die Variable im Methodentext initialisieren.  
  
Im folgenden Beispiel wird C3222 generiert:  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  

