---
title: Compilerfehler C2585 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ab812a4b6621acb28a4df636056598047f5c21e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230160"
---
# <a name="compiler-error-c2585"></a>Compilerfehler C2585
explizite Konvertierung in 'type' ist nicht eindeutig  
  
 Die typkonvertierung kann mehr als ein Ergebnis erzeugen.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Konvertieren von einem Typ Klasse oder Struktur, die basierend auf mehrfache Vererbung. Wenn der Typ mehr als einmal dieselbe Basisklasse erbt, die Konvertierungsfunktion or -Operator muss verwenden bereichsauflösung (`::`) angeben, welche die geerbten Klassen, die bei der Konvertierung verwendet.  
  
2.  Ein Konvertierungsoperator und einen Konstruktor wurden durch dieselbe Konvertierung definiert.