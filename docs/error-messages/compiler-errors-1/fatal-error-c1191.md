---
title: Schwerwiegender Fehler C1191 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1191
dev_langs:
- C++
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf700db0e415fd7886cd8ba845f06a2d8f6c3249
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1191"></a>Schwerwiegender Fehler C1191
"Dll" kann nur im globalen Gültigkeitsbereich importiert werden  
  
 Die Anweisung in "mscorlib.dll" in einem Programm zu importieren, / CLR-Programmierung verwendet, darf nicht in einem Namespace oder einer Funktion, aber Sie müssen im globalen Gültigkeitsbereich angezeigt.  
  
 Im folgenden Beispiel wird C1191 generiert:  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```