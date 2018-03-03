---
title: Compilerwarnung (Stufe 4) C4626 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4626
dev_langs:
- C++
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d7f0206125a9f210db860cee95fc47c49413a89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4626"></a>Compilerwarnung (Stufe 4) C4626
„Abgeleitete Klasse“: Der Zuweisungsoperator wurde implizit als gelöscht definiert, da auf einen Basisklassen-Zuweisungsoperator nicht zugegriffen werden kann oder dieser gelöscht wurde.  
  
 Ein Zuweisungsoperator wurde gelöscht, oder es kann nicht auf diesen in einer Basisklasse zugegriffen werden. Daher wurde er nicht für eine abgeleitete Klasse generiert. Bei jedem Versuch, Objekte dieses Typs zuzuweisen, wird ein Compilerfehler generiert.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Im folgenden Beispiel wird C4626 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C4626  
// compile with: /W4  
#pragma warning(default : 4626)  
class B  
{  
// public:  
   B& operator = (const B&)  
   {  
      return *this;  
   }  
};  
  
class D : public B  
{  
  
}; // C4626 - to fix, make B's copy constructor public  
  
int main()  
{  
   D m;  
   D n;  
   // m = n;   // this line will cause an error  
}  
```