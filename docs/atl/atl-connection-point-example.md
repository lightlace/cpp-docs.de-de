---
title: Beispiel für ATL-Verbindungspunkt
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: f33364cee65031c358fb546312f3fe2b7ae854d3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491798"
---
# <a name="atl-connection-point-example"></a>Beispiel für ATL-Verbindungspunkt

Dieses Beispiel zeigt ein Objekt, das [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) als ausgehende Schnittstelle unterstützt:

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

Wenn Sie `IPropertyNotifySink` als ausgehende Schnittstelle angeben, können Sie die Klasse [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) anstelle von `IConnectionPointImpl`verwenden. Beispiel:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>Siehe auch

[Verbindungspunkt](../atl/atl-connection-points.md)
