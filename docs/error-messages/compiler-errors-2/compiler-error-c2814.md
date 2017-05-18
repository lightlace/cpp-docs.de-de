---
title: Compilerfehler C2814 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2814
dev_langs:
- C++
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: 16
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
ms.openlocfilehash: 164ad4f3862008a2352fc235df09b17e99cbfe83
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2814"></a>Compilerfehler C2814
„Member“: Ein systemeigener Typ kann innerhalb eines verwalteten oder WinRT-Typs „Typ“ nicht geschachtelt werden.  
  
## <a name="example"></a>Beispiel  
 Ein systemeigener Typ kann nicht in einem CLR- oder WinRT-Typ geschachtelt werden. Im folgenden Beispiel wird C2814 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  

