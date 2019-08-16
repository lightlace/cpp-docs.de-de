---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 16fb330d2da83ddfd013e33a2d4b688b2711103b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492306"
---
# <a name="notifyhandler"></a>NotifyHandler

Der Name der Funktion, die durch den dritten Parameter des NOTIFY_HANDLER-Makros in der Meldungs Zuordnung identifiziert wird.

## <a name="syntax"></a>Syntax

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parameter

*idCtrl*<br/>
Der Bezeichner des Steuer Elements, das die Nachricht sendet.

*pnmh*<br/>
Adresse einer [NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr) -Struktur, die den Benachrichtigungs Code und zusätzliche Informationen enthält. Bei einigen Benachrichtigungs Meldungen verweist dieser Parameter auf eine größere Struktur, die über `NMHDR` die Struktur als erstes Element verfügt.

*bHandled*<br/>
In der Meldungs Zuordnung wird *bbehandelte* auf true festgelegt, bevor *notifyhandler* aufgerufen wird. Wenn *notifyhandler* die Nachricht nicht vollständig verarbeitet, sollte *bbehandelte* auf **false** festgelegt werden, um anzugeben, dass die Nachricht weiterverarbeitet werden muss.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung. 0, wenn erfolgreich.

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung dieses Nachrichten Handlers in einer Meldungs Zuordnung finden Sie unter [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)<br/>
[Meldungszuordnungen](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
