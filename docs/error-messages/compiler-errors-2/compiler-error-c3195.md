---
title: Compiler-Fehler C3195 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 9
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
ms.openlocfilehash: ae4ca677380fd9b4052ecb1f41ba44899ed87768
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3195"></a>Compiler-Fehler C3195 generiert
"operator" : ist reserviert und kann nicht als Member einer Verweisklasse oder eines Werttyps verwendet werden. CLR- oder WinRT-Operatoren müssen mit dem Schlüsselwort "operator" definiert werden.  
  
Der Compiler hat eine Operatordefinition gefunden, in der die Managed Extensions for C++-Syntax verwendet wird. Sie müssen die C++-Syntax für Operatoren verwenden.  
  
Im folgenden Beispiel wird C3195 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```
