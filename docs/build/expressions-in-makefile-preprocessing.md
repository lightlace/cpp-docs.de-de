---
title: Ausdrücke für den Präprozessorlauf eines Makefiles
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
ms.openlocfilehash: e55be14b6623232966b1539615c4f7f40139e38f
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421847"
---
# <a name="expressions-in-makefile-preprocessing"></a>Ausdrücke für den Präprozessorlauf eines Makefiles

Die **! IF** oder **! ELSE IF** `constantexpression` ganzzahlige Konstanten (in Dezimal oder C-Schreibweise), Zeichenfolgenkonstanten oder Befehle umfasst. Verwenden Sie Klammern, um Ausdrücke zu gruppieren. Ausdrücke verwenden von C-Stil-Ganzzahlen mit Vorzeichen arithmetische; Zahlen sind in 32-Bit-zweier-Komplement Form im Bereich von – 2147483648 bis 2147483647.

Ausdrücke können Operatoren verwenden, die auf Konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Operatoren für die vorverarbeitung eines Makefiles](../build/makefile-preprocessing-operators.md)

[Ausführen eines Programms in vorverarbeitung](../build/executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>Siehe auch

[Vorverarbeitung eines Makefiles](../build/makefile-preprocessing.md)
