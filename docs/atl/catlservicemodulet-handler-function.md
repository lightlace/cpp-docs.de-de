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
ms.openlocfilehash: e344fd36ad6c70a80486eef6a10eacd8a88a2baf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273373"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT:: Handler-Funktion

`CAtlServiceModuleT::Handler` ist die Routine, die der dienststeuerungs-Manager (SCM) zum Abrufen des Status des Diensts, und weisen Sie ihm verschiedener Anweisungen (z. B. beenden oder anhalten) aufruft. Dienststeuerungs-Manager übergibt ein Vorgangscode `Handler` , um anzugeben, welche Aktion der Dienst ausführen soll. Ein Standarddienst in ATL generierte verarbeitet nur die Stop-Anweisung. Wenn der dienststeuerungs-Manager die Stop-Anweisung erfolgreich ist, weist den Dienst dienststeuerungs-Manager, dass das Programm wird beendet. Der Dienst ruft dann `PostThreadMessage` Beenden-Meldung an sich selbst zu veröffentlichen. Dies beendet die Nachrichtenschleife aus, und der Dienst wird letztendlich geschlossen.

Um weitere Anweisungen zu behandeln, müssen Sie die `m_status` Datenmember initialisiert, der `CAtlServiceModuleT` Konstruktor. Dieses Datenelement weist dienststeuerungs-Manager, welche Schaltflächen zu aktivieren, wenn der Dienst in der Systemsteuerung für die Dienste-Anwendung ausgewählt ist.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)
