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
ms.openlocfilehash: ff4596a52170d0c6d197a0bda431963b5f0e9344
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120933"
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
 *CtlType*  
 Der Steuerelementtyp. Folgende Werte sind für Steuerelementtypen gültig:  
  
- ODT_BUTTON Ownerdrawn-Schaltfläche  
  
- ODT_COMBOBOX Ownerdrawn-Kombinationsfeld  
  
- Odt_combobox Besitzer gezeichnetes Listenfeld  
  
- ODT_MENU Besitzer gezeichnetes Menü  
  
- ODT_LISTVIEW Listenansicht-Steuerelement  
  
- ODT_STATIC Besitzer gezeichnetes statisches Steuerelement  
  
- ODT_TAB Registerkarten-Steuerelement  
  
 *CtlID*  
 Die Steuerelement-ID für ein Kombinationsfeld, ein Listenfeld oder eine Schaltfläche. Dieser Member wird nicht für ein Menü verwendet.  
  
 *Element-ID*  
 Die Menüelement-ID für ein Menü oder der Index des Elements in einem Listenfeld oder Kombinationsfeld. Für einen leeren Listenfeld oder Kombinationsfeld wird bei diesem Member einen negativen Wert, wodurch die Anwendung nur das Fokusrechteck an den angegebenen Koordinaten zu zeichnen die `rcItem` Member, obwohl keine Elemente im Steuerelement vorhanden sind. Dem Benutzer kann auf diese Weise angezeigt werden, ob das Listenfeld oder Kombinationsfeld den Eingabefokus besitzt. Die Einstellung der Bits in der `itemAction` Element bestimmt, ob das Rechteck gezeichnet werden, als ob das Listenfeld oder Kombinationsfeld den Eingabefokus besitzt.  
  
 *ItemAction*  
 Definiert die erforderliche Zeichenaktion. Dabei handelt es sich um mindestens eins der folgenden Bits:  
  
- ODA_DRAWENTIRE dieses Bit festgelegt ist, wenn das gesamte Steuerelement gezeichnet werden muss.  
  
- ODA_FOCUS dieses Bit festgelegt ist, wenn das Steuerelement erhält oder Eingabefokus verliert. Die `itemState` Member sollten aktiviert sein, um zu bestimmen, ob das Steuerelement den Fokus besitzt.  
  
- ODA_SELECT dieses Bit festgelegt ist, wenn nur der Auswahlstatus geändert wurde. Die `itemState` Member sollte aktiviert sein, um die neue Auswahlstatus zu bestimmen.  
  
 *itemState*  
 Gibt den visuellen Status des Elements nach dem Abschluss der aktuellen Zeichenaktion an. Ist ein Menüelement abgeblendet dargestellt werden, wird das Statusflag, also ODS_GRAYED festgelegt werden. Diese Statusflags sind verfügbar:  
  
- ODS_CHECKED dieses Bit festgelegt ist, ist das Menüelement überprüft werden soll. Dieses Bit wird nur in Menüs verwendet.  
  
- ODS_DISABLED dieses Bit festgelegt ist, wenn das Element ist, als deaktiviert gezeichnet werden soll.  
  
- ODS_FOCUS dieses Bit festgelegt ist, wenn das Element den Eingabefokus besitzt.  
  
- ODS_GRAYED dieses Bit festgelegt ist, wenn das Element abgeblendet dargestellt werden. Dieses Bit wird nur in Menüs verwendet.  
  
- ODS_SELECTED dieses Bit festgelegt ist, wenn der Status des Artikels ausgewählt ist.  
  
- ODS_COMBOBOXEDIT das Zeichnen findet im Auswahlfeld (Bearbeiten-Steuerelement) von einem Besitzer gezeichneten Kombinationsfelds statt.  
  
- ODS_DEFAULT das Element ist das Standardelement.  
  
 *hwndItem*  
 Gibt das Fensterhandle des Steuerelements für Kombinationsfelder, Listenfelder und Schaltflächen an. Gibt das Handle des Menüs (HMENU), die das Element für Menüs enthält.  
  
 *hDC*  
 Bezeichnet einen Gerätekontext. Dieser Gerätekontext muss beim Ausführen von Zeichenvorgängen im Steuerelement verwendet werden.  
  
 *rcItem*  
 Ein Rechteck in den Gerätekontext, der gemäß der *hDC* Element, das die Begrenzungen des zu zeichnenden Steuerelements definiert. Windows beschneidet automatisch alles, was der Besitzer im Gerätekontext für Kombinationsfelder, Listenfelder und Schaltflächen zeichnet, Menüelemente werden jedoch nicht beschnitten. Beim Zeichnen von Menüelementen muss der Besitzer nicht außerhalb der Grenzen des Rechtecks definiert durch Zeichnen die `rcItem` Member.  
  
 *itemData*  
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
 Das besitzende Fenster des Steuerelements oder Menüelements Elements Ownerdrawn-empfängt einen Zeiger auf diese Struktur als der *lParam* -Parameter der Nachricht WM_DRAWITEM.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

