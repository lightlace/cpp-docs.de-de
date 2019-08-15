---
title: "\"-Funktion (\") \": ServiceMain-Funktion"
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: b79767d4c1696174f90a325ea152ccc7939ed9fe
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491713"
---
# <a name="catlservicemoduletservicemain-function"></a>"-Funktion (") ": ServiceMain-Funktion

Der Dienststeuerungs-Manager (SCM) `ServiceMain` Ruft auf, wenn Sie die System Steuerungsanwendung "Dienste" öffnen, den Dienst auswählen und auf " **starten**" klicken.

Nachdem der SCM aufgerufen `ServiceMain`hat, muss ein Dienst dem SCM eine Handlerfunktion einräumen. Mit dieser Funktion kann der SCM den Dienststatus abrufen und bestimmte Anweisungen (z. b. anhalten oder beenden) übergeben. Diese Funktion wird vom SCM abgerufen, wenn der `_Handler` Dienst an die Win32-API-Funktion, [registerservicectrlhandler](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw), übergibt. (`_Handler` ist eine statische Member-Funktion, die den nicht statischen Member-Funktions [Handler](../atl/reference/catlservicemodulet-class.md#handler)aufruft.)

Beim Start sollte ein Dienst auch den SCM über seinen aktuellen Status informieren. Dies geschieht durch Übergeben von SERVICE_START_PENDING an die Win32-API-Funktion [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus).

`ServiceMain`Anschließend wird `CAtlExeModuleT::InitializeCom`aufgerufen, wodurch die Win32-API-Funktion [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)aufgerufen wird. Standardmäßig `InitializeCom` übergibt das COINIT_MULTITHREADED-Flag an die-Funktion. Dieses Flag gibt an, dass das Programm ein frei Thread Server sein soll.

Nun wird `CAtlServiceModuleT::Run` aufgerufen, um die Hauptarbeit des Dienstanbieter auszuführen. `Run`wird weiter ausgeführt, bis der Dienst beendet wird.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
