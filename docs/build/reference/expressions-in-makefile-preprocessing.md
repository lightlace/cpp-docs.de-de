---
title: Ausdrücke für den Präprozessorlauf eines Makefiles
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
ms.openlocfilehash: 3d668492441eb2fc09be378dbebfe2b18c1b5753
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271306"
---
# <a name="expressions-in-makefile-preprocessing"></a>Ausdrücke für den Präprozessorlauf eines Makefiles

Die **! IF** oder **! ELSE IF** `constantexpression` ganzzahlige Konstanten (in Dezimal oder C-Schreibweise), Zeichenfolgenkonstanten oder Befehle umfasst. Verwenden Sie Klammern, um Ausdrücke zu gruppieren. Ausdrücke verwenden von C-Stil-Ganzzahlen mit Vorzeichen arithmetische; Zahlen sind in 32-Bit-zweier-Komplement Form im Bereich von – 2147483648 bis 2147483647.

Ausdrücke können Operatoren verwenden, die auf Konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Operatoren für die vorverarbeitung eines Makefiles](makefile-preprocessing-operators.md)

[Ausführen eines Programms in vorverarbeitung](executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>Siehe auch

[Vorverarbeitung eines Makefiles](makefile-preprocessing.md)
