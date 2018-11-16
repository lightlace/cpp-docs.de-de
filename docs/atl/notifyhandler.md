---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NotifyHandler
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 72c8fa3a0773a67c32a0652eb048885564a734be
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694607"
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
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
