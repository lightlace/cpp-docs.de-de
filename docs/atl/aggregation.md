---
title: Aggregation
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: d5a09dcd8c289447491ebc7111a77549166a7d00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633411"
---
# <a name="aggregation"></a>Aggregation

Es gibt Situationen, wenn ein Objekt der Implementierer, Nutzen der Dienste, die von einem anderen, bereits erstellte Objekt möchten. Darüber hinaus möchten sie dieses zweite Objekt als einem natürlichen Bestandteil der ersten angezeigt werden. COM erreicht werden beide dieser Ziele durch Kapselung und Aggregation.

Aggregation bedeutet, dass das enthaltende (äußere) Objekt (innere) enthaltenen Objekts im Rahmen der Erstellung erstellt und die Schnittstellen des inneren Objekts von der äußeren verfügbar gemacht werden. Ein Objekt kann selbst aggregierbar sein muss. Wenn es sich handelt, muss er bestimmte Regeln für die Aggregation zum ordnungsgemäßen folgen.

In erster Linie für alle `IUnknown` -Methodenaufrufe des enthaltenen Objekts auf das enthaltende Objekt delegieren müssen.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[Wiederverwendung von Objekten](/windows/desktop/com/reusing-objects)

