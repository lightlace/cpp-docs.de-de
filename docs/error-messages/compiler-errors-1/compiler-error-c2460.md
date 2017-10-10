---
title: Compilerfehler C2460 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 00e4015a0dae5054973ba72bb0e4f89c7443ae03
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2460"></a>Compilerfehler C2460
'Bezeichner1': verwendet "Bezeichner2", die definiert wird  
  
 Eine Klasse oder Struktur (`identifier2`) wird als Mitglied von sich selbst deklariert (`identifier1`). Rekursive Definitionen von Klassen und Strukturen sind nicht zulässig.  
  
 Im folgende Beispiel wird C2460 generiert:  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 Verwenden Sie stattdessen einen Zeigerverweis in der Klasse.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```
