---
title: Compilerfehler C2909 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2909
dev_langs:
- C++
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
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
ms.openlocfilehash: 89bf4cde99d9629a0057106ff14f5641f81dbdde
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2909"></a>Compilerfehler C2909
'bezeichner': Für die explizite Instanziierung einer Funktionsvorlage ist ein Rückgabetyp erforderlich.  
  
 Eine explizite Instanziierung einer Funktionsvorlage erfordert die explizite Angabe ihres Rückgabetyps. Die implizite Angabe von Rückgabetypen ist nicht möglich.  
  
 Im folgenden Beispiel wird C2909 generiert:  
  
```  
// C2909.cpp  
// compile with: /c  
template<class T> int f(T);  
template f<int>(int);         // C2909  
template int f<int>(int);   // OK  
```
