---
title: Compilerfehler C2585 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25df5237d2536f6f74226121cbeceba61a454390
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2585"></a>Compilerfehler C2585
explizite Konvertierung in 'type' ist nicht eindeutig  
  
 Die typkonvertierung kann mehr als ein Ergebnis erzeugen.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Konvertieren von einem Typ Klasse oder Struktur, die basierend auf mehrfache Vererbung. Wenn der Typ mehr als einmal dieselbe Basisklasse erbt, die Konvertierungsfunktion or -Operator muss verwenden bereichsauflösung (`::`) angeben, welche die geerbten Klassen, die bei der Konvertierung verwendet.  
  
2.  Ein Konvertierungsoperator und einen Konstruktor wurden durch dieselbe Konvertierung definiert.