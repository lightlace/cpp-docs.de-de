---
title: Compiler-Fehler C3084 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3084
dev_langs:
- C++
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 7fb05bf2ebf23446de0552fd06092cb75541d49e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3084"></a>Compilerfehler C3084
"Funktion": ein Finalizer/Destruktor kann nicht "Schlüsselwort" sein.  
  
 Ein Finalizer oder Destruktor wurde falsch deklariert.  
  
 Beispielsweise sollte ein Destruktor nicht als versiegelt gekennzeichnet werden.  Abgeleitete Typen können nicht auf den Destruktor zugreifen.  Weitere Informationen finden Sie unter [Explizite Overrides](../../windows/explicit-overrides-cpp-component-extensions.md) und [Destruktoren und Finalizer unter Gewusst wie: definieren und Verarbeiten von Klassen und Strukturen (C++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3084 generiert.  
  
```  
// C3084.cpp  
// compile with: /clr /c  
ref struct R {  
protected:  
   !R() sealed;   // C3084  
   !R() abstract;   // C3084  
   !R();  
};  
```
