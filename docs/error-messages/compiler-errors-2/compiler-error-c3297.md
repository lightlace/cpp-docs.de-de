---
title: Compilerfehler C3297 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3297
dev_langs: C++
helpviewer_keywords: C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c2190bb4f2fe5c6195221deebe5b24097b614691
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3297"></a>Compilerfehler C3297
'Einschränkung_2': 'Einschränkung_1' kann nicht als Einschränkung verwendet werden, da 'Einschränkung_1' die Werteinschränkung aufweist.  
  
 Wertklassen sind versiegelt. Wenn eine Einschränkung eine Wertklasse ist, kann von ihr keine andere Einschränkung abgeleitet werden.  
  
 Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3297 generiert:  
  
```  
// C3297.cpp  
// compile with: /clr /c  
generic<class T, class U>  
where T : value class  
where U : T   // C3297  
public ref struct R {};  
```