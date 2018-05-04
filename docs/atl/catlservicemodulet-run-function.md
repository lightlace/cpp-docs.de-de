---
title: 'CServiceModule:: Run-Funktion | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a07ad6b09fa10a81b500625531226dc18fc6281a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="catlservicemoduletrun-function"></a>CServiceModule:: Run-Funktion
**Führen Sie** enthält Aufrufe `PreMessageLoop`, `RunMessageLoop`, und `PostMessageLoop`. Nach dem aufgerufenen, `PreMessageLoop` zuerst speichert der Dienst-Thread-ID. Der Dienst wird diese ID verwenden, selbst per schließen eine **WM_QUIT** Nachricht mit der Win32-API-Funktion [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` Ruft dann `InitializeSecurity`. Standardmäßig `InitializeSecurity` Aufrufe [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) mit der Sicherheitsbeschreibung, die auf NULL festgelegt, was bedeutet, dass jeder Benutzer Zugriff auf das Objekt hat.  
  
 Wenn Sie nicht, dass den Dienst seiner eigenen Sicherheitsberechtigungen angeben möchten, überschreiben `PreMessageLoop` und rufen Sie nicht `InitializeSecurity`, und COM ermitteln Sie dann die Sicherheitseinstellungen aus der Registrierung wird. Eine einfache Möglichkeit zum Konfigurieren der registrierungseinstellungen ist mit der [DCOMCNFG](../atl/dcomcnfg.md) Hilfsprogramm weiter unten in diesem Abschnitt erläutert.  
  
 Sobald Sicherheit angegeben wird, wird das Objekt bei COM registriert, damit neue Clients an das Programm eine Verbindung herstellen können. Schließlich weist das Programm dem Dienstkontroll-Manager (SCM), dass er ausgeführt wird und eine Nachrichtenschleife eingetragen. Die Anwendung weiter ausgeführt, bis es beim Herunterfahren des Diensts beenden-Meldung zurückgesendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CSecurityDesc-Klasse](../atl/reference/csecuritydesc-class.md)   
 [CSid-Klasse](../atl/reference/csid-class.md)   
 [CDacl-Klasse](../atl/reference/cdacl-class.md)   
 [CServiceModule:: Run](../atl/reference/catlservicemodulet-class.md#run)

