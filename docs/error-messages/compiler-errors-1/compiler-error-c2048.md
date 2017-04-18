---
title: Compilerfehler C2048 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2048
dev_langs:
- C++
helpviewer_keywords:
- C2048
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
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
ms.openlocfilehash: 2bf1c0b77fcc13d342e6a7b01cd48f3944753b4a
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2048"></a>Compilerfehler C2048
Mehrere Vorkommen von default  
  
 Eine `switch` -Anweisung enthält mehrere `default` -Bezeichnungen. Löschen Sie eine der `default` Bezeichnungen, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C2048 generiert:  
  
```  
// C2048.cpp  
int main() {  
   int a = 1;  
   switch (a) {  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
      default:   // C2048  
         a = 3;  
   }  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2048b.cpp  
int main() {  
   int a = 1;  
   switch (a) {  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```
