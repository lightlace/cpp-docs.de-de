---
title: Definitionen für die Grammatikzusammenfassung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ac3b742406f1e8be955921a9ee238f3b35d3bdf
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540433"
---
# <a name="definitions-for-the-grammar-summary"></a>Definitionen für die Grammatikzusammenfassung
Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition. Es ist keine andere Auflösung möglich. Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.  
  
Bei Nichtterminalen handelt es sich um Platzhalter in der Syntax. Die meisten sind an anderer Stelle in dieser Syntaxzusammenfassung definiert. Definitionen können rekursiv sein. Die folgenden Nichtterminale werden in definiert die [lexikalische Konventionen](../cpp/lexical-conventions.md) Teil der *C++-Sprachreferenz*:  
  
`constant`, *Konstantenausdruck*, *Bezeichner*, *Schlüsselwort*, `operator`, `punctuator`  
  
Eine optionale Komponente wird durch das tiefgestellte "opt" angegeben. Beispielsweise gibt folgende Komponente einen optionalen Ausdruck an, der in geschweiften Klammern eingeschlossen ist:  
  
**{** *Ausdruck*opt **}**  
  
## <a name="see-also"></a>Siehe auch 
 
[Grammatikzusammenfassung (C/C++)](../preprocessor/grammar-summary-c-cpp.md)