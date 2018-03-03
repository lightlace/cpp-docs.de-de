---
title: Compilerwarnung (Stufe 1) C4624 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4624
dev_langs:
- C++
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a3acf93e1609b6a53f6654afb83a51bad49da84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4624"></a>Compilerwarnung (Stufe 1) C4624
'derived class': Der Destruktor wurde impliziert als gelöscht definiert, da ein Basisklassen-Destruktor nicht zugreifbar ist oder gelöscht wurde.  
  
 Ein Destruktor stand nicht für den Zugriff zur Verfügung oder wurde in einer Basisklasse gelöscht. Daher wurde er nicht für eine abgeleitete Klasse generiert. Jeder Versuch, ein Objekt dieses Typs auf dem Stapel zu erstellen, verursacht einen Compilerfehler.  
  
 Im folgenden Beispiel wird C4624 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```