---
title: Hergeleitete abhängige Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: d4d12d0ab686c604ce0d4495df89ec62c6160ebe
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414147"
---
# <a name="inferred-dependents"></a>Hergeleitete abhängige Dateien

Eine hergeleitete abhängige stammt aus einer Rückschlussregel und ausgewertet wird, bevor der expliziten Abhängigkeiten. Wenn eine hergeleitete abhängige in Bezug auf sein Ziel veraltet ist, ruft NMAKE Befehlsblock für die Abhängigkeit. Wenn eine hergeleitete abhängige nicht vorhanden ist oder in Bezug auf seine eigenen Abhängigkeiten veraltet ist, aktualisiert die hergeleitete abhängige Datei zuerst. Weitere Informationen zu hergeleitete abhängige Dateien, finden Sie unter [Rückschlussregeln](../build/inference-rules.md).

## <a name="see-also"></a>Siehe auch

[Abhängige Dateien](../build/dependents.md)
