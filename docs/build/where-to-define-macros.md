---
title: Definieren von Makros
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: 130863f8c5640a0c4915734732d93fc00d3d6479
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656247"
---
# <a name="where-to-define-macros"></a>Definieren von Makros

Definieren von Makros in einer Befehlszeile, Befehlsdatei, Makefile oder der Datei Tools.ini.

In einem Makefile oder der Datei Tools.ini jede Makrodefinition muss in einer separaten Zeile angezeigt werden und darf nicht mit einem Leerzeichen oder Tabstopp beginnen. Leerzeichen oder Tabstopps, um das Gleichheitszeichen werden ignoriert. Alle [Zeichenfolge Zeichen](../build/defining-an-nmake-macro.md) sind Literale, einschließlich der Sie umgebenden Anführungszeichen und Leerzeichen.

In einer Befehlszeile oder eine Befehlsdatei Leerzeichen und Tabulatoren trennen die Argumente und können nicht das Gleichheitszeichen umschließen. Wenn `string` eingebettete Leerzeichen oder Tabstopps, schließen Sie entweder die Zeichenfolge oder das gesamte Makro in doppelte Anführungszeichen ("").

## <a name="see-also"></a>Siehe auch

[Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)