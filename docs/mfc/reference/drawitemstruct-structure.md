---
title: DRAWITEMSTRUCT-Struktur
ms.date: 11/04/2016
f1_keywords:
- DRAWITEMSTRUCT
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
ms.openlocfilehash: 9c5bfc12bd371761682102dad6d7bcb75ef44151
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624431"
---
# <a name="drawitemstruct-structure"></a>DRAWITEMSTRUCT-Struktur

Die `DRAWITEMSTRUCT` -Struktur stellt Informationen zur Verfügung, über die das besitzende Fenster verfügen muss, um zu bestimmen, wie ein vom Besitzer gezeichnetes Steuerelement oder Menüelement gezeichnet werden muss.

## <a name="syntax"></a>Syntax

```
typedef struct tagDRAWITEMSTRUCT {
    UINT CtlType;
    UINT CtlID;
    UINT itemID;
    UINT itemAction;
    UINT itemState;
    HWND hwndItem;
    HDC hDC;
    RECT rcItem;
    DWORD itemData;
} DRAWITEMSTRUCT;
```

#### <a name="parameters"></a>Parameter

*CtlType*<br/>
Der Steuerelementtyp. Folgende Werte sind für Steuerelementtypen gültig:

- ODT_BUTTON Ownerdrawn-Schaltfläche

- ODT_COMBOBOX Ownerdrawn-Kombinationsfeld

- Odt_combobox Ownerdrawn-Listenfeld

- ODT_MENU Besitzer gezeichnetes Menü

- ODT_LISTVIEW Listenansicht-Steuerelement

- ODT_STATIC Besitzer gezeichnetes statisches Steuerelement

- ODT_TAB Registerkarten-Steuerelement

*CtlID*<br/>
Die Steuerelement-ID für ein Kombinationsfeld, ein Listenfeld oder eine Schaltfläche. Dieser Member wird nicht für ein Menü verwendet.

*Element-ID*<br/>
Die Menüelement-ID für ein Menü oder der Index des Elements in einem Listenfeld oder Kombinationsfeld. Für einen leeren Listenfeld oder Kombinationsfeld hat dieser Member einen negativen Wert, der der Anwendung ermöglicht, nur das Fokusrechteck an den angegebenen Koordinaten zu zeichnen ist die `rcItem` Member, obwohl im Steuerelement keine Elemente vorhanden sind. Dem Benutzer kann auf diese Weise angezeigt werden, ob das Listenfeld oder Kombinationsfeld den Eingabefokus besitzt. Die Einstellung der Bits in der `itemAction` Element bestimmt, ob das Rechteck so gezeichnet werden soll, als ob das Listenfeld oder Kombinationsfeld den Eingabefokus besitzt.

*itemAction*<br/>
Definiert die erforderliche Zeichenaktion. Dabei handelt es sich um mindestens eins der folgenden Bits:

- ODA_DRAWENTIRE dieses Bit festgelegt ist, wenn das gesamte Steuerelement gezeichnet werden muss.

- ODA_FOCUS dieses Bit festgelegt ist, wenn das Steuerelement erhält oder Eingabefokus verliert. Die `itemState` Member sollte aktiviert sein, um festzustellen, ob das Steuerelement den Fokus besitzt.

- ODA_SELECT dieses Bit festgelegt ist, wenn nur der Auswahlstatus geändert hat. Die `itemState` Member sollte aktiviert sein, um zu bestimmen, die neue Auswahl den.

*itemState*<br/>
Gibt den visuellen Status des Elements nach dem Abschluss der aktuellen Zeichenaktion an. Wenn ein Menüelement ist dargestellt werden muss, wird das Statusflag, also ODS_GRAYED festgelegt werden. Diese Statusflags sind verfügbar:

- ODS_CHECKED dieses Bit festgelegt ist, wenn das Menüelement aktiviert werden. Dieses Bit wird nur in Menüs verwendet.

- ODS_DISABLED dieses Bit festgelegt ist, wenn das Element als deaktiviert gezeichnet werden.

- ODS_FOCUS dieses Bit ist festgelegt, wenn das Element den Eingabefokus besitzt.

- ODS_GRAYED dieses Bit festgelegt ist, wenn das Element dargestellt werden muss. Dieses Bit wird nur in Menüs verwendet.

- ODS_SELECTED dieses Bit festgelegt ist, wenn der Status des Artikels ausgewählt ist.

- ODS_COMBOBOXEDIT das Zeichnen findet im Auswahlfeld (Bearbeiten-Steuerelement) eines von einem Besitzer gezeichneten Kombinationsfelds statt.

- ODS_DEFAULT das Element ist das Standardelement.

*hwndItem*<br/>
Gibt das Fensterhandle des Steuerelements für Kombinationsfelder, Listenfelder und Schaltflächen an. Gibt das Handle des Menüs (HMENU), das das Element für Menüs enthält.

*hDC*<br/>
Bezeichnet einen Gerätekontext. Dieser Gerätekontext muss beim Ausführen von Zeichenvorgängen im Steuerelement verwendet werden.

*rcItem*<br/>
Ein Rechteck, in den Gerätekontext, die gemäß der *hDC* Element, das die Grenzen des zu zeichnenden Steuerelements definiert. Windows beschneidet automatisch alles, was der Besitzer im Gerätekontext für Kombinationsfelder, Listenfelder und Schaltflächen zeichnet, Menüelemente werden jedoch nicht beschnitten. Beim Zeichnen von Menüelementen muss der Besitzer nicht außerhalb der Grenzen des vom definierten Rechtecks zeichnen die `rcItem` Member.

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

## <a name="remarks"></a>Hinweise

Das besitzende Fenster des Steuerelements oder Menüelements Elements Besitzer gezeichnetes erhält einen Zeiger auf diese Struktur als die *lParam* -Parameter der Nachricht WM_DRAWITEM.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

