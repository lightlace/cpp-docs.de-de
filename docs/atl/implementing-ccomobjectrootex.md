---
title: Implementieren von CComObjectRootEx | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CComObjectRootEx
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fefc7c3ed9177fb756e6298b54121a638ac8e253
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767477"
---
# <a name="implementing-ccomobjectrootex"></a>Implementieren von CComObjectRootEx

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) ist wesentlich; alle ATL-Objekte müssen eine Instanz des `CComObjectRootEx` oder [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) bei der Vererbung. `CComObjectRootEx` Stellt den Standardwert `QueryInterface` -Mechanismus basierend auf COM-Zuordnungseinträgen.

Über die COM-Zuordnung sind die Schnittstellen eines Objekts für einen Client verfügbar, wenn der Client nach einer Schnittstelle fragt. Die Abfrage wird mittels `CComObjectRootEx::InternalQueryInterface` durchgeführt. `InternalQueryInterface` behandelt nur Schnittstellen in der COM-Zuordnungstabelle.

Sie können Schnittstellen eingeben, in die COM-Zuordnungstabelle mit der [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) Makro oder eine ihrer Varianten. Mit dem folgenden Code werden beispielsweise die Schnittstellen `IDispatch`, `IBeeper` und `ISupportErrorInfo` in die COM-Zuordnungstabelle eingegeben:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>Siehe auch

[Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)   
[COM-Zuordnungs-Makros](../atl/reference/com-map-macros.md)

