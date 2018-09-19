---
title: 'CAtlServiceModuleT:: Handler-Funktion | Microsoft-Dokumentation'
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
ms.openlocfilehash: 7c8dc0b0d41a18c775258e1eacddd8e4dbebdb3d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039217"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT:: Handler-Funktion

`CAtlServiceModuleT::Handler` ist die Routine, die der dienststeuerungs-Manager (SCM) zum Abrufen des Status des Diensts, und weisen Sie ihm verschiedener Anweisungen (z. B. beenden oder anhalten) aufruft. Dienststeuerungs-Manager übergibt ein Vorgangscode `Handler` , um anzugeben, welche Aktion der Dienst ausführen soll. Ein Standarddienst in ATL generierte verarbeitet nur die Stop-Anweisung. Wenn der dienststeuerungs-Manager die Stop-Anweisung erfolgreich ist, weist den Dienst dienststeuerungs-Manager, dass das Programm wird beendet. Der Dienst ruft dann `PostThreadMessage` Beenden-Meldung an sich selbst zu veröffentlichen. Dies beendet die Nachrichtenschleife aus, und der Dienst wird letztendlich geschlossen.

Um weitere Anweisungen zu behandeln, müssen Sie die `m_status` Datenmember initialisiert, der `CAtlServiceModuleT` Konstruktor. Dieses Datenelement weist dienststeuerungs-Manager, welche Schaltflächen zu aktivieren, wenn der Dienst in der Systemsteuerung für die Dienste-Anwendung ausgewählt ist.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Handler](../atl/reference/catlservicemodulet-class.md#handler)

