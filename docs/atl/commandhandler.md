---
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 743be3e0bc9cc96fc6b22d0806d399ab5e160a3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235063"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` die Funktion wird durch den dritten Parameter des COMMAND_HANDLER Makros in der meldungszuordnung identifiziert werden.

## <a name="syntax"></a>Syntax

```cpp
LRESULT CommandHandler(
    WORD wNotifyCode,
    WORD wID,
    HWND hWndCtl,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parameter

*wNotifyCode*<br/>
Der Benachrichtigungscode.

*wID*<br/>
Der Bezeichner der dem Menüelement-Steuerelement oder Accelerator.

*hWndCtl*<br/>
Ein Handle für ein Window-Steuerelement.

*bHandled*<br/>
Die Zuordnung Nachrichtensätze *bHandled* auf "true", bevor Sie `CommandHandler` aufgerufen wird. Wenn `CommandHandler` ist nicht vollständig verarbeitet die Nachricht sollte *bHandled* auf "false", um anzugeben, die Nachricht noch weitere Verarbeitung erforderlich.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung. Bei Erfolg 0.

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung dieser Nachrichtenhandler in einer meldungszuordnung, finden Sie unter [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)<br/>
[Meldungszuordnungen](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
