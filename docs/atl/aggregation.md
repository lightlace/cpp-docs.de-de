---
title: Aggregation
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: 288af427bd6a8d9baf572dfad8e4a25452694ad9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491972"
---
# <a name="aggregation"></a>Aggregation

Es gibt Zeiten, in denen die Implementierung eines Objekts die Dienste nutzen möchte, die von einem anderen, vorgefertigten Objekt angeboten werden. Außerdem soll dieses zweite Objekt als natürlicher Teil des ersten Objekts angezeigt werden. COM erreicht beide dieser Ziele durch Einschluss und Aggregation.

Aggregation bedeutet, dass das enthaltende (äußere) Objekt als Teil des Erstellungs Prozesses das enthaltene (innere) Objekt erstellt und die Schnittstellen des inneren Objekts vom äußeren verfügbar gemacht werden. Ein Objekt kann aggregiert werden. Wenn dies der Fall ist, müssen bestimmte Regeln für die Aggregation befolgt werden, damit Sie ordnungsgemäß funktionieren.

Hauptsächlich müssen `IUnknown` alle Methodenaufrufe für das enthaltene Objekt an das enthaltende Objekt delegieren.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[Wieder verwenden von Objekten](/windows/win32/com/reusing-objects)
