---
title: Vorrang bei Makrodefinitionen
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 8829b3cdbc7b2324ef3d118f8ca45dd2a1621e7e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619078"
---
# <a name="precedence-in-macro-definitions"></a>Vorrang bei Makrodefinitionen

Wenn ein Makro mehrere Definitionen verfügt, verwendet NMAKE die höchsten Rangfolge-Definition. Die folgende Liste zeigt die Reihenfolge der Rangfolge, vom höchsten zum niedrigsten Wert:

1. Ein Makro definiert, in der Befehlszeile

1. Ein Makro definiert, die in einem Makefile oder include-Datei

1. Ein geerbter Umgebungsvariablen-Makro

1. Ein Makro definiert, in der Datei Tools.ini

1. Ein vordefiniertes Makro, z. B. [CC](../build/command-macros-and-options-macros.md) und [AS](../build/command-macros-and-options-macros.md)

Verwenden Sie/e Makros von Umgebungsvariablen für Makefilemakros mit demselben Namen überschreiben geerbte verursachen. Verwendung **! UNDEF** an eine Befehlszeile außer Kraft zu setzen.

## <a name="see-also"></a>Siehe auch

[Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)