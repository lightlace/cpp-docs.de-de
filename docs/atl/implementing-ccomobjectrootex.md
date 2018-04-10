---
title: Implementierung von CComObjectRootEx | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CComObjectRootEx
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ae8b8266aca2c9d6099455ddcb7618206dbe8c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-ccomobjectrootex"></a>Implementierung von CComObjectRootEx
[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) unbedingt; alle ATL-Objekten benötigen eine Instanz des `CComObjectRootEx` oder [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) in ihre Vererbung. `CComObjectRootEx`Stellt den Standardwert `QueryInterface` Mechanismus auf der Grundlage von COM-Zuordnungseinträge.  
  
 Über die COM-Zuordnung sind die Schnittstellen eines Objekts für einen Client verfügbar, wenn der Client nach einer Schnittstelle fragt. Die Abfrage wird mittels `CComObjectRootEx::InternalQueryInterface` durchgeführt. `InternalQueryInterface`nur behandelt Schnittstellen in der COM-Zuordnungstabelle.  
  
 Geben Sie den Schnittstellen, in der COM-Zuordnungstabelle mit der [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) -Makro oder einer dessen Varianten. Mit dem folgenden Code werden beispielsweise die Schnittstellen `IDispatch`, `IBeeper` und `ISupportErrorInfo` in die COM-Zuordnungstabelle eingegeben:  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ATL-COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)   
 [COM-Zuordnungs-Makros](../atl/reference/com-map-macros.md)

