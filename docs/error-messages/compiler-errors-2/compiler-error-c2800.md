---
title: Compilerfehler C2800 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2800
dev_langs:
- C++
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dd9723513042ae7ef6d63914f5abecd63192e37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235596"
---
# <a name="compiler-error-c2800"></a>Compilerfehler C2800
'Operator Operator' kann nicht überladen werden  
  
 Die folgenden Operatoren können nicht überladen werden: Klasse Memberzugriff (`.`), Zeiger auf Member (`.*`), Bereich Auflösung (`::`), bedingte Ausdruck (`? :`), und `sizeof`.  
  
 Im folgenden Beispiel wird C2800 generiert:  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```