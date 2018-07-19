---
title: 'CAtlServiceModuleT:: Start-Funktion | Microsoft-Dokumentation'
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
ms.openlocfilehash: e509ad88a744f6ebaaca41ecd0d6455d68c2585c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850653"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT:: Start-Funktion
`Run` enthält Aufrufe `PreMessageLoop`, `RunMessageLoop`, und `PostMessageLoop`. Nach dem aufrufen, `PreMessageLoop` zuerst speichert der Dienst die Thread-ID. Der Dienst wird diese ID verwenden, um sich selbst zu schließen durch Senden einer WM_QUIT-Nachricht mithilfe der Win32-API-Funktion, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` Ruft dann `InitializeSecurity`. In der Standardeinstellung `InitializeSecurity` Aufrufe [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) mit der Sicherheitsbeschreibung, die auf NULL festgelegt, was bedeutet, dass Benutzer, die Zugriff auf das Objekt verfügen.  
  
 Wenn Sie nicht, dass den Dienst seine eigene Sicherheit angeben möchten, außer Kraft setzen `PreMessageLoop` und rufen Sie nicht `InitializeSecurity`, und COM wird dann bestimmen die Sicherheitseinstellungen aus der Registrierung. Ist eine bequeme Möglichkeit, das Konfigurieren der registrierungseinstellungen der [DCOMCNFG](../atl/dcomcnfg.md) Hilfsprogramm, die weiter unten in diesem Abschnitt erläutert.  
  
 Sobald Security angegeben wird, ist das Objekt mit COM registriert, so, dass neue Clients an das Programm eine Verbindung herstellen können. Schließlich weist das Programm dem dienststeuerungs-Manager (SCM), dass er ausgeführt wird und die Anwendung eine Meldungsschleife gibt. Die Anwendung weiter ausgeführt, bis es beim Herunterfahren des Diensts beenden-Meldung zurückgesendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CSecurityDesc-Klasse](../atl/reference/csecuritydesc-class.md)   
 [CSid-Klasse](../atl/reference/csid-class.md)   
 [CDacl-Klasse](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#run)

