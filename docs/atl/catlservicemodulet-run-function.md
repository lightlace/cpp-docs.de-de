---
title: 'CAtlServiceModuleT:: Start-Funktion'
ms.date: 11/04/2016
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: 3abb6908a64864463c45d8fc4dc24bfc813db586
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458663"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT:: Start-Funktion

`Run` enthält Aufrufe `PreMessageLoop`, `RunMessageLoop`, und `PostMessageLoop`. Nach dem aufrufen, `PreMessageLoop` zuerst speichert der Dienst die Thread-ID. Der Dienst wird diese ID verwenden, um sich selbst zu schließen durch Senden einer WM_QUIT-Nachricht mithilfe der Win32-API-Funktion, [PostThreadMessage](https://msdn.microsoft.com/library/windows/desktop/ms644946).

`PreMessageLoop` Ruft dann `InitializeSecurity`. In der Standardeinstellung `InitializeSecurity` Aufrufe [CoInitializeSecurity](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializesecurity) mit der Sicherheitsbeschreibung, die auf NULL festgelegt, was bedeutet, dass Benutzer, die Zugriff auf das Objekt verfügen.

Wenn Sie nicht, dass den Dienst seine eigene Sicherheit angeben möchten, außer Kraft setzen `PreMessageLoop` und rufen Sie nicht `InitializeSecurity`, und COM wird dann bestimmen die Sicherheitseinstellungen aus der Registrierung. Ist eine bequeme Möglichkeit, das Konfigurieren der registrierungseinstellungen der [DCOMCNFG](../atl/dcomcnfg.md) Hilfsprogramm, die weiter unten in diesem Abschnitt erläutert.

Sobald Security angegeben wird, ist das Objekt mit COM registriert, so, dass neue Clients an das Programm eine Verbindung herstellen können. Schließlich weist das Programm dem dienststeuerungs-Manager (SCM), dass er ausgeführt wird und die Anwendung eine Meldungsschleife gibt. Die Anwendung weiter ausgeführt, bis es beim Herunterfahren des Diensts beenden-Meldung zurückgesendet.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CSecurityDesc-Klasse](../atl/reference/csecuritydesc-class.md)<br/>
[CSid-Klasse](../atl/reference/csid-class.md)<br/>
[CDacl-Klasse](../atl/reference/cdacl-class.md)<br/>
[CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#run)

