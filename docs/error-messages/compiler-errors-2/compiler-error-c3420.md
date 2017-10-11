---
title: Compilerfehler C3420 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3420
dev_langs:
- C++
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b0f17a1dc713940cfb18ff05af71b69f3e4df516
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3420"></a>Compilerfehler C3420
"Finalizer": Ein Finalizer kann nicht virtuell sein.  
  
 Ein Finalizer kann von seinem einschließenden Typ nur nicht virtuell aufgerufen werden. Aus diesem Grund wird die Deklaration eines Finalizers als Fehler angesehen.  
  
 Weitere Informationen finden Sie unter [Destruktoren und Finalizer wie: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3420 generiert.  
  
```  
// C3420.cpp  
// compile with: /clr /c  
ref class R {  
   virtual !R() {}   // C3420  
};  
```
