---
title: Meldungshandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MessageHandler
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: 3627dadde60a5ba0ece90497b85e2085f33e0919
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448398"
---
# <a name="messagehandler"></a>Meldungshandler

`MessageHandler` ist der Name der Funktion durch den zweiten Parameter, der das Makro MESSAGE_HANDLER aus, in der meldungszuordnung identifiziert.

## <a name="syntax"></a>Syntax

```
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*uMsg*<br/>
Gibt die Meldung.

*wParam-Parameter*<br/>
Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
Zusätzliche meldungsspezifische Informationen.

*bHandled*<br/>
Die Zuordnung Nachrichtensätze *bHandled* auf "true", bevor Sie `MessageHandler` aufgerufen wird. Wenn `MessageHandler` ist nicht vollständig verarbeitet die Nachricht sollte *bHandled* auf "false", um anzugeben, die Nachricht noch weitere Verarbeitung erforderlich.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung. Bei Erfolg 0.

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung dieser Nachrichtenhandler in einer meldungszuordnung, finden Sie unter [MESSAGE_HANDLER aus](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)<br/>
[Meldungszuordnungen](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)
