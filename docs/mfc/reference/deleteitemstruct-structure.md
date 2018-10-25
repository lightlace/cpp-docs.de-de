---
title: DELETEITEMSTRUCT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9061205bdf3697e492b846d160a5b4dd2d154bb9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065017"
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT-Struktur

Die `DELETEITEMSTRUCT` Struktur beschrieben wird, ein gelöschtes Ownerdrawn-Listenfeld oder Kombinationsfeld Element.

## <a name="syntax"></a>Syntax

```
typedef struct tagDELETEITEMSTRUCT { /* ditms */
    UINT CtlType;
    UINT CtlID;
    UINT itemID;
    HWND hwndItem;
    UINT itemData;
} DELETEITEMSTRUCT;
```

#### <a name="parameters"></a>Parameter

*CtlType*<br/>
Gibt an, odt_combobox (ein Ownerdrawn-Listenfeld) oder ODT_COMBOBOX (ein Ownerdrawn-Kombinationsfeld).

*CtlID*<br/>
Gibt den Bezeichner der im Listenfeld oder Kombinationsfeld.

*Element-ID*<br/>
Gibt den Index des Elements in das Listenfeld oder Kombinationsfeld, die entfernt an.

*hwndItem*<br/>
Bezeichnet das Steuerelement.

*itemData*<br/>
Gibt anwendungsspezifische Daten für das Element an. Dieser Wert wird übergeben, auf das Steuerelement in der *lParam* -Parameter der Nachricht, die das Element, das im Listenfeld oder Kombinationsfeld hinzufügt.

## <a name="remarks"></a>Hinweise

Wenn ein Element entfernt wird, aus dem Listenfeld oder Kombinationsfeld oder wenn das Listenfeld oder Kombinationsfeld zerstört wird, sendet Windows die WM_DELETEITEM-Nachricht an den Besitzer für jede gelöschte Element. Die *lParam* -Parameter der Nachricht enthält einen Zeiger auf diese Struktur.

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)

