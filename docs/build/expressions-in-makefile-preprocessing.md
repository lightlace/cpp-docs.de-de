---
title: Ausdrücke in Präprozessorlauf eines Makefiles | Microsoft Docs
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
ms.openlocfilehash: 04a53e5e6fe45c2c846cae3fb9e973fe1c712107
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="expressions-in-makefile-preprocessing"></a>Ausdrücke für den Präprozessorlauf eines Makefiles
Die **! IF** oder **! ElseIf** `constantexpression` Ganzzahlkonstanten (in Dezimal oder C-Schreibweise), Zeichenfolgenkonstanten oder Befehle besteht. Verwenden Sie Klammern, um Ausdrücke zu. Ausdrücke verwenden C-Stil Ganzzahlen mit Vorzeichen arithmetische; Zahlen werden in 32-Bit zweierkomplementdarstellung im Bereich von – 2147483648 bis 2147483647.  
  
 Ausdrücke können Operatoren, die fungieren auf Konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade zu können.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [Makefile-vorverarbeitungsoperatoren](../build/makefile-preprocessing-operators.md)  
  
 [Ausführen eines Programms im Präprozessorlauf](../build/executing-a-program-in-preprocessing.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Vorverarbeitung eines Makefiles](../build/makefile-preprocessing.md)