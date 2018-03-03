---
title: 'NMAKE: Schwerwiegender Fehler U1073 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faae317df44560991a88d47ec7f123e6a8126429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE: Schwerwiegender Fehler U1073
weiß nicht, wie "Zielname" vornehmen.  
  
 Das angegebene Ziel ist nicht vorhanden, und es gibt keine auszuführenden Befehl oder Rückschlussregel anzuwendende.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Überprüfen Sie die Schreibweise der Zielname.  
  
2.  Wenn *Targetname* ist ein Pseudoziel Angabe ist als Ziel in einem anderen Beschreibungsblock.  
  
3.  Wenn *Targetname* ist ein Makroaufruf achten, dass es nicht auf eine null-Zeichenfolge erweitert.