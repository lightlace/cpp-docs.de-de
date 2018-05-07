---
title: 'NMAKE: Schwerwiegender Fehler U1073 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dde9ca2f4a15edf6599dcc31b39d9411645f2a6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE: Schwerwiegender Fehler U1073
weiß nicht, wie "Zielname" vornehmen.  
  
 Das angegebene Ziel ist nicht vorhanden, und es gibt keine auszuführenden Befehl oder Rückschlussregel anzuwendende.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Überprüfen Sie die Schreibweise der Zielname.  
  
2.  Wenn *Targetname* ist ein Pseudoziel Angabe ist als Ziel in einem anderen Beschreibungsblock.  
  
3.  Wenn *Targetname* ist ein Makroaufruf achten, dass es nicht auf eine null-Zeichenfolge erweitert.