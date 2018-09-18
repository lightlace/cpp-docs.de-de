---
title: CommandHandler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CommandHandler
dev_langs:
- C++
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5a4d4c359fb4a90bfd25801f7c73f5bc4d7d501
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019470"
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

*wNotifyCode schalten*<br/>
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
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)

