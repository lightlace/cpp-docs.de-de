---
title: Implementieren von CComObjectRootEx
ms.date: 11/04/2016
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
ms.openlocfilehash: 80ce9936546b936770d8dedd0ba55f8c05617d37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197470"
---
# <a name="implementing-ccomobjectrootex"></a>Implementieren von CComObjectRootEx

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) ist wesentlich; alle ATL-Objekte müssen eine Instanz des `CComObjectRootEx` oder [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) bei der Vererbung. `CComObjectRootEx` Stellt den Standardwert `QueryInterface` -Mechanismus basierend auf COM-Zuordnungseinträgen.

Über die COM-Zuordnung sind die Schnittstellen eines Objekts für einen Client verfügbar, wenn der Client nach einer Schnittstelle fragt. Die Abfrage wird mittels `CComObjectRootEx::InternalQueryInterface` durchgeführt. `InternalQueryInterface` behandelt nur Schnittstellen in der COM-Zuordnungstabelle.

Sie können Schnittstellen eingeben, in die COM-Zuordnungstabelle mit der [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) Makro oder eine ihrer Varianten. Mit dem folgenden Code werden beispielsweise die Schnittstellen `IDispatch`, `IBeeper` und `ISupportErrorInfo` in die COM-Zuordnungstabelle eingegeben:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>Siehe auch

[Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)<br/>
[COM-Zuordnungs-Makros](../atl/reference/com-map-macros.md)
