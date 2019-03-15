---
title: Hergeleitete abhängige Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 2382dec960ef93fc2f73987ad27b4670768a68cc
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825558"
---
# <a name="inferred-dependents"></a>Hergeleitete abhängige Dateien

Eine hergeleitete abhängige stammt aus einer Rückschlussregel und ausgewertet wird, bevor der expliziten Abhängigkeiten. Wenn eine hergeleitete abhängige in Bezug auf sein Ziel veraltet ist, ruft NMAKE Befehlsblock für die Abhängigkeit. Wenn eine hergeleitete abhängige nicht vorhanden ist oder in Bezug auf seine eigenen Abhängigkeiten veraltet ist, aktualisiert die hergeleitete abhängige Datei zuerst. Weitere Informationen zu hergeleitete abhängige Dateien, finden Sie unter [Rückschlussregeln](inference-rules.md).

## <a name="see-also"></a>Siehe auch

[Abhängige Dateien](dependents.md)
