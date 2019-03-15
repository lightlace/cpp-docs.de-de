---
title: 'CAtlServiceModuleT:: ServiceMain-Funktion'
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 81cd8fcbdf275063b243e215301eff504a2b5cc6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811900"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT:: ServiceMain-Funktion

Der dienststeuerungs-Manager (SCM) Ruft `ServiceMain` Wenn Sie die Systemsteuerung für die Dienste-Anwendung öffnen, wählen Sie den Dienst, und klicken Sie auf **starten**.

Nach dem dienststeuerungs-Manager ruft `ServiceMain`, ein Dienst muss dienststeuerungs-Manager eine Handlerfunktion erteilen. Mithilfe dieser Funktion können den SCM-Status des Diensts zu erhalten und übergeben Sie spezifische Anweisungen (z. B. durch das Anhalten oder Beenden). Dienststeuerungs-Manager ruft diese Funktion ab, wenn der Dienst übergibt `_Handler` an die Win32-API-Funktion, [' RegisterServiceCtrlHandler '](/windows/desktop/api/winsvc/nf-winsvc-registerservicectrlhandlera). (`_Handler` ist eine statische Memberfunktion, die die nicht statische Memberfunktion ruft [Handler](../atl/reference/catlservicemodulet-class.md#handler).)

Beim Start sollte ein Dienst dienststeuerungs-Manager von den aktuellen Status auch darüber informieren. Dies geschieht durch die Übergabe von SERVICE_START_PENDING an die Win32-API-Funktion, [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).

`ServiceMain` Ruft dann `CAtlExeModuleT::InitializeCom`, die Win32-API-Funktion aufruft [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex). In der Standardeinstellung `InitializeCom` übergibt das Flag COINIT_MULTITHREADED an die Funktion. Dieses Flag gibt an, dass das Programm ein Freethread-Server sein.

Jetzt `CAtlServiceModuleT::Run` wird aufgerufen, um die eigentliche Arbeit des Diensts führen. `Run` wird weiterhin ausgeführt, bis der Dienst beendet wird.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
