---
title: Was ist ein Hostobjekt? (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d197f02949f6eaaeee50b428338684135d1db27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="what-is-a-host-object"></a>Was ist ein Hostobjekt?
Ein Hostobjekt ist ein COM-Objekt, das dem ActiveX-Steuerelementcontainer vom ATL für ein bestimmtes Fenster darstellt. Der Host Objekt Unterklassen Containerfenster, damit Nachrichten an das Steuerelement widerspiegeln, er bietet die notwendigen Containerschnittstellen, die vom Steuerelement verwendet werden und macht die [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) und [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) Schnittstellen, die Ihnen ermöglichen, konfigurieren Sie die Umgebung des Steuerelements.  
  
 Sie können das Hostobjekt, das zum Festlegen der ambient-Eigenschaften des Containers verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

