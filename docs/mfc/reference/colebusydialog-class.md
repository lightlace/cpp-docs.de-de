---
title: Klasse COleBusyDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleBusyDialog
dev_langs:
- C++
helpviewer_keywords:
- Server Not Responding dialog box
- Server Busy dialog box
- COleBusyDialog class
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0c3ed264cdb83bc97337f13279a20f26b21d454b
ms.lasthandoff: 02/24/2017

---
# <a name="colebusydialog-class"></a>COleBusyDialog-Klasse
Wird für die OLE-Dialogfelder "Server antwortet nicht" oder "Server ausgelastet" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Erstellt ein `COleBusyDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE-Server ausgelastet.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Bestimmt die Auswahl im Dialogfeld.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|Struktur des Typs **OLEUIBUSY** , steuert das Verhalten des Dialogfelds.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleBusyDialog` beim Aufrufen dieser Dialogfelder aufgerufen werden soll. Nach einer `COleBusyDialog` -Objekts, können Sie die [M_bz](#m_bz) Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_bz` Struktur ist vom Typ **OLEUIBUSY**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Member-Funktion.  
  
> [!NOTE]
>  Diese Klasse wird von Anwendung Container vom Assistenten generierten Code verwendet.  
  
 Weitere Informationen finden Sie unter der [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="a-namecolebusydialoga--colebusydialogcolebusydialog"></a><a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog  
 Nur diese Funktion erstellt ein `COleBusyDialog` Objekt.  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *htaskBusy*  
 Handle für die Serveraufgabe, die ausgelastet ist.  
  
 *bNotResponding*  
 Wenn **TRUE**, rufen Sie das Dialogfeld nicht reagiert. anstatt das Dialogfeld Server ausgelastet. Im Dialogfeld reagiert nicht mit der Wortlaut unterscheidet die Formulierung im Dialogfeld "Server ausgelastet" und "Abbrechen"-Schaltfläche wird deaktiviert.  
  
 `dwFlags`  
 Erstellen Sie das Flag. Kann&0; (null) oder mehrere der folgenden Werte mit dem bitweisen OR-Operator kombiniert enthalten:  
  
- **BZ_DISABLECANCELBUTTON** deaktivieren Sie die Schaltfläche "Abbrechen", beim Aufrufen des Dialogfelds.  
  
- **BZ_DISABLESWITCHTOBUTTON** deaktivieren Sie die Schaltfläche "Wechseln zu" beim Aufrufen des Dialogfelds.  
  
- **BZ_DISABLERETRYBUTTON** "Wiederholen" deaktivieren, wenn das Dialogfeld aufrufen.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, das übergeordnete Fenster des Dialog-Objekts zum Hauptfenster der Anwendung festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen Sie [DoModal](#domodal).  
  
 Weitere Informationen finden Sie unter der [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedomodala--colebusydialogdomodal"></a><a name="domodal"></a>COleBusyDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld OLE-Server ausgelastet "oder" Server antwortet nicht anzeigen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** , wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_bz](#m_bz) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.  
  
##  <a name="a-namegetselectiontypea--colebusydialoggetselectiontype"></a><a name="getselectiontype"></a>COleBusyDialog::GetSelectionType  
 Rufen Sie diese Funktion, um den Typ der Auswahl der Benutzer im Dialogfeld "Server ausgelastet" zu erhalten.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Typ der ausgewählten Optionen.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp Werte werden angegeben, indem die **Auswahl** Enumerationstyp deklariert wird, der `COleBusyDialog` Klasse.  
  
 `enum Selection`  
  
 `{`  
  
 `switchTo,`  
  
 `retry,`  
  
 `callUnblocked`  
  
 `};`  
  
 Führen Sie die kurze Beschreibungen der folgenden Werte:  
  
- **COleBusyDialog::switchTo** wechseln zu gedrückt wurde.  
  
- **COleBusyDialog::retry** Wiederholung gedrückt wurde.  
  
- **COleBusyDialog::callUnblocked** Aufruf an den Server zu aktivieren, ist jetzt aufgehoben.  
  
##  <a name="a-namembza--colebusydialogmbz"></a><a name="m_bz"></a>COleBusyDialog::m_bz  
 Struktur des Typs **OLEUIBUSY** zum Steuern des Verhaltens im Dialogfeld "Server ausgelastet" verwendet.  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)

