---
title: Beispiel für ATL-Verbindungspunkt
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 9312db740171672e6b0f231855408e0d0a9e060d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495991"
---
# <a name="atl-connection-point-example"></a>Beispiel für ATL-Verbindungspunkt

Dieses Beispiel zeigt ein Objekt, das unterstützt [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) als Ausgangsschnittstelle:

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

Beim Angeben von `IPropertyNotifySink` als Ausgangsschnittstelle, können Sie Klasse [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) anstelle von `IConnectionPointImpl`. Zum Beispiel:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>Siehe auch

[Verbindungspunkt](../atl/atl-connection-points.md)

