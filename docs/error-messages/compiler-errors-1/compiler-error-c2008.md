---
title: Compilerfehler Fehler C2008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88dcbc88b50ee46b406d383ec36e1fed167eca05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2008"></a>Compilerfehler Fehler C2008
"Zeichen": unerwartetes Zeichen in Makrodefinition  
  
 Das Zeichen wird unmittelbar nach dem Makronamen angezeigt. Um den Fehler zu beheben, muss ein Leerzeichen nach dem Makronamen vorhanden sein.  
  
 Im folgende Beispiel wird C2008 generiert:  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 Mögliche Lösung:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```