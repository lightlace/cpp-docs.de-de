---
title: Mathematischer Fehler M6201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6a15e841cfc8daf1abdafc9997698807e7356af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332064"
---
# <a name="math-error-m6201"></a>Mathematischer Fehler M6201
'Funktion': _DOMAIN-Fehler  
  
 Ein Argument an die angegebene Funktion wurde außerhalb der Domäne der zulässigen Eingabewerte für diese Funktion.  
  
## <a name="example"></a>Beispiel  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 Dieser Fehler-Ruft die `_matherr` -Funktion mit den Namen der Funktion, die Argumente und den Fehlertyp. Sie können Umschreiben der `_matherr` Funktion, um die Behandlung bestimmter Gleitkommaoperationen zur Laufzeit anzupassen.