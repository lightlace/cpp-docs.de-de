---
title: ILK-Dateien als Eingabe für den Linker
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 012ca9aaa50ac2f8bb9d95ef77df5bb7127c5b79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595974"
---
# <a name="ilk-files-as-linker-input"></a>ILK-Dateien als Eingabe für den Linker

Beim inkrementellen Verknüpfen aktualisiert LINK die ILK-Status-Datei, die sie während der die erste inkrementelle Verknüpfung erstellt. Diese Datei hat den gleichen Basisnamen wie die .exe-Datei oder DLL-Datei, und es hat die Erweiterung .ilk. Während der spätere inkrementelle Links aktualisiert LINK für die ILK-Datei. Wenn die ILK-Datei fehlt, LINK führt einen vollständigen Verknüpfungsvorgang durch, und erstellt eine neue ILK-Datei. Wenn die ILK-Datei nicht verwendbar ist, führt ein nicht inkrementelles Verknüpfen. Ausführliche Informationen zu inkrementellen verknüpfen, finden Sie unter den [inkrementell verknüpfen (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) Option.

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](../../build/reference/link-input-files.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)