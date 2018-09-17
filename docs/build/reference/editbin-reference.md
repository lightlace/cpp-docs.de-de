---
title: EDITBIN-Referenz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 809d1d4f25611b2310d651702f01e1e98888ad4a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699946"
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