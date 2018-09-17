---
title: . ILK-Dateien als Linkereingabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3b8de3758daf59a543cdcc9f3b73e1d6c6f0ce8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720589"
---
# <a name="ilk-files-as-linker-input"></a>ILK-Dateien als Eingabe für den Linker

Beim inkrementellen Verknüpfen aktualisiert LINK die ILK-Status-Datei, die sie während der die erste inkrementelle Verknüpfung erstellt. Diese Datei hat den gleichen Basisnamen wie die .exe-Datei oder DLL-Datei, und es hat die Erweiterung .ilk. Während der spätere inkrementelle Links aktualisiert LINK für die ILK-Datei. Wenn die ILK-Datei fehlt, LINK führt einen vollständigen Verknüpfungsvorgang durch, und erstellt eine neue ILK-Datei. Wenn die ILK-Datei nicht verwendbar ist, führt ein nicht inkrementelles Verknüpfen. Ausführliche Informationen zu inkrementellen verknüpfen, finden Sie unter den [inkrementell verknüpfen (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) Option.

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](../../build/reference/link-input-files.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)