---
title: Compilerfehler C2801 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2801
dev_langs:
- C++
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f68b3f575fcb8b909f58ac2ffbcaca26580279da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237090"
---
# <a name="compiler-error-c2801"></a>Compilerfehler C2801
'Operator Operator' muss ein nicht statisches Member sein.  
  
 Die folgenden Operatoren können nur als nicht statische Member überladen werden:  
  
-   Zuweisung `=`  
  
-   Klassenmemberzugriff `->`  
  
-   Indizierung `[]`  
  
-   Funktionsaufruf `()`  
  
 Mögliche Ursachen für C2801:  
  
-   Überladener Operator ist eine Klasse, Struktur oder union-Member.  
  
-   Überladener Operator deklariert ist `static`.  
  
-   Im folgende Beispiel wird C2801 generiert:  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```