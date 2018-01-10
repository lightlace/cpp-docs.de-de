---
title: Compiler-Fehler C2733 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2733
dev_langs: C++
helpviewer_keywords: C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fb0c21850d93a39047bacfe38592e381e9fb5918
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2733"></a>Compiler-Fehler C2733 generiert
zweite C-Bindung für überladene Funktion 'Funktion' nicht zulässig  
  
 Mehr als einer überladenen Funktion mit C-Bindung deklariert wird. Wenn Sie C-Bindung verwenden, kann jeweils nur eine Art einer angegebenen Funktion externe sein. Da überladene Funktionen denselben nicht ergänzten Namen haben, können sie mit C-Programmen verwendet werden.  
  
 Im folgende Beispiel wird C2733 generiert:  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```