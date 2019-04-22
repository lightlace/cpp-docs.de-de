---
title: Definitionen für die Grammatikzusammenfassung
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
ms.openlocfilehash: 6e8671ba0d68b13f68db0f2b08dab4fe98f917e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024954"
---
# <a name="definitions-for-the-grammar-summary"></a>Definitionen für die Grammatikzusammenfassung

Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition. Es ist keine andere Auflösung möglich. Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.

Bei Nichtterminalen handelt es sich um Platzhalter in der Syntax. Die meisten sind an anderer Stelle in dieser Syntaxzusammenfassung definiert. Definitionen können rekursiv sein. Die folgenden Nichtterminale werden in definiert die [lexikalische Konventionen](../cpp/lexical-conventions.md) Teil der *C++-Sprachreferenz*:

`constant`, *constant-expression*, *identifier*, *keyword*, `operator`, `punctuator`

Eine optionale Komponente wird durch das tiefgestellte <sub>opt</sub> angegeben. Beispielsweise gibt folgende Komponente einen optionalen Ausdruck an, der in geschweiften Klammern eingeschlossen ist:

**{** *expression*<sub>opt</sub> **}**

## <a name="see-also"></a>Siehe auch

[Grammatikzusammenfassung (C/C++)](../preprocessor/grammar-summary-c-cpp.md)