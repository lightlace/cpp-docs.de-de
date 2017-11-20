---
title: Compilerfehler C3298 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3298
dev_langs: C++
helpviewer_keywords: C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a21b2d28120cb5e1c936b632d67ff28bb6568210
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3298"></a>Compilerfehler C3298
"constraint_1": "constraint_2" kann nicht als Einschränkung verwendet werden, da "constraint_2" die ref-Einschränkung und "constraint_1" die Werteinschränkung aufweist.  
  
 Sie können keine sich gegenseitig ausschließende Eigenschaften für eine Einschränkung angeben. Beispielsweise kann ein generischer Typparameter nicht gleichzeitig auf einen Werttyp und einen Referenztyp eingeschränkt werden.  
  
 Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3298 generiert:  
  
```  
// C3298.cpp  
// compile with: /clr /c   
generic<class T, class U>  
where T : ref class  
where U : T, value class   // C3298  
public ref struct R {};  
```