---
title: Compilerfehler C2133 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2133
dev_langs:
- C++
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c04452ec947adefa6b30928dc75de4edffc361fc
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2133"></a>Compilerfehler C2133
'Bezeichner': Unbekannte Größe  
  
 Ein Array ohne Größenangabe wird als ein Mitglied aus einer Klasse, Struktur, Union oder Enumeration deklariert. Die Option/Za (ANSI C) lässt sich nicht auf Memberarrays aus.  
  
 Im folgende Beispiel wird C2133 generiert:  
  
```  
// C2133.cpp  
// compile with: /Za  
struct X {  
   int a[0];   // C2133 unsized array  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C2133b.cpp  
// compile with: /c  
struct X {  
   int a[0];   // no /Za  
};  
```