---
title: Compilerfehler C3755 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3602f78659e58de9dc394f6887901c46de8de60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267108"
---
# <a name="compiler-error-c3755"></a>Compilerfehler C3755
'Delegat': ein Delegat ist möglicherweise nicht definiert  
  
 Ein [Delegate (Komponentenerweiterungen für C++)](../../windows/delegate-cpp-component-extensions.md) deklariert, aber nicht definiert werden können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3755 generiert.  
  
```  
// C3755.cpp  
// compile with: /clr /c  
delegate void MyDel() {};   // C3755  
```  
  
## <a name="example"></a>Beispiel  
 C3755 kann auch auftreten, wenn Sie versuchen, eine Delegatvorlage für zu erstellen. Im folgenden Beispiel wird C3755 generiert.  
  
```  
// C3755_b.cpp  
// compile with: /clr /c  
ref struct R {  
   template<class T>  
   delegate void D(int) {}   // C3755  
};  
```