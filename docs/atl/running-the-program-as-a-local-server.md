---
title: Ausführen des Programms als lokaler Server
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: 9a55dba861457eae888f519fb3bbd6c7a66e623c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610859"
---
# <a name="running-the-program-as-a-local-server"></a>Ausführen des Programms als lokaler Server

Wenn die Anwendung als Dienst ausführen mergereplikationsabonnenten nicht geeignet ist, können Sie die Registrierung vorübergehend ändern, damit das Programm als normaler lokalen Server ausgeführt wird. Benennen Sie einfach die `LocalService` Wert unter Ihrem App-ID, `_LocalService` und stellen Sie sicher die `LocalServer32` Schlüssel unter Ihrer CLSID richtig festgelegt ist. (Beachten Sie, dass benennt mithilfe von DCOMCNFG um anzugeben, dass Ihre Anwendung auf einem anderen Computer ausgeführt werden soll, um Ihre `LocalServer32` um `_LocalServer32`.) Das Programm ausgeführt wird, wie ein lokaler Server Weitere wenige Sekunden beim Start dauert da der Aufruf von `StartServiceCtrlDispatcher` in `CAtlServiceModuleT::Start` dauert ein paar Sekunden, bevor ein Fehler auftritt.

## <a name="see-also"></a>Siehe auch

[Tipps zum Debuggen](../atl/debugging-tips.md)

