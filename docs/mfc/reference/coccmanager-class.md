---
title: Klasse COccManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COccManager
dev_langs:
- C++
helpviewer_keywords:
- custom controls [MFC], sites
- COccManager class
- CNoTrackObject class
- ActiveX control containers [C++], control site
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
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
ms.openlocfilehash: 14a75c491a7061d921d6c0c250c6224f4e7d2f04
ms.lasthandoff: 02/24/2017

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
|[COccManager::CreateDlgControls](#createdlgcontrols)|Erstellt von ActiveX-Steuerelementen, die von der zugeordneten `COleContainer` Objekt.|  
|[COccManager::CreateSite](#createsite)|Erstellt ein `COleClientSite`-Objekt.|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|Ruft den Code für die Standardschaltfläche ab.|  
|[COccManager::IsDialogMessage](#isdialogmessage)|Das Ziel einer Nachricht Dialogfeld bestimmt.|  
|[COccManager::IsLabelControl](#islabelcontrol)|Bestimmt, ob das angegebene Steuerelement ein Bezeichnungsfeld-Steuerelement ist.|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Bestimmt, ob das aktuelle mnemonische Zeichen das mnemonische Zeichen des angegebenen Steuerelements übereinstimmt.|  
|[COccManager::OnEvent](#onevent)|Versucht, das angegebene Ereignis zu behandeln.|  
|[COccManager::PostCreateDialog](#postcreatedialog)|Während der Erstellung des Dialogfeld reservierten Ressourcen frei.|  
|[COccManager::PreCreateDialog](#precreatedialog)|Verarbeitet eine Dialogfeldvorlage für ActiveX-Steuerelemente.|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|Schaltet den Standardzustand des angegebenen Steuerelements.|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Trennt alle vorhandenen ActiveX-Steuerelemente von allgemeinen Steuerelementen in der Vorlage angegebene Dialogfeld.|  
  
## <a name="remarks"></a>Hinweise  
 Die Basisklasse **CNoTrackObject**, ist eine nicht dokumentierte Basisklasse (im Verzeichnis AFXTLS. (H). Abgeleitete Klassen von MFC-Framework für die Verwendung vorgesehen, die **CNoTrackObject** Klasse von speicherverlusterkennung ausgeschlossen werden. Es wird nicht empfohlen, direkt von abzuleiten, **CNoTrackObject**.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxocc.h  
  
##  <a name="a-namecreatecontainera--coccmanagercreatecontainer"></a><a name="createcontainer"></a>COccManager::CreateContainer  
 Aufgerufen, um ein Steuerelementcontainer zu erstellen.  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Window-Objekt, das den benutzerdefinierten Site-Container zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den neu erstellten Container; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Erstellen von benutzerdefinierten Websites finden Sie unter [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).  
  
##  <a name="a-namecreatedlgcontrolsa--coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a>COccManager::CreateDlgControls  
 Rufen Sie diese Funktion zum Erstellen von ActiveX-Steuerelemente, die durch die `pOccDialogInfo` Parameter.  
  
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
 Ein Zeiger auf das übergeordnete Element des Dialog-Objekts.  
  
 `lpszResourceName`  
 Der Name der Ressource erstellt wird.  
  
 `pOccDialogInfo`  
 Ein Zeiger auf die Dialogfeldvorlage verwendet, um das Dialogfeldobjekt zu erstellen.  
  
 `lpResource`  
 Ein Zeiger auf eine Ressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement erfolgreich erstellt wurde; andernfalls&0; (null).  
  
##  <a name="a-namecreatesitea--coccmanagercreatesite"></a><a name="createsite"></a>COccManager::CreateSite  
 Aufgerufen, um eine-Steuerelement Website, auf den Container erstellen `pCtrlCont`.  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Parameter  
 `pCtrlCont`  
 Ein Zeiger auf der Steuerelement-Container, die Site für das neue Steuerelement hostet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Site für das neu erstellte Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Erstellen eines benutzerdefinierten Steuerelements-Website, unter Verwendung der [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-abgeleiteten Klasse.  
  
 Jedes Steuerelementcontainer kann mehrere Sites gehostet. Erstellen Sie zusätzliche Standorte durch mehrere Aufrufe `CreateSite`.  
  
##  <a name="a-namegetdefbtncodea--coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a>COccManager::GetDefBtnCode  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Steuerelement eine Standardschaltfläche ist.  
  
```  
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Das Window-Objekt, das das Button-Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- **DLGC_DEFPUSHBUTTON** -Steuerelement ist die Standardschaltfläche im Dialogfeld.  
  
- **DLGC_UNDEFPUSHBUTTON** Steuerelement ist nicht die Standardschaltfläche im Dialogfeld.  
  
- **0** Steuerelement ist keine Schaltfläche.  
  
##  <a name="a-nameisdialogmessagea--coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a>COccManager::IsDialogMessage  
 Aufgerufen, um festzustellen, ob eine Nachricht für das angegebene Dialogfeld vorgesehen ist und ist er die Nachricht verarbeitet.  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndDlg*  
 Ein Zeiger auf das beabsichtigte Ziel (Dialogfeld) der Nachricht.  
  
 `lpMsg`  
 Ein Zeiger auf eine `MSG` -Struktur, die der Nachricht, die überprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten des `IsDialogMessage` wird zur Überprüfung von Tastatureingaben und konvertieren sie in der Auswahl für das entsprechende Dialogfeld. Beispielsweise wählt die TAB-Taste beim drücken, das Steuerelement oder die nächste Gruppe von Steuerelementen.  
  
 Überschreiben Sie diese Funktion, um benutzerdefiniertes Verhalten für Nachrichten an das angegebene Dialogfeld bereitzustellen.  
  
##  <a name="a-nameislabelcontrola--coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a>COccManager::IsLabelControl  
 Rufen Sie diese Funktion, um zu bestimmen, ob das angegebene Steuerelement ein Bezeichnungsfeld-Steuerelement ist.  
  
```  
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);  
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement eine Bezeichnung ist; andernfalls&0; (null)  
  
### <a name="remarks"></a>Hinweise  
 Ein Bezeichnungsfeld-Steuerelement ist verhält sich wie eine Bezeichnung für ein Steuerelement Ihrer Wahl in der Reihenfolge weiter ist.  
  
##  <a name="a-nameismatchingmnemonica--coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic  
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
 Ein Zeiger auf die Nachricht mit der Mnemonik zutreffen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das mnemonische Zeichen des Steuerelements entspricht; andernfalls&0; (null)  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameoneventa--coccmanageronevent"></a><a name="onevent"></a>COccManager::OnEvent  
 Vom Framework aufgerufen wird, das angegebene Ereignis behandeln.  
  
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
 Wenn nicht **NULL**, `OnEvent` füllt die **pTarget** und **Pmf** Mitglieder der **AFX_CMDHANDLERINFO** Struktur, anstatt den Befehl zu verteilen. Dieser Parameter sollte in der Regel **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Ereignis behandelt wurde, andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um den Standardwert für die Ereignisbehandlung Prozess anzupassen.  
  
##  <a name="a-nameprecreatedialoga--coccmanagerprecreatedialog"></a><a name="precreatedialog"></a>COccManager::PreCreateDialog  
 Vom Framework eine Dialogfeldvorlage für ActiveX-Steuerelemente zu verarbeiten, vor dem Erstellen des aktuellen Dialogfelds aufgerufen.  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `pOccDialogInfo`  
 Ein **_AFX_OCC_DIALOG_INFO** Struktur enthält Informationen über die Dialogfeldvorlage und alle ActiveX-Steuerelemente, die vom Dialogfeld gehostet.  
  
 *pOrigTemplate*  
 Ein Zeiger auf die Dialogfeldvorlage zur Erstellung des Dialogfelds verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Struktur von Dialogen Vorlage verwendet, um das Dialogfeld zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig führt einen Aufruf von `SplitDialogTemplate`, bestimmen, befinden sich alle ActiveX-Steuerelemente vorhanden und gibt dann die resultierenden Dialogfeldvorlage zurück.  
  
 Überschreiben Sie diese Funktion, um den Prozess der Erstellung eines Dialogfelds, das hosting von ActiveX-Steuerelementen anpassen.  
  
##  <a name="a-namepostcreatedialoga--coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a>COccManager::PostCreateDialog  
 Vom Framework aufgerufen, für die Dialogfeldvorlage belegten Speicher freizugeben.  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `pOccDialogInfo`  
 Ein **_AFX_OCC_DIALOG_INFO** Struktur enthält Informationen über die Dialogfeldvorlage und alle ActiveX-Steuerelemente, die vom Dialogfeld gehostet.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Speicher belegt wurde, durch einen Aufruf von `SplitDialogTemplate`, und für alle gehosteten ActiveX-Steuerelemente im Dialogfeld verwendet wurde.  
  
 Überschreiben Sie diese Funktion, um den Prozess Bereinigen von Ressourcen verwendet, die für die Dialogfeldobjekt anzupassen.  
  
##  <a name="a-namesetdefaultbuttona--coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a>COccManager::SetDefaultButton  
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
 Wert ungleich NULL, wenn das Steuerelement die Standardschaltfläche werden sollen; andernfalls&0; (null).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement muss verfügen die **OLEMISC_ACTSLIKEBUTTON** Status-Bit festgelegt. Weitere Informationen zu **OLEMISC** Flags finden Sie unter der [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Thema in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesplitdialogtemplatea--coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate  
 Aufgerufen, die ActiveX-Steuerelemente von Standardsteuerelementen Dialogfeld geteilt.  
  
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
 Ein Zeiger auf ein Dialogfeld Vorlagenstruktur nur nicht-ActiveX-Steuerelemente enthält. Wenn keine ActiveX-Steuerelemente vorhanden sind, **NULL** zurückgegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine ActiveX-Steuerelemente gefunden werden, die Vorlage wird analysiert, und erstellt eine neue Vorlage, die nur nicht-ActiveX-Steuerelemente enthält. Alle ActiveX-Steuerelemente, die während dieses Vorgangs gefunden werden hinzugefügt `ppOleDlgItems`.  
  
 Es sind keine ActiveX-Steuerelemente in der Vorlage **NULL** zurückgegeben *.*  
  
> [!NOTE]
>  Arbeitsspeicher für die neue Vorlage auf freigegeben wird die `PostCreateDialog` Funktion.  
  
 Überschreiben Sie diese Funktion, um diesen Prozess anzupassen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlSite-Klasse](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer-Klasse](../../mfc/reference/colecontrolcontainer-class.md)

