---
title: Ausdrücke im Präprozessorlauf eines Makefiles | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1070eb01802bd4b39f62ae24519ad6dabca7eb90
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719004"
---
# <a name="expressions-in-makefile-preprocessing"></a>Ausdrücke für den Präprozessorlauf eines Makefiles

Die **! IF** oder **! ELSE IF** `constantexpression` ganzzahlige Konstanten (in Dezimal oder C-Schreibweise), Zeichenfolgenkonstanten oder Befehle umfasst. Verwenden Sie Klammern, um Ausdrücke zu gruppieren. Ausdrücke verwenden von C-Stil-Ganzzahlen mit Vorzeichen arithmetische; Zahlen sind in 32-Bit-zweier-Komplement Form im Bereich von – 2147483648 bis 2147483647.

Ausdrücke können Operatoren verwenden, die auf Konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Operatoren für die vorverarbeitung eines Makefiles](../build/makefile-preprocessing-operators.md)

[Ausführen eines Programms in vorverarbeitung](../build/executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>Siehe auch

[Vorverarbeitung eines Makefiles](../build/makefile-preprocessing.md)