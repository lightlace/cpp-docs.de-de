---
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 99a95228f6036e5f391395be367cdef39ca3dc3b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492456"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler`die Funktion, die durch den dritten Parameter des COMMAND_HANDLER-Makros in der Meldungs Zuordnung identifiziert wird.

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
Der Benachrichtigungs Code.

*wID*<br/>
Der Bezeichner des Menü Elements, des Steuer Elements oder der Zugriffstaste.

*hWndCtl*<br/>
Ein Handle für ein Fenster Steuerelement.

*bHandled*<br/>
In der Meldungs Zuordnung wird *bbehandelte* auf `CommandHandler` true festgelegt, bevor aufgerufen wird. Wenn `CommandHandler` die Nachricht nicht vollständig verarbeitet, sollte *bbehandelte* auf false festgelegt werden, um anzugeben, dass die Nachricht weiterverarbeitet werden muss.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung. 0, wenn erfolgreich.

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung dieses Nachrichten Handlers in einer Meldungs Zuordnung finden Sie unter [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)<br/>
[Meldungszuordnungen](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
