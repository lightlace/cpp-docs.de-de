---
title: Compilerwarnung (Stufe 1) C4624 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4624
dev_langs:
- C++
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d11bc5c8b5034fa305a22ba893c62faff18cc38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281033"
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