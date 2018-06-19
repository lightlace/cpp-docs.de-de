---
title: COleBusyDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs:
- C++
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b061d2cc31a67c2e6059abeaadb6062b77cacb88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374369"
---
# <a name="colebusydialog-class"></a>COleBusyDialog-Klasse
Wird für die OLE-Dialogfelder "Server antwortet nicht" oder "Server ausgelastet" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Erstellt ein `COleBusyDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|Zeigt das Dialogfeld "OLE-Server ausgelastet" an.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Bestimmt die Auswahl im Dialogfeld an.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|Struktur des Typs **OLEUIBUSY** , steuert das Verhalten des Dialogfelds.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleBusyDialog` sollen diese Dialogfelder aufzurufen. Nach einem `COleBusyDialog` -Objekts können Sie mithilfe der [M_bz](#m_bz) Struktur initialisiert werden, die Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_bz` Struktur ist vom Typ **OLEUIBUSY**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Memberfunktion.  
  
> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.  
  
 Weitere Informationen finden Sie unter der [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Struktur im Windows SDK.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="colebusydialog"></a>  COleBusyDialog::COleBusyDialog  
 Diese Funktion nur bildet eine `COleBusyDialog` Objekt.  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *htaskBusy*  
 Handle für den Server-Aufgabe, die stark ausgelastet ist.  
  
 *bNotResponding*  
 Wenn **"true"**, rufen Sie das Dialogfeld nicht mehr reagiert anstatt das Dialogfeld Server ausgelastet. Klicken Sie im Dialogfeld reagiert nicht mit der Wortlaut weicht etwas mit dem Wortlaut in das Dialogfeld "Server ausgelastet" und die Schaltfläche "Abbrechen" ist deaktiviert.  
  
 `dwFlags`  
 Erstellen Sie das Flag. Kann 0 (null) oder mehrere der folgenden Werte mit dem bitweisen OR-Operator kombiniert enthalten:  
  
- **BZ_DISABLECANCELBUTTON** deaktivieren Sie die Schaltfläche "Abbrechen", beim Aufrufen des Dialogfelds "".  
  
- **BZ_DISABLESWITCHTOBUTTON** deaktivieren Sie die Schaltfläche "Wechseln zu" beim Aufrufen des Dialogfelds "".  
  
- **BZ_DISABLERETRYBUTTON** deaktivieren Sie die Schaltfläche "Wiederholen", beim Aufrufen des Dialogfelds "".  
  
 `pParentWnd`  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster eines jedoch stattdessen das Dialogfeld auf das Hauptanwendungsfenster festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen [DoModal](#domodal).  
  
 Weitere Informationen finden Sie unter der [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Struktur im Windows SDK.  
  
##  <a name="domodal"></a>  COleBusyDialog::DoModal  
 Mit dieser Funktion wird zum Anzeigen des Dialogfelds OLE-Server ausgelastet "oder" Server antwortet nicht.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** wird das Dialogfeld erfolgreich angezeigt.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) Funktion im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_bz](#m_bz) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder der Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.  
  
##  <a name="getselectiontype"></a>  COleBusyDialog::GetSelectionType  
 Mit dieser Funktion wird zum Abrufen des Auswahltyps, der vom Benutzer im Dialogfeld "Server ausgelastet" ausgewählt wurde.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Typ der Auswahl.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp Werte werden angegeben, indem die **Auswahl** Enumerationstyp deklariert wird, der `COleBusyDialog` Klasse.  
  
```  
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```  
  
 Führen Sie die kurze Beschreibungen der folgenden Werte:  
  
- **COleBusyDialog::switchTo** wechseln zu gedrückt wurde.  
  
- **COleBusyDialog::retry** Wiederholung gedrückt wurde.  
  
- **COleBusyDialog::callUnblocked** Aufruf zum Aktivieren des Servers ist jetzt entsperrt.  
  
##  <a name="m_bz"></a>  COleBusyDialog::m_bz  
 Struktur des Typs **OLEUIBUSY** zum Steuern des Verhaltens im Dialogfeld "Server ausgelastet" verwendet.  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
