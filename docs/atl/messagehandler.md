---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: aa044ef88ba3c872c2652cd774ac50024e52c68c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492314"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler`der Name der Funktion, die durch den zweiten Parameter des MESSAGE_HANDLER-Makros in der Meldungs Zuordnung identifiziert wird.

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
Gibt die Meldung an.

*wParam*<br/>
Zusätzliche Nachrichten spezifische Informationen.

*lParam*<br/>
Zusätzliche Nachrichten spezifische Informationen.

*bHandled*<br/>
In der Meldungs Zuordnung wird *bbehandelte* auf `MessageHandler` true festgelegt, bevor aufgerufen wird. Wenn `MessageHandler` die Nachricht nicht vollständig verarbeitet, sollte *bbehandelte* auf false festgelegt werden, um anzugeben, dass die Nachricht weiterverarbeitet werden muss.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung. 0, wenn erfolgreich.

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung dieses Nachrichten Handlers in einer Meldungs Zuordnung finden Sie unter [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)<br/>
[Meldungszuordnungen](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
