---
title: 'CAtlServiceModuleT:: Start-Funktion'
ms.date: 11/04/2016
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 0730bad600190ed06c6f40a4a7cf396f0924a5fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476630"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT:: Start-Funktion

Wenn der Dienst ausgeführt wird, `_tWinMain` Aufrufe `CAtlServiceModuleT::WinMain`, die wiederum ruft `CAtlServiceModuleT::Start`.

`CAtlServiceModuleT::Start` ein Array von richtet `SERVICE_TABLE_ENTRY` Strukturen, die jeder Dienst seine Startfunktion beim zugeordnet. Dieses Array wird dann an die Win32-API-Funktion übergeben [StartServiceCtrlDispatcher](/windows/desktop/api/winsvc/nf-winsvc-startservicectrldispatchera). Theoretisch kann eine EXE-Datei mehrere Dienste behandeln und das Array möglicherweise mehrere `SERVICE_TABLE_ENTRY` Strukturen. Allerdings unterstützt ein ATL generierte-Dienst derzeit nur ein Dienst pro exe-Datei. Daher verfügt das Array über einen einzelnen Eintrag, der den Dienstnamen enthält, und `_ServiceMain` als die Startfunktion. `_ServiceMain` ist eine statischen Memberfunktion `CAtlServiceModuleT` aufruft, die nicht statische Memberfunktion `ServiceMain`.

> [!NOTE]
>  Fehler des `StartServiceCtrlDispatcher` zur Verbindung mit der dienststeuerungs-Manager (SCM)-wahrscheinlich bedeutet, dass das Programm nicht als Dienst ausgeführt wird. In diesem Fall die Anwendung ruft `CAtlServiceModuleT::Run` direkt, damit das Programm als lokaler Server ausführen kann. Weitere Informationen zu Ausführung des Programms als lokaler Server, finden Sie unter [Debuggen Tipps](../atl/debugging-tips.md).

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#start)

