---
title: COccManager Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
dev_langs: C++
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d27b1d018b427360105f1e294f2d0385ce18f5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="coccmanager-class"></a>COccManager-Klasse
Verwaltet unterschiedliche benutzerdefinierte ControlSites. Wird von `COleControlContainer` - und `COleControlSite` -Objekten implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COccManager::CreateContainer](#createcontainer)|Erstellt eine **COleContainer** Objekt.|  
|[COccManager::CreateDlgControls](#createdlgcontrols)|ActiveX-Steuerelemente, die durch den zugehörigen gehostet erstellt `COleContainer` Objekt.|  
|[COccManager::CreateSite](#createsite)|Erstellt ein `COleClientSite`-Objekt.|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|Ruft den Code für die Standardschaltfläche ab.|  
|[COccManager::IsDialogMessage](#isdialogmessage)|Das Ziel einer Nachricht Dialogfeld bestimmt.|  
|[COccManager::IsLabelControl](#islabelcontrol)|Bestimmt, ob das angegebene Steuerelement ein Bezeichnungsfeld-Steuerelement ist.|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Bestimmt, ob der aktuelle mnemonischen Zeichen das mnemonische Zeichen des angegebenen Steuerelements übereinstimmt.|  
|[COccManager::OnEvent](#onevent)|Versucht, das angegebene Ereignis zu behandeln.|  
|[COccManager::PostCreateDialog](#postcreatedialog)|Gibt während der Erstellung des Dialogfeld reservierten Ressourcen frei.|  
|[COccManager::PreCreateDialog](#precreatedialog)|Verarbeitet eine Dialogfeldvorlage für ActiveX-Steuerelemente.|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|Schaltet den Standardzustand des angegebenen Steuerelements.|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Trennt alle vorhandenen ActiveX-Steuerelemente aus allgemeinen Steuerelementen in der angegebenen Dialogfeldvorlage.|  
  
## <a name="remarks"></a>Hinweise  
 Die Basisklasse **CNoTrackObject**, ist eine nicht dokumentierte Basisklasse (im Verzeichnis AFXTLS. H). Abgeleitete Klassen von für die Verwendung von MFC-Framework konzipiert, die **CNoTrackObject** Klasse speicherverlusterkennung ausgeschlossen werden. Es wird nicht empfohlen, dass Sie direkt von ableiten **CNoTrackObject**.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxocc.h  
  
##  <a name="createcontainer"></a>COccManager::CreateContainer  
 Vom Framework aufgerufen wird, einen Steuerelementcontainer zu erstellen.  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Window-Objekt, das die benutzerdefinierte Website Container zugewiesen sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den neu erstellten Container; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Erstellen von benutzerdefinierten Websites finden Sie unter [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).  
  
##  <a name="createdlgcontrols"></a>COccManager::CreateDlgControls  
 Mit dieser Funktion wird zum Erstellen von ActiveX-Steuerelemente, die gemäß der `pOccDialogInfo` Parameter.  
  
```  
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    LPCTSTR lpszResourceName,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

 
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    void* lpResource,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndParent*  
 Ein Zeiger auf das übergeordnete Element des dem Dialogfeldobjekt.  
  
 `lpszResourceName`  
 Der Name der Ressource erstellt wird.  
  
 `pOccDialogInfo`  
 Ein Zeiger auf die Dialogfeldvorlage verwendet, um das Dialogfeldobjekt zu erstellen.  
  
 `lpResource`  
 Ein Zeiger auf eine Ressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement erfolgreich erstellt wurde; andernfalls 0 (null).  
  
##  <a name="createsite"></a>COccManager::CreateSite  
 Wird aufgerufen, durch das Framework zum Erstellen einer Steuerelement-Website, die vom Container verweist gehostet `pCtrlCont`.  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Parameter  
 `pCtrlCont`  
 Ein Zeiger auf dem Steuerelementcontainer hostet die Website des neuen Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Site für das neu erstellte Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zur Erstellung eines benutzerdefinierten Steuerelements-Website, unter Verwendung Ihrer [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-abgeleitete Klasse.  
  
 Jedes Steuerelementcontainer kann mehrere Websites hosten. Erstellen Sie zusätzliche Websites mit mehreren Aufrufen an `CreateSite`.  
  
##  <a name="getdefbtncode"></a>COccManager::GetDefBtnCode  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Steuerelement eine Standardschaltfläche ist.  
  
```  
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Das Window-Objekt, das das Schaltflächen-Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- **DLGC_DEFPUSHBUTTON** Steuerelement ist die Standardschaltfläche im Dialogfeld "".  
  
- **DLGC_UNDEFPUSHBUTTON** Steuerelement ist nicht die Standardschaltfläche im Dialogfeld "".  
  
- **0** -Steuerelement ist nicht mit einer Schaltfläche.  
  
##  <a name="isdialogmessage"></a>COccManager::IsDialogMessage  
 Wird aufgerufen, durch das Framework, um festzustellen, ob eine Nachricht im angegebenen Dialogfeld dient, und wenn dies der Fall, die Nachricht verarbeitet.  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndDlg*  
 Ein Zeiger auf das Dialogfeld vorgesehenes Ziel der Nachricht.  
  
 `lpMsg`  
 Ein Zeiger auf eine `MSG` Struktur mit der Nachricht überprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten des `IsDialogMessage` für tastaturmeldungen überprüfen und konvertieren sie in der Auswahl des entsprechenden Dialogfelds wird. Die TAB-Taste, wenn gedrückt wird, wählt z. B. das nächste Steuerelement bzw. jede Gruppe von Steuerelementen.  
  
 Überschreiben Sie diese Funktion, um benutzerdefiniertes Verhalten für Nachrichten im Dialog "angegebene" bereitzustellen.  
  
##  <a name="islabelcontrol"></a>COccManager::IsLabelControl  
 Rufen Sie diese Funktion, um zu bestimmen, ob das angegebene Steuerelement ein Bezeichnungsfeld-Steuerelement ist.  
  
```  
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);  
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement eine Bezeichnung ist; andernfalls 0 (null)  
  
### <a name="remarks"></a>Hinweise  
 Ein Bezeichnungsfeld-Steuerelement ist verhält sich wie eine Bezeichnung für den jeweiligen weiter in der Reihenfolge aufweist.  
  
##  <a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic  
 Rufen Sie diese Funktion, um zu bestimmen, ob das aktuelle mnemonische Zeichen, die vom Steuerelement dargestellt entspricht.  
  
```  
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,  
    LPMSG lpMsg);

 
static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement enthält.  
  
 `lpMsg`  
 Ein Zeiger auf die Nachricht, enthält das mnemonische Zeichen übereinstimmen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die mnemonischen Codes des Steuerelements entspricht; andernfalls 0 (null)  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onevent"></a>COccManager::OnEvent  
 Vom Framework aufgerufen, das angegebene Ereignis zu behandeln.  
  
```  
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,  
    UINT idCtrl,  
    AFX_EVENT* pEvent,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pCmdTarget*  
 Ein Zeiger auf die `CCmdTarget` Objekt versucht wird, das Ereignis behandeln  
  
 `idCtrl`  
 Die Ressourcen-ID des Steuerelements.  
  
 `pEvent`  
 Das Ereignis behandelt wird.  
  
 `pHandlerInfo`  
 Wenn dies nicht der **NULL**, `OnEvent` füllt die **pTarget** und **Pmf** Mitglied der **AFX_CMDHANDLERINFO** Struktur anstelle von Verteilen den Befehl. Dieser Parameter muss in der Regel **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Ereignis behandelt wurde, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Anpassen der Standardprozess für die Ereignisbehandlung an.  
  
##  <a name="precreatedialog"></a>COccManager::PreCreateDialog  
 Wird aufgerufen, durch das Framework eine Dialogfeldvorlage für ActiveX-Steuerelemente vor dem Erstellen des tatsächlichen Dialogfelds zu verarbeiten.  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `pOccDialogInfo`  
 Ein **_AFX_OCC_DIALOG_INFO** Struktur, die Informationen auf der Dialogfeldvorlage und alle ActiveX-Steuerelemente gehostet werden, indem Sie das Dialogfeld "enthält.  
  
 *pOrigTemplate*  
 Ein Zeiger auf die Dialogfeldvorlage beim Erstellen des Dialogfelds "" verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Dialogfeld Vorlagenstruktur verwendet, um das Dialogfeld zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten aufruft `SplitDialogTemplate`, bestimmen Sie, wenn es-ActiveX gibt-Steuerelemente vorhanden, und gibt anschließend die resultierenden Dialogfeldvorlage zurück.  
  
 Überschreiben Sie diese Funktion, um den Prozess der Erstellung ein Dialogfeld, das hosting von ActiveX-Steuerelementen anpassen.  
  
##  <a name="postcreatedialog"></a>COccManager::PostCreateDialog  
 Vom Framework aufgerufen, für die Dialogfeldvorlage belegten Arbeitsspeicher freizugeben.  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pOccDialogInfo`  
 Ein **_AFX_OCC_DIALOG_INFO** Struktur, die Informationen auf der Dialogfeldvorlage und alle ActiveX-Steuerelemente gehostet werden, indem Sie das Dialogfeld "enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Speicherplatz belegt wurde durch einen Aufruf von `SplitDialogTemplate`, und für alle gehosteten ActiveX-Steuerelemente im Dialogfeld verwendet wurde.  
  
 Überschreiben Sie diese Funktion, um den Prozess der alle vom Dialogfeld Box-Objekt verwendeten Ressourcen bereinigen anzupassen.  
  
##  <a name="setdefaultbutton"></a>COccManager::SetDefaultButton  
 Rufen Sie diese Funktion, um das Steuerelement als Standardschaltfläche festzulegen.  
  
```  
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,  
    BOOL bDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement enthält.  
  
 `bDefault`  
 Wert ungleich NULL, wenn das Steuerelement die Standardschaltfläche werden sollte; andernfalls 0 (null).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement benötigen die **OLEMISC_ACTSLIKEBUTTON** Status-Bit festgelegt ist. Weitere Informationen zu **OLEMISC** Flags finden Sie unter der [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Thema im Windows SDK.  
  
##  <a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate  
 Wird aufgerufen, durch das Framework die ActiveX-Steuerelemente von Standardsteuerelementen Dialogfeld geteilt.  
  
```  
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,  
    DLGITEMTEMPLATE** ppOleDlgItems);
```  
  
### <a name="parameters"></a>Parameter  
 `pTemplate`  
 Ein Zeiger auf die Dialogfeldvorlage untersucht werden.  
  
 `ppOleDlgItems`  
 Eine Liste von Zeigern auf Elemente, die ActiveX-Steuerelemente sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Dialogfeld Vorlagenstruktur nur nicht-ActiveX-Steuerelemente enthält. Wenn keine ActiveX-Steuerelemente vorhanden sind **NULL** zurückgegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn alle ActiveX-Steuerelemente gefunden werden, wird die Vorlage wird analysiert, und erstellt eine neue Vorlage, die nur mit nicht-ActiveX-Steuerelemente enthält. Alle ActiveX-Steuerelemente, die während dieses Vorgangs gefunden werden hinzugefügt, um `ppOleDlgItems`.  
  
 Wenn es keine ActiveX-Steuerelemente in der Vorlage gibt **NULL** zurückgegeben *.*  
  
> [!NOTE]
>  Arbeitsspeicher für die neue Vorlage, in freigegeben wird der `PostCreateDialog` Funktion.  
  
 Überschreiben Sie diese Funktion, um diesen Prozess anzupassen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlSite-Klasse](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer-Klasse](../../mfc/reference/colecontrolcontainer-class.md)
