---
title: Schwerwiegender Fehler C1018 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1018
dev_langs:
- C++
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
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
ms.openlocfilehash: dc31094266e886d8bee27e2e70c9a89a7fd55731
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1018"></a>Schwerwiegender Fehler C1018
Unerwartetes #elif  
  
 Die `#elif` -Direktive befindet sich außerhalb eines `#if`-, `#ifdef`- oder `#ifndef` -Konstrukts. Verwenden Sie `#elif` nur innerhalb eines dieser Konstrukte.  
  
 Im folgenden Beispiel wird C1018 generiert:  
  
```  
// C1018.cpp  
#elif      // C1018  
#endif  
  
int main() {}  
```  
  
 Mögliche Lösung:  
  
```  
// C1018b.cpp  
#if 1  
#elif  
#endif  
  
int main() {}  
```
