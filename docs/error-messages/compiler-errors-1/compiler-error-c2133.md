---
title: Compilerfehler C2133 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2133
dev_langs:
- C++
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 878f6fa4a36e7de28bfc084f7f716d50b52c363a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171912"
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