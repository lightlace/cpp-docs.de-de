---
title: CAtlServiceModuleT::Handler Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs:
- C++
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0c0386cd17e7a33628790520e356c706f9743b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler-Funktion
`CAtlServiceModuleT::Handler` ist die Routine, die der dienststeuerungs-Manager (SCM) zum Abrufen des Status des Diensts, und weisen Sie ihm verschiedene Anweisungen (z. B. beenden oder anhalten) aufgerufen. SCM übergibt ein Vorgangscode zu `Handler` , um anzugeben, wie der Dienst vorgegangen. Eine ATL generierte Standarddienst verarbeitet nur die Stop-Anweisung. Wenn die SCM Stop-Anweisung übergibt, weist den Dienst dem SCM, dass das Programm beendet. Der Dienst ruft dann `PostThreadMessage` zum Beenden-Meldung mit sich selbst bereitstellen. Die Nachrichtenschleife wird beendet, und der Dienst wird letztendlich geschlossen.  
  
 Um weitere Anweisungen zu behandeln, müssen Sie ändern die `m_status` Datenmember initialisiert, der `CAtlServiceModuleT` Konstruktor. Dieses Datenelement weist SCM, welche Schaltflächen aktivieren, wenn der Dienst in der Anwendung Dienste in der Systemsteuerung ausgewählt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

