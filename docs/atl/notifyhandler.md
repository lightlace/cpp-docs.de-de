---
title: NotifyHandler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f11c698b0f89e0584b673a112da10e82250cf5c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035772"
---
# <a name="notifyhandler"></a>NotifyHandler

Der Name der Funktion durch den dritten Parameter des NOTIFY_HANDLER Makros in der meldungszuordnung identifiziert.

## <a name="syntax"></a>Syntax

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parameter

*idCtrl*<br/>
Der Bezeichner des Steuerelements, das Sie die Nachricht gesendet.

*pnmh*<br/>
Adresse von einem [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) Struktur, die der Benachrichtigungscode und zusätzliche Informationen enthält. Für einige Benachrichtigungen, zeigt dieser Parameter auf einer größeren Struktur, die die `NMHDR` Struktur wie des ersten Elements.

*bHandled*<br/>
Die Zuordnung Nachrichtensätze *bHandled* auf "true", bevor Sie *NotifyHandler* aufgerufen wird. Wenn *NotifyHandler* ist nicht vollständig verarbeitet die Nachricht sollte *bHandled* zu **"false"** an, dass noch weitere Verarbeitung die Nachricht erforderlich.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Nachrichtenverarbeitung. Bei Erfolg 0.

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung dieser Nachrichtenhandler in einer meldungszuordnung, finden Sie unter [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)<br/>
[Meldungszuordnungen](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)
