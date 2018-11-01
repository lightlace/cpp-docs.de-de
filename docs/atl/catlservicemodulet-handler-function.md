---
title: 'CAtlServiceModuleT:: Handler-Funktion'
ms.date: 11/04/2016
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: 74c52e07f5be4ac16c8f9a20115a623c53f46090
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553685"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT:: Handler-Funktion

`CAtlServiceModuleT::Handler` ist die Routine, die der dienststeuerungs-Manager (SCM) zum Abrufen des Status des Diensts, und weisen Sie ihm verschiedener Anweisungen (z. B. beenden oder anhalten) aufruft. Dienststeuerungs-Manager übergibt ein Vorgangscode `Handler` , um anzugeben, welche Aktion der Dienst ausführen soll. Ein Standarddienst in ATL generierte verarbeitet nur die Stop-Anweisung. Wenn der dienststeuerungs-Manager die Stop-Anweisung erfolgreich ist, weist den Dienst dienststeuerungs-Manager, dass das Programm wird beendet. Der Dienst ruft dann `PostThreadMessage` Beenden-Meldung an sich selbst zu veröffentlichen. Dies beendet die Nachrichtenschleife aus, und der Dienst wird letztendlich geschlossen.

Um weitere Anweisungen zu behandeln, müssen Sie die `m_status` Datenmember initialisiert, der `CAtlServiceModuleT` Konstruktor. Dieses Datenelement weist dienststeuerungs-Manager, welche Schaltflächen zu aktivieren, wenn der Dienst in der Systemsteuerung für die Dienste-Anwendung ausgewählt ist.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Handler](../atl/reference/catlservicemodulet-class.md#handler)

