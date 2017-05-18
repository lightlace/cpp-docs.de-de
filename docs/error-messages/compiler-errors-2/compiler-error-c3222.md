---
title: Compilerfehler C3222 | Microsoft-Dokumentation
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: bd1058f4e33bc70c9021bfb1ceff78af58d09552
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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

