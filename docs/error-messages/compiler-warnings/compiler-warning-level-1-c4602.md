---
title: Compilerwarnung (Stufe 1) C4602 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4602
dev_langs:
- C++
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b47b7c0cb0271aa6ab463fb5505af348bc5e75af
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4602"></a>Compilerwarnung (Stufe 1) C4602
\#Pragma-Pop_macro: 'Makroname' kein vorherigen #pragma Push_macro für diesen Bezeichner  
  
 Bei Verwendung von [Pop_macro](../../preprocessor/pop-macro.md) für ein bestimmtes Makro verwenden, Sie müssen zuerst vergangen Makronamen an [Push_macro](../../preprocessor/push-macro.md). Im folgenden Beispiel wird C4602 generiert:  
  
```  
// C4602.cpp  
// compile with: /W1  
int main()  
{  
   #pragma pop_macro("x")   // C4602 x is not on the stack  
}  
```
