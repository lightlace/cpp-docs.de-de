---
title: "Running the Program as a Local Server"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Dienste, running as local servers"
  - "Debuggen [ATL], running services as local server"
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Running the Program as a Local Server
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn, das Programm als Dienst auszuführen umständlich ist, können Sie die Registrierung vorübergehend ändern, damit das Programm als normaler lokalen Server ausgeführt wird.  Benennen Sie einfach den `LocalService`\-Wert unter dem "" mit `_LocalService` und stellen Sie sicher, dass die `LocalServer32` Schlüssel mit dem CLSID richtig festgelegt wird.  \(Beachten Sie, dass mit DCOMCNFG anzugeben, dass die Anwendung auf einem anderen Computer ausgeführt werden sollte die `LocalServer32` Schlüssel zu `_LocalServer32` umbenannt.\) Das Ausführen des Programms als lokaler Server erfordert mehr einigen Sekunden beim Start, da der Aufruf **StartServiceCtrlDispatcher** in `CAtlServiceModuleT::Start` einige Sekunden benötigt, bevor er fehlschlägt.  
  
## Siehe auch  
 [Debugging Tips](../atl/debugging-tips.md)