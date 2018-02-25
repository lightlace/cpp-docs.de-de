---
title: "Definitionen für die Zusammenfassung der Grammatik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 755533d59b9b893da4a657db6da2ea80f13138b5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="definitions-for-the-grammar-summary"></a>Definitionen für die Grammatikzusammenfassung
Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition. Es ist keine andere Auflösung möglich. Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.  
  
Bei Nichtterminalen handelt es sich um Platzhalter in der Syntax. Die meisten sind an anderer Stelle in dieser Syntaxzusammenfassung definiert. Definitionen können rekursiv sein. Die folgenden Nichtterminale werden definiert, der [lexikalische Konventionen](../cpp/lexical-conventions.md) Teil der *C++-Sprachreferenz*:  
  
`constant`, *constant-expression*, *identifier*, *keyword*, `operator`, `punctuator`  
  
Eine optionale Komponente wird durch das tiefgestellte "opt" angegeben. Beispielsweise gibt folgende Komponente einen optionalen Ausdruck an, der in geschweiften Klammern eingeschlossen ist:  
  
**{** *expression*opt **}**  
  
## <a name="see-also"></a>Siehe auch  
[Grammatikzusammenfassung (C/C++)](../preprocessor/grammar-summary-c-cpp.md)