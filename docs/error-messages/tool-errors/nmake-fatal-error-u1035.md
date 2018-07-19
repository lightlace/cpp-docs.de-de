---
title: 'NMAKE: Schwerwiegender Fehler U1035 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bb32f815345b933ad6a65a0c8c1ec8ad59cbe81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322795"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE: Schwerwiegender Fehler U1035
Syntaxfehler: erwartet ':' oder '=' Trennzeichen  
  
 Entweder einen Doppelpunkt (**:**) oder ein Gleichheitszeichen (**=**) wurde erwartet.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Ein Ziel folgte kein Doppelpunkt.  
  
2.  Einem Doppelpunkt und ohne Leerzeichen (z. B. a:) folgt ein Ziel mit einem Buchstaben. NMAKE, die sie als eine Laufwerksangabe interpretiert.  
  
3.  Eine Rückschlussregel folgte kein Doppelpunkt.  
  
4.  Eine Makrodefinition wurde nicht von einem Gleichheitszeichen gefolgt werden.  
  
5.  Ein Zeichen gefolgt von einem umgekehrten Schrägstrich (**\\**), um einen Befehl aus, um eine neue Zeile zu fortfahren verwendet wurde.  
  
6.  Eine Zeichenfolge angezeigt, die keine NMAKE Syntaxregel folgen.  
  
7.  Makefile wurde von einem Textverarbeitungsprogramm formatiert.