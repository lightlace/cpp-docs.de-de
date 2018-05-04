---
title: Implementierung von CComObjectRootEx | Microsoft Docs
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
ms.openlocfilehash: 44c62e7589b9b300ceaa2886760bf2c3d85550ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-ccomobjectrootex"></a>Implementierung von CComObjectRootEx
[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) unbedingt; alle ATL-Objekten benötigen eine Instanz des `CComObjectRootEx` oder [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) in ihre Vererbung. `CComObjectRootEx` Stellt den Standardwert `QueryInterface` Mechanismus auf der Grundlage von COM-Zuordnungseinträge.  
  
 Über die COM-Zuordnung sind die Schnittstellen eines Objekts für einen Client verfügbar, wenn der Client nach einer Schnittstelle fragt. Die Abfrage wird mittels `CComObjectRootEx::InternalQueryInterface` durchgeführt. `InternalQueryInterface` Nur behandelt Schnittstellen in der COM-Zuordnungstabelle.  
  
 Geben Sie den Schnittstellen, in der COM-Zuordnungstabelle mit der [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) -Makro oder einer dessen Varianten. Mit dem folgenden Code werden beispielsweise die Schnittstellen `IDispatch`, `IBeeper` und `ISupportErrorInfo` in die COM-Zuordnungstabelle eingegeben:  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ATL-COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)   
 [COM-Zuordnungs-Makros](../atl/reference/com-map-macros.md)

