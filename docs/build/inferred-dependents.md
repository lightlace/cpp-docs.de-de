---
title: Hergeleitete abhängige Elemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 631c5631b60f0e05dd1f1541facc767f35944d3d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701479"
---
# <a name="inferred-dependents"></a>Hergeleitete abhängige Dateien

Eine hergeleitete abhängige stammt aus einer Rückschlussregel und ausgewertet wird, bevor der expliziten Abhängigkeiten. Wenn eine hergeleitete abhängige in Bezug auf sein Ziel veraltet ist, ruft NMAKE Befehlsblock für die Abhängigkeit. Wenn eine hergeleitete abhängige nicht vorhanden ist oder in Bezug auf seine eigenen Abhängigkeiten veraltet ist, aktualisiert die hergeleitete abhängige Datei zuerst. Weitere Informationen zu hergeleitete abhängige Dateien, finden Sie unter [Rückschlussregeln](../build/inference-rules.md).

## <a name="see-also"></a>Siehe auch

[Abhängige Dateien](../build/dependents.md)