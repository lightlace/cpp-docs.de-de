---
title: Compilerwarnung (Stufe 1) C4186 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4186
dev_langs:
- C++
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 3c3dc72d13dedf4c86aa8666a8e561e6ba74fcec
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4186"></a>Compilerwarnung (Stufe 1) C4186
\#Importattribut 'Attribut' erfordert Anzahl Argumente; ignoriert  
  
 Ein `#import` -Attribut weist die falsche Anzahl von Argumenten auf.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4186.cpp  
// compile with: /W1 /c  
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186  
```  
  
 Das `no_namespace` -Attribut akzeptiert keine Argumente. Das **rename** -Attribut erhält nur zwei Argumente.
