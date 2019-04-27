---
title: Globale Funktionen für Ereignis behandeln
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: bb109c63b497420ad6e797cd8e0b366ce4dc0475
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276341"
---
# <a name="event-handling-global-functions"></a>Globale Funktionen für Ereignis behandeln

Diese Funktion bietet es sich um einen Ereignishandler.

> [!IMPORTANT]
>  Die Funktion, die in der folgenden Tabelle aufgeführten kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Wartet auf ein Objekt, das signalisiert werden, Unterdessen fenstermeldungen nach Bedarf.|

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop

Wartet auf die Signalisierung des Objekts und leitet unterdessen Fenstermeldungen nach Bedarf weiter.

> [!IMPORTANT]
>  Diese Funktion kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Parameter

*hEvent*<br/>
[in] Das Handle des Objekts, die gewartet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Objekt signalisiert wird.

### <a name="remarks"></a>Hinweise

Dies ist nützlich, wenn Sie warten, bis ein Ereignis eines Objekts auftreten, und es geschieht benachrichtigt werden möchten, aber Windows-Meldungen während des Wartens verteilt werden können.

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)
