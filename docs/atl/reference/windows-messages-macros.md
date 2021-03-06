---
title: Windows-Meldungen-Makros
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: 7bb5e2fa265c3a5dcabcc16d8343d5b86a4aaf42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275924"
---
# <a name="windows-messages-macros"></a>Windows-Meldungen-Makros

Dieses Makro leitet Windows-Meldungen.

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|Verwenden Sie eine Nachricht empfangen, die von einem Fenster in ein anderes Fenster zur Verarbeitung weitergeleitet.|

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG

Dieses Makro leitet eine Nachricht von einem Fenster in ein anderes Fenster für die Verarbeitung empfangen.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Nachricht verarbeitet wurde, NULL, wenn nicht.

### <a name="remarks"></a>Hinweise

Verwenden Sie WM_FORWARDMSG, um eine Nachricht empfangen, die von einem Fenster in ein anderes Fenster für die Verarbeitung weiterzuleiten. Die lParam- und WPARAM-Parameter werden wie folgt verwendet:

|Parameter|Verwendung|
|---------------|-----------|
|WPARAM|Daten, die vom Benutzer definiert werden.|
|LPARAM|Ein Zeiger auf eine `MSG` Struktur, die Informationen zu einer Meldung enthält.|

### <a name="example"></a>Beispiel

Im folgenden Beispiel `m_hWndOther` stellt dar, das andere Fenster, das diese Nachricht empfangen hat.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
