---
title: MessageHandler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a2434257290c673ca4e18be2e5ec70877e72e67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039087"
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
