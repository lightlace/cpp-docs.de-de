---
title: Definitionen für die Grammatikzusammenfassung
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
ms.openlocfilehash: 93cf6ffc5daf53a106c9f15a2289e2b52739d72f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222415"
---
# <a name="definitions-for-the-grammar-summary"></a>Definitionen für die Grammatikzusammenfassung

Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition. Es ist keine andere Auflösung möglich. Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.

Bei Nichtterminalen handelt es sich um Platzhalter in der Syntax. Die meisten sind an anderer Stelle in dieser Syntaxzusammenfassung definiert. Definitionen können rekursiv sein. Die folgenden nicht Terminals sind im Abschnitt " [lexikalische Konventionen](../cpp/lexical-conventions.md) " der  *C++ Sprachreferenz*definiert:

*Constant*, *Constant-Expression*, *Identifier*, *Schlüsselwort*, *Operator*, *Satzzeichen*

Eine optionale Komponente wird durch das tiefgestellte <sub>opt</sub> angegeben. Beispielsweise gibt folgende Komponente einen optionalen Ausdruck an, der in geschweiften Klammern eingeschlossen ist:

**{** *expression*<sub>opt</sub> **}**

## <a name="see-also"></a>Siehe auch

[Grammatik Zusammenfassung (CC++/)](../preprocessor/grammar-summary-c-cpp.md)
