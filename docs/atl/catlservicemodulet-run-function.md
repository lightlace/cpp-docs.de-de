---
title: 'Die Funktion "-Funktion ausführen":'
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: 0c35020996852731a8f22c15860d4cceb7a8bdb6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491521"
---
# <a name="catlservicemoduletrun-function"></a>Die Funktion "-Funktion ausführen":

`Run`enthält Aufrufe von `PreMessageLoop`, `RunMessageLoop`und `PostMessageLoop`. Nach dem Aufrufen speichert zuerstdieThread-IDdesdienstanders.`PreMessageLoop` Der Dienst verwendet diese ID, um sich selbst zu schließen, indem er eine WM_QUIT-Nachricht mithilfe der Win32-API-Funktion " [PostThreadMessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)" sendet.

`PreMessageLoop`Anschließend wird `InitializeSecurity`aufgerufen. Standardmäßig wird `InitializeSecurity` von [CoInitializeSecurity](/windows/win32/api/combaseapi/nf-combaseapi-coinitializesecurity) aufgerufen, wobei die Sicherheits Beschreibung auf NULL festgelegt ist, was bedeutet, dass jeder Benutzer Zugriff auf Ihr Objekt hat.

Wenn Sie nicht möchten, dass der Dienst seine eigene Sicherheit angibt, über `PreMessageLoop` schreiben `InitializeSecurity`Sie, und com führt dann die Sicherheitseinstellungen aus der Registrierung aus. Eine bequeme Möglichkeit zum Konfigurieren der Registrierungs Einstellungen ist das Hilfsprogramm [DCOMCNFG](../atl/dcomcnfg.md) , das weiter unten in diesem Abschnitt erläutert wird.

Sobald die Sicherheit angegeben ist, wird das Objekt bei com registriert, sodass neue Clients eine Verbindung mit dem Programm herstellen können. Schließlich informiert das Programm den Dienststeuerungs-Manager (SCM), dass er ausgeführt wird, und das Programm gibt eine Nachrichten Schleife ein. Das Programm wird so lange ausgeführt, bis es beim Herunterfahren des Dienstes eine Beendigungs Meldung sendet.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CSecurityDesc-Klasse](../atl/reference/csecuritydesc-class.md)<br/>
[CSid-Klasse](../atl/reference/csid-class.md)<br/>
[CDacl-Klasse](../atl/reference/cdacl-class.md)<br/>
["": Run](../atl/reference/catlservicemodulet-class.md#run)
