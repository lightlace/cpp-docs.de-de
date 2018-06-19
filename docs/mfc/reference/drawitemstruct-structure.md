---
title: DRAWITEMSTRUCT-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DRAWITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdb7daba666e8aaf983eadc77417cad46180e7df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378268"
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
 `CtlType`  
 Der Steuerelementtyp. Folgende Werte sind für Steuerelementtypen gültig:  
  
- **ODT_BUTTON** Vom Besitzer gezeichnete Schaltfläche  
  
- **ODT_COMBOBOX** Vom Besitzer gezeichnetes Kombinationsfeld  
  
- **ODT_COMBOBOX** Vom Besitzer gezeichnetes Listenfeld  
  
- **ODT_MENU** Vom Besitzer gezeichnetes Menü  
  
- **ODT_LISTVIEW** Listenansicht-Steuerelement  
  
- **ODT_STATIC** Vom Besitzer gezeichnetes statisches Steuerelement  
  
- **ODT_TAB** Registerkarten-Steuerelement  
  
 `CtlID`  
 Die Steuerelement-ID für ein Kombinationsfeld, ein Listenfeld oder eine Schaltfläche. Dieser Member wird nicht für ein Menü verwendet.  
  
 `itemID`  
 Die Menüelement-ID für ein Menü oder der Index des Elements in einem Listenfeld oder Kombinationsfeld. Bei einem leeren Listenfeld oder Kombinationsfeld hat dieser Member einen negativen Wert, was es der Anwendung ermöglicht, nur das Fokusrechteck an den im Member **rcItem** angegebenen Koordinaten zu zeichnen, obwohl das Steuerelement keine Elemente enthält. Dem Benutzer kann auf diese Weise angezeigt werden, ob das Listenfeld oder Kombinationsfeld den Eingabefokus besitzt. Die Einstellung der Bits im Member **itemAction** bestimmt, ob das Rechteck so gezeichnet wird, als ob das Listenfeld oder Kombinationsfeld den Eingabefokus hat.  
  
 `itemAction`  
 Definiert die erforderliche Zeichenaktion. Dabei handelt es sich um mindestens eins der folgenden Bits:  
  
- **ODA_DRAWENTIRE** Dieses Bit ist gesetzt, wenn das gesamte Steuerelement gezeichnet werden muss.  
  
- **ODA_FOCUS** Dieses Bit ist gesetzt, wenn das Steuerelement den Eingabefokus erhält oder abgibt. Der Member **itemState** sollte aktiviert sein, um zu bestimmen, ob das Steuerelement den Fokus hat.  
  
- **ODA_SELECT** Dieses Bit wird gesetzt, wenn sich nur der Auswahlstatus geändert hat. Der Member **itemState** sollte aktiviert sein, um zu bestimmen, ob die neue Auswahl den Fokus hat.  
  
 *itemState*  
 Gibt den visuellen Status des Elements nach dem Abschluss der aktuellen Zeichenaktion an. Das heißt, wenn ein Menüelement ausgegraut dargestellt werden soll, ist das Statusflag **ODS_GRAYED** gesetzt. Diese Statusflags sind verfügbar:  
  
- **ODS_CHECKED** Dieses Bit ist gesetzt, wenn das Menüelement aktiviert werden muss. Dieses Bit wird nur in Menüs verwendet.  
  
- **ODS_DISABLED** Dieses Bit ist gesetzt, wenn das Element als deaktiviert gezeichnet werden muss.  
  
- **ODS_FOCUS** Dieses Bit ist gesetzt, wenn das Element den Eingabefokus aufweist.  
  
- **ODS_GRAYED** Dieses Bit ist gesetzt, wenn das Element ausgegraut dargestellt werden muss. Dieses Bit wird nur in Menüs verwendet.  
  
- **ODS_SELECTED** Dieses Bit ist gesetzt, wenn der Status des Elements „aktiviert“ ist.  
  
- **ODS_COMBOBOXEDIT** Das Zeichnen findet im Auswahlfeld (Bearbeiten-Steuerelement) eines von einem Besitzer gezeichneten Kombinationsfelds statt.  
  
- **ODS_DEFAULT** Das Element ist das Standardelement.  
  
 `hwndItem`  
 Gibt das Fensterhandle des Steuerelements für Kombinationsfelder, Listenfelder und Schaltflächen an. Gibt das Handle des Menüs (`HMENU`) an, das das Element für Menüs enthält.  
  
 `hDC`  
 Bezeichnet einen Gerätekontext. Dieser Gerätekontext muss beim Ausführen von Zeichenvorgängen im Steuerelement verwendet werden.  
  
 *rcItem*  
 Ein Rechteck in dem vom `hDC` -Member angegebenen Gerätekontext, das die Grenzen des zu zeichnenden Steuerelements definiert. Windows beschneidet automatisch alles, was der Besitzer im Gerätekontext für Kombinationsfelder, Listenfelder und Schaltflächen zeichnet, Menüelemente werden jedoch nicht beschnitten. Beim Zeichnen von Menüelementen darf der Besitzer nicht außerhalb der Grenzen des vom Member **rcItem** definierten Rechtecks zeichnen.  
  
 `itemData`  
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
 Das besitzende Fenster des vom Besitzer gezeichneten Steuerelements oder Menüelements erhält einen Zeiger auf diese Struktur als `lParam` -Parameter der `WM_DRAWITEM` -Nachricht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

