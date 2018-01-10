---
title: Compilerfehler C3420 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3420
dev_langs: C++
helpviewer_keywords: C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da0c47ccb08d1d4e9aa4c75fbce4d4fe8252a340
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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