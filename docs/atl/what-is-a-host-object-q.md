---
title: Was ist ein Hostobjekt? (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da735caa84c133b9cdf63fae5df8bdd3d5f774b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="what-is-a-host-object"></a>Was ist ein Hostobjekt?
Ein Hostobjekt ist ein COM-Objekt, das dem ActiveX-Steuerelementcontainer vom ATL für ein bestimmtes Fenster darstellt. Der Host Objekt Unterklassen Containerfenster, damit Nachrichten an das Steuerelement widerspiegeln, er bietet die notwendigen Containerschnittstellen, die vom Steuerelement verwendet werden und macht die [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) und [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) Schnittstellen, die Ihnen ermöglichen, konfigurieren Sie die Umgebung des Steuerelements.  
  
 Sie können das Hostobjekt, das zum Festlegen der ambient-Eigenschaften des Containers verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

