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
ms.openlocfilehash: 4799d0b9c36ade8b1e203ca106605db75752b02f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752814"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` die Funktion wird durch den dritten Parameter des COMMAND_HANDLER Makros in der meldungszuordnung identifiziert werden.

## <a name="syntax"></a>Syntax

```  
LRESULT CommandHandler(
    WORD wNotifyCode,  
    WORD wID,  
    HWND hWndCtl,  
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parameter

*wNotifyCode schalten*  
Der Benachrichtigungscode.

*wID*  
Der Bezeichner der dem Menüelement-Steuerelement oder Accelerator.

*hWndCtl*  
Ein Handle für ein Window-Steuerelement.

*bHandled*  
Die Zuordnung Nachrichtensätze *bHandled* auf "true", bevor Sie `CommandHandler` aufgerufen wird. Wenn `CommandHandler` ist nicht vollständig verarbeitet die Nachricht sollte *bHandled* auf "false", um anzugeben, die Nachricht noch weitere Verarbeitung erforderlich.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung. Bei Erfolg 0.

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung dieser Nachrichtenhandler in einer meldungszuordnung, finden Sie unter [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)   
[Meldungszuordnungen](../atl/message-maps-atl.md)   
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)

