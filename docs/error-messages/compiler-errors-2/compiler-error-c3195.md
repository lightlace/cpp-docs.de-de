---
title: Compiler-Fehler C3195 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3195
dev_langs: C++
helpviewer_keywords: C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6e95ce1592c98fae59869e0153ee27c0f727397
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3195"></a>Compiler-Fehler C3195 generiert
"operator" : ist reserviert und kann nicht als Member einer Verweisklasse oder eines Werttyps verwendet werden. CLR- oder WinRT-Operatoren müssen mit dem Schlüsselwort "operator" definiert werden.  
  
Der Compiler hat eine Operatordefinition gefunden, in der die Managed Extensions for C++-Syntax verwendet wird. Sie müssen für Operatoren die C++-Syntax verwenden.  
  
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