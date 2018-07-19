---
title: Ausführen des Programms als lokaler Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae2e44ba51a878d293ad5b497a1638cc9d7dc76
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848482"
---
# <a name="running-the-program-as-a-local-server"></a>Ausführen des Programms als lokaler Server
Wenn die Anwendung als Dienst ausführen mergereplikationsabonnenten nicht geeignet ist, können Sie die Registrierung vorübergehend ändern, damit das Programm als normaler lokalen Server ausgeführt wird. Benennen Sie einfach die `LocalService` Wert unter Ihrem App-ID, `_LocalService` und stellen Sie sicher die `LocalServer32` Schlüssel unter Ihrer CLSID richtig festgelegt ist. (Beachten Sie, dass benennt mithilfe von DCOMCNFG um anzugeben, dass Ihre Anwendung auf einem anderen Computer ausgeführt werden soll, um Ihre `LocalServer32` um `_LocalServer32`.) Das Programm ausgeführt wird, wie ein lokaler Server Weitere wenige Sekunden beim Start dauert da der Aufruf von `StartServiceCtrlDispatcher` in `CAtlServiceModuleT::Start` dauert ein paar Sekunden, bevor ein Fehler auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps zum Debuggen](../atl/debugging-tips.md)

