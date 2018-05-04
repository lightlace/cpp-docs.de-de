---
title: Ausführen des Programms als lokaler Server | Microsoft Docs
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
ms.openlocfilehash: c2b8a79978528493e02ac5a272dafe8da6fdc1d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="running-the-program-as-a-local-server"></a>Ausführen des Programms als lokaler Server
Wenn das Programm als Dienst ausführen unpraktisch ist, können Sie die Registrierung vorübergehend ändern, damit das Programm als normaler lokaler Server ausgeführt wird. Benennen Sie einfach die `LocalService` Wert unter der AppID an `_LocalService` und stellen Sie sicher der `LocalServer32` Schlüssel unter der CLSID richtig festgelegt ist. (Beachten Sie, dass benennt mithilfe von DCOMCNFG um anzugeben, dass Ihre Anwendung auf einem anderen Computer ausgeführt werden soll, um Ihre `LocalServer32` um `_LocalServer32`.) Das Programm ausgeführt wird, wie ein lokaler Server ein paar Sekunden beim Start da findet der Aufruf von **StartServiceCtrlDispatcher** in `CAtlServiceModuleT::Start` braucht einige Sekunden, bevor ein Fehler auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps zum Debuggen](../atl/debugging-tips.md)

