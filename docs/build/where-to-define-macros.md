---
title: Definieren von Makros
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: 5a5e853627f5d337e3f0587cb41fdc77e7eeb4f5
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417917"
---
# <a name="where-to-define-macros"></a>Definieren von Makros

Definieren von Makros in einer Befehlszeile, Befehlsdatei, Makefile oder der Datei Tools.ini.

In einem Makefile oder der Datei Tools.ini jede Makrodefinition muss in einer separaten Zeile angezeigt werden und darf nicht mit einem Leerzeichen oder Tabstopp beginnen. Leerzeichen oder Tabstopps, um das Gleichheitszeichen werden ignoriert. Alle [Zeichenfolge Zeichen](../build/defining-an-nmake-macro.md) sind Literale, einschließlich der Sie umgebenden Anführungszeichen und Leerzeichen.

In einer Befehlszeile oder eine Befehlsdatei Leerzeichen und Tabulatoren trennen die Argumente und können nicht das Gleichheitszeichen umschließen. Wenn `string` eingebettete Leerzeichen oder Tabstopps, schließen Sie entweder die Zeichenfolge oder das gesamte Makro in doppelte Anführungszeichen ("").

## <a name="see-also"></a>Siehe auch

[Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)
