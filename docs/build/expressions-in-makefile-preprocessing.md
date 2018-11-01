---
title: Ausdrücke für den Präprozessorlauf eines Makefiles
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
ms.openlocfilehash: 8d7b8cd489eabf239cbc993181142ca84431cd82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594869"
---
# <a name="expressions-in-makefile-preprocessing"></a>Ausdrücke für den Präprozessorlauf eines Makefiles

Die **! IF** oder **! ELSE IF** `constantexpression` ganzzahlige Konstanten (in Dezimal oder C-Schreibweise), Zeichenfolgenkonstanten oder Befehle umfasst. Verwenden Sie Klammern, um Ausdrücke zu gruppieren. Ausdrücke verwenden von C-Stil-Ganzzahlen mit Vorzeichen arithmetische; Zahlen sind in 32-Bit-zweier-Komplement Form im Bereich von – 2147483648 bis 2147483647.

Ausdrücke können Operatoren verwenden, die auf Konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Operatoren für die vorverarbeitung eines Makefiles](../build/makefile-preprocessing-operators.md)

[Ausführen eines Programms in vorverarbeitung](../build/executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>Siehe auch

[Vorverarbeitung eines Makefiles](../build/makefile-preprocessing.md)