---
title: EDITBIN-Referenz
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: c2c0ee66ed1811755edc33b24737e057554fd01f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542904"
---
# <a name="editbin-reference"></a>EDITBIN-Referenz

Die Microsoft COFF-Binärdatei-Editor (EDITBIN. EXE-Datei) ändert, Binärdateien Common Object File Format (COFF). EDITBIN können Sie die um Objektdateien, ausführbaren Dateien und Dynamic Link Libraries (DLL) zu ändern.

> [!NOTE]
>  Sie können dieses Tool nur über die Visual Studio-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.

EDITBIN ist nicht verfügbar für die Verwendung in Dateien mit der ["/ GL"](../../build/reference/gl-whole-program-optimization.md) -Compileroption. Änderungen an Binärdateien, die mit "/ GL" erstellt wurde, müssen Sie erreicht werden, indem Sie neu zu kompilieren und verknüpfen.

- [EDITBIN-Befehlszeile](../../build/reference/editbin-command-line.md)

- [EDITBIN-Optionen](../../build/reference/editbin-options.md)

## <a name="see-also"></a>Siehe auch

[C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)