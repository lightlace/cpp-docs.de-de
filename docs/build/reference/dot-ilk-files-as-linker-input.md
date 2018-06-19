---
title: . ILK-Dateien als Linkereingabe | Microsoft Docs
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
ms.openlocfilehash: 01fea585b86114373017b6d73948cb1438b7185e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371683"
---
# <a name="ilk-files-as-linker-input"></a>ILK-Dateien als Eingabe für den Linker
Beim inkrementellen Verknüpfen aktualisiert LINK die ILK-Status-Datei, die er während der ersten inkrementellen Link erstellt hat. Diese Datei hat den gleichen Basisnamen wie die .exe oder .dll-Datei, und es hat die Erweiterung .ilk. Während der spätere inkrementelle Links aktualisiert LINK die ILK-Datei. Wenn die ILK-Datei nicht vorhanden ist, wird LINK führt einen vollständigen Verknüpfungsvorgang durch und erstellt eine neue ILK-Datei. Wenn die ILK-Datei unbrauchbar ist, führt ein nicht inkrementelles Verknüpfen. Weitere Informationen zu inkrementellen verknüpfen, finden Sie unter der [inkrementell verknüpfen (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) Option.  
  
## <a name="see-also"></a>Siehe auch  
 [LINK-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)