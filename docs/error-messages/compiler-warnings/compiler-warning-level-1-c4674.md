---
title: Compiler (Stufe 1) C4674 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4674
dev_langs:
- C++
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: 9
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
ms.openlocfilehash: ca99a22e6f91f44af58a1421d59151597017cddb
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4674"></a>Compilerwarnung (Stufe 1) C4674
"Methode" sollte als "static" deklariert werden und nur einen Parameter haben  
  
Die Signatur eines Konvertierungsoperators war falsch. Die Methode wird nicht als benutzerdefinierte Konvertierung angesehen. Weitere Informationen zum Definieren von Operatoren finden Sie unter [User-Defined Operators (C++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md) und [User-Defined Conversions (C++ / CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4674 generiert.  
  
```  
// C4674.cpp  
// compile with: /clr /WX /W1 /LD  
ref class G {  
   int op_Implicit(int i) {   // C4674  
      return 0;  
   }  
};  
```  

