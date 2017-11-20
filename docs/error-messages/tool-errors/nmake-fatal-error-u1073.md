---
title: 'NMAKE: Schwerwiegender Fehler U1073 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1073
dev_langs: C++
helpviewer_keywords: U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cc68305e5866c9765cba6bcdc1e4ac3ba17fce64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE: Schwerwiegender Fehler U1073
weiß nicht, wie "Zielname" vornehmen.  
  
 Das angegebene Ziel ist nicht vorhanden, und es gibt keine auszuführenden Befehl oder Rückschlussregel anzuwendende.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Überprüfen Sie die Schreibweise der Zielname.  
  
2.  Wenn *Targetname* ist ein Pseudoziel Angabe ist als Ziel in einem anderen Beschreibungsblock.  
  
3.  Wenn *Targetname* ist ein Makroaufruf achten, dass es nicht auf eine null-Zeichenfolge erweitert.