---
title: MEASUREITEMSTRUCT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MEASUREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- MEASUREITEMSTRUCT structure [MFC]
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db24d772e2f007b3350443ae6bc84f97cac34e76
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397766"
---
# <a name="measureitemstruct-structure"></a>MEASUREITEMSTRUCT-Struktur

Die `MEASUREITEMSTRUCT` Struktur informiert Windows der Dimensionen eines Ownerdrawn-Steuerelements oder Menüelements-Elements.

## <a name="syntax"></a>Syntax

```
typedef struct tagMEASUREITEMSTRUCT {
    UINT CtlType;
    UINT CtlID;
    UINT itemID;
    UINT itemWidth;
    UINT itemHeight;
    DWORD itemData
} MEASUREITEMSTRUCT;
```

#### <a name="parameters"></a>Parameter

*CtlType*<br/>
Enthält den Steuerelementtyp. Folgende Werte sind für Steuerelementtypen gültig:

- ODT_COMBOBOX Ownerdrawn-Kombinationsfeld

- Odt_combobox Ownerdrawn-Listenfeld

- ODT_MENU Ownerdrawn-Menü

*CtlID*<br/>
Enthält die Steuerelement-ID für ein Kombinationsfeld, Listenfeld oder Schaltfläche. Dieser Member wird nicht für ein Menü verwendet.

*Element-ID*<br/>
Die Menüelement-ID für ein Menü oder die Listenelement Feld ID für ein variabler Höhe Kombinationsfeld oder Listenfeld enthält. Dieser Member wird nicht für eine feste Höhe Kombinationsfeld oder Listenfeld oder für eine Schaltfläche verwendet.

*itemWidth*<br/>
Gibt die Breite eines Menüelements. Der Besitzer des Menüelements Ownerdrawn-muss dieses Element ausfüllen, bevor sie aus der Nachricht zurückgibt.

*itemHeight*<br/>
Gibt die Höhe eines einzelnen Elements in einem Listenfeld oder einem Menü an. Vor dem Zurückgeben aus der Nachricht, der Besitzer des im Ownerdrawn-Kombinationsfeld, muss dieses Element im Listenfeld oder Menüelement ausfüllen. Die maximale Höhe des Listenfelds ist 255.

*itemData*<br/>
Für ein Kombinationsfeld oder Listenfeld enthält dieser Member den Wert, der dem Listenfeld von einer der folgenden Methoden übergeben wurde:

- [CComboBox:: AddString](../../mfc/reference/ccombobox-class.md#addstring)

- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)

- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)

- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)

Für ein Menü enthält dieser Member den Wert, der dem Menü durch eine der folgenden Methoden übergeben wurde:

- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)

- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)

- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)

Dadurch wird Windows, um die Benutzerinteraktion mit dem Steuerelement ordnungsgemäß zu verarbeiten. Fehler beim Ausfüllen der entsprechenden Elemente in der `MEASUREITEMSTRUCT` Struktur führt dazu, dass eine ungültige Operation des Steuerelements.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

