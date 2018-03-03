---
title: CAtlServiceModuleT::Handler Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs:
- C++
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00158bbed5318d919c284b91cd651141a35bd441
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler-Funktion
`CAtlServiceModuleT::Handler`ist die Routine, die der dienststeuerungs-Manager (SCM) zum Abrufen des Status des Diensts, und weisen Sie ihm verschiedene Anweisungen (z. B. beenden oder anhalten) aufgerufen. SCM übergibt ein Vorgangscode zu `Handler` , um anzugeben, wie der Dienst vorgegangen. Eine ATL generierte Standarddienst verarbeitet nur die Stop-Anweisung. Wenn die SCM Stop-Anweisung übergibt, weist den Dienst dem SCM, dass das Programm beendet. Der Dienst ruft dann `PostThreadMessage` zum Beenden-Meldung mit sich selbst bereitstellen. Die Nachrichtenschleife wird beendet, und der Dienst wird letztendlich geschlossen.  
  
 Um weitere Anweisungen zu behandeln, müssen Sie ändern die `m_status` Datenmember initialisiert, der `CAtlServiceModuleT` Konstruktor. Dieses Datenelement weist SCM, welche Schaltflächen aktivieren, wenn der Dienst in der Anwendung Dienste in der Systemsteuerung ausgewählt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

