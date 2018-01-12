---
title: Mathematischer Fehler M6201 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6201
dev_langs: C++
helpviewer_keywords: M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17de7fab7b41a5a8acc2fed2f3c8185f66aadd9c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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