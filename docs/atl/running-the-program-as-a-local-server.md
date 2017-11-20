---
title: "Ausführen des Programms als lokaler Server | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 131bfefb35164b2d1e53f5671016235e5426c096
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="running-the-program-as-a-local-server"></a>Ausführen des Programms als lokaler Server
Wenn das Programm als Dienst ausführen unpraktisch ist, können Sie die Registrierung vorübergehend ändern, damit das Programm als normaler lokaler Server ausgeführt wird. Benennen Sie einfach die `LocalService` Wert unter der AppID an `_LocalService` und stellen Sie sicher der `LocalServer32` Schlüssel unter der CLSID richtig festgelegt ist. (Beachten Sie, dass benennt mithilfe von DCOMCNFG um anzugeben, dass Ihre Anwendung auf einem anderen Computer ausgeführt werden soll, um Ihre `LocalServer32` um `_LocalServer32`.) Das Programm ausgeführt wird, wie ein lokaler Server ein paar Sekunden beim Start da findet der Aufruf von **StartServiceCtrlDispatcher** in `CAtlServiceModuleT::Start` braucht einige Sekunden, bevor ein Fehler auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps zum Debuggen](../atl/debugging-tips.md)

