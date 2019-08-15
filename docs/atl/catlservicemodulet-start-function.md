---
title: '-Funktion für die Funktion "-Start":'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: e6de15f40e89bfffba504db04ee7a16b2a68cac9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491662"
---
# <a name="catlservicemoduletstart-function"></a>-Funktion für die Funktion "-Start":

Wenn der Dienst ausgeführt wird, `_tWinMain` ruft `CAtlServiceModuleT::WinMain`auf, der wiederum aufruft `CAtlServiceModuleT::Start`.

`CAtlServiceModuleT::Start`richtet ein Array von `SERVICE_TABLE_ENTRY` -Strukturen ein, die jeden Dienst seiner Start Funktion zuordnen. Dieses Array wird dann an die Win32-API-Funktion [StartServiceCtrlDispatcher](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw)übergeben. Theoretisch könnte eine exe mehrere Dienste verarbeiten, und das Array könnte mehrere `SERVICE_TABLE_ENTRY` Strukturen aufweisen. Derzeit unterstützt ein ATL-generierter Dienst jedoch nur einen Dienst pro exe. Daher verfügt das Array über einen einzelnen Eintrag, der den Dienstnamen und `_ServiceMain` als Start Funktion enthält. `_ServiceMain`ist eine statische Member-Funktion `CAtlServiceModuleT` von, die die nicht statische Member- `ServiceMain`Funktion aufruft.

> [!NOTE]
>  `StartServiceCtrlDispatcher` Wenn Sie keine Verbindung mit dem Dienststeuerungs-Manager (SCM) herstellen, bedeutet dies wahrscheinlich, dass das Programm nicht als Dienst ausgeführt wird. In diesem Fall ruft `CAtlServiceModuleT::Run` das Programm direkt auf, sodass das Programm als lokaler Server ausgeführt werden kann. Weitere Informationen zum Ausführen des Programms als lokaler Server finden Sie unter [Tipps zum Debuggen](../atl/debugging-tips.md).

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)
