---
title: COccManager-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 627fb8e1ad1341257e3064ee195952c37dd4a481
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195537"
---
# <a name="coccmanager-class"></a>COccManager-Klasse
Verwaltet unterschiedliche benutzerdefinierte ControlSites. Wird von `COleControlContainer` - und `COleControlSite` -Objekten implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COccManager::CreateContainer](#createcontainer)|Erstellt ein `COleContainer`-Objekt.|  
|[COccManager::CreateDlgControls](#createdlgcontrols)|Erstellt von ActiveX-Steuerelementen, die von der zugeordneten `COleContainer` Objekt.|  
|[COccManager::CreateSite](#createsite)|Erstellt ein `COleClientSite`-Objekt.|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|Ruft den Code für die Schaltfläche "Standard" ab.|  
|[COccManager::IsDialogMessage](#isdialogmessage)|Bestimmt das Ziel eine Nachricht für das Dialogfeld.|  
|[COccManager::IsLabelControl](#islabelcontrol)|Bestimmt, ob das angegebene Steuerelement ein Label-Steuerelement ist.|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Bestimmt, ob der aktuelle mnemonischen Zeichen das mnemonische Zeichen des angegebenen Steuerelements übereinstimmt.|  
|[COccManager::OnEvent](#onevent)|Versucht, das angegebene Ereignis zu behandeln.|  
|[COccManager::PostCreateDialog](#postcreatedialog)|Gibt während der Erstellung des Dialogfeld zugeordnete Ressourcen frei.|  
|[COccManager::PreCreateDialog](#precreatedialog)|Verarbeitet eine Dialogfeldvorlage für ActiveX-Steuerelemente.|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|Schaltet den Standardzustand des angegebenen Steuerelements.|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Trennt alle vorhandenen ActiveX-Steuerelemente aus allgemeinen Steuerelementen in die angegebene Dialogfeldvorlage.|  
  
## <a name="remarks"></a>Hinweise  
 Die Basisklasse, `CNoTrackObject`, ist eine nicht dokumentierte Basisklasse (im Verzeichnis AFXTLS. H). Entwickelt für die Verwendung von MFC-Framework, abgeleitete Klassen aus der `CNoTrackObject` Klasse speicherverlusterkennung ausgeschlossen werden. Es wird nicht empfohlen, dass Sie direkt von ableiten `CNoTrackObject`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxocc.h  
  
##  <a name="createcontainer"></a>  COccManager::CreateContainer  
 Wird aufgerufen, durch das Framework zum Erstellen eines Steuerelementcontainers.  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Ein Zeiger auf das Window-Objekt, das die benutzerdefinierte Website-Container zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den neu erstellten Container; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Erstellen von benutzerdefinierten Websites finden Sie unter [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).  
  
##  <a name="createdlgcontrols"></a>  COccManager::CreateDlgControls  
 Mit dieser Funktion wird zum Erstellen von ActiveX-Steuerelemente, die gemäß der *pOccDialogInfo* Parameter.  
  
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
  
 *lpszResourceName*  
 Der Name der Ressource erstellt wird.  
  
 *pOccDialogInfo*  
 Ein Zeiger auf die Dialogfeldvorlage verwendet, um das Dialogfeldobjekt zu erstellen.  
  
 *lpResource*  
 Ein Zeiger auf eine Ressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Steuerelement erfolgreich erstellt wurde; andernfalls 0 (null).  
  
##  <a name="createsite"></a>  COccManager::CreateSite  
 Wird aufgerufen, durch das Framework zum Erstellen einer Steuerelement-Website, die vom Container verweist gehostet *pCtrlCont*.  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Parameter  
 *pCtrlCont*  
 Ein Zeiger auf den Steuerelementcontainer, die Site für das neue Steuerelement hostet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Site für das neu erstellte Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Erstellen eines benutzerdefinierten Steuerelements-Website, unter Verwendung Ihrer [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-abgeleitete Klasse.  
  
 Jeder Steuerelementcontainer kann mehrere Websites hosten. Erstellen Sie zusätzliche Standorte mit mehreren Aufrufen an `CreateSite`.  
  
##  <a name="getdefbtncode"></a>  COccManager::GetDefBtnCode  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Steuerelement die Standardschaltfläche Push ist.  
  
```  
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Das Window-Objekt, das das Schaltflächen-Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- DLGC_DEFPUSHBUTTON-Steuerelement ist die Standardschaltfläche im Dialogfeld.  
  
- DLGC_UNDEFPUSHBUTTON-Steuerelement ist nicht als Standardschaltfläche im Dialogfeld.  
  
- **0** Steuerelement ist keine Schaltfläche.  
  
##  <a name="isdialogmessage"></a>  COccManager::IsDialogMessage  
 Wird aufgerufen, durch das Framework, um festzustellen, ob eine Nachricht für das angegebene Dialogfeld bestimmt ist und, wenn es sich handelt, die Nachricht verarbeitet.  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndDlg*  
 Ein Zeiger auf das Dialogfeld "vorgesehenen" der Nachricht.  
  
 *lpMsg*  
 Ein Zeiger auf ein `MSG` -Struktur, die der Nachricht, die überprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten des `IsDialogMessage` tastaturmeldungen überprüfen und konvertieren sie in der Auswahl des entsprechenden Dialogfelds wird. Die TAB-Taste, wenn gedrückt wird, wählt z. B. das nächste Steuerelement oder eine Gruppe von Steuerelementen.  
  
 Überschreiben Sie diese Funktion, um benutzerdefiniertes Verhalten für Nachrichten an das angegebene Dialogfeld bereitzustellen.  
  
##  <a name="islabelcontrol"></a>  COccManager::IsLabelControl  
 Rufen Sie diese Funktion, um zu bestimmen, ob das angegebene Steuerelement ein Label-Steuerelement ist.  
  
```  
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);  
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Ein Zeiger auf das Fenster, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn das Steuerelement eine Bezeichnung ist; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Ein Label-Steuerelement ist eine, die verhält sich wie eine Bezeichnung für ein Steuerelement Ihrer Wahl in der Reihenfolge nächste ist.  
  
##  <a name="ismatchingmnemonic"></a>  COccManager::IsMatchingMnemonic  
 Rufen Sie diese Funktion, um zu bestimmen, ob die aktuelle mnemonisches Zeichen vom Steuerelement dargestellte entspricht.  
  
```  
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,  
    LPMSG lpMsg);

 
static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Ein Zeiger auf das Fenster, das das Steuerelement enthält.  
  
 *lpMsg*  
 Ein Zeiger auf die Nachricht, enthält das mnemonische Zeichen übereinstimmen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das mnemonische Zeichen des Steuerelements übereinstimmt; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onevent"></a>  COccManager::OnEvent  
 Wird aufgerufen, durch das Framework, das angegebene Ereignis zu behandeln.  
  
```  
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,  
    UINT idCtrl,  
    AFX_EVENT* pEvent,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pCmdTarget*  
 Ein Zeiger auf die `CCmdTarget` Objekts, das versucht, das Ereignis behandeln  
  
 *idCtrl*  
 Die Ressourcen-ID des Steuerelements.  
  
 *pEvent*  
 Das Ereignis behandelt wird.  
  
 *pHandlerInfo*  
 Falls ungleich NULL, `OnEvent` füllt die `pTarget` und `pmf` Mitglied der `AFX_CMDHANDLERINFO` Struktur anstatt den Befehl zu verteilen. In der Regel sollte dieser Parameter NULL sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Ereignis behandelt wurde, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um den Standardprozess für die Ereignisbehandlung anpassen.  
  
##  <a name="precreatedialog"></a>  COccManager::PreCreateDialog  
 Wird aufgerufen, durch das Framework eine Dialogfeldvorlage für ActiveX-Steuerelemente vor dem Erstellen des eigentlichen Dialogfelds zu verarbeiten.  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 *pOccDialogInfo*  
 Ein `_AFX_OCC_DIALOG_INFO` Struktur, die Informationen zu der Dialogfeldvorlage und alle ActiveX-Steuerelemente gehostet werden, indem Sie das Dialogfeld enthält.  
  
 *pOrigTemplate*  
 Ein Zeiger auf die Dialogfeldvorlage zum Erstellen des Dialogfelds verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Dialogfeld-Vorlagen: Struktur verwendet, um das Dialogfeld zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig sendet einen Aufruf an `SplitDialogTemplate`, bestimmen Sie, wenn es-ActiveX gibt-Steuerelemente vorhanden, und gibt dann die resultierenden Dialogfeldvorlage zurück.  
  
 Überschreiben Sie diese Funktion, um den Prozess der Erstellung eines Dialogfelds, das hosting von ActiveX-Steuerelementen anpassen.  
  
##  <a name="postcreatedialog"></a>  COccManager::PostCreateDialog  
 Wird aufgerufen, durch das Framework für die Dialogfeldvorlage belegten Arbeitsspeicher freizugeben.  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pOccDialogInfo*  
 Ein `_AFX_OCC_DIALOG_INFO` Struktur, die Informationen zu der Dialogfeldvorlage und alle ActiveX-Steuerelemente gehostet werden, indem Sie das Dialogfeld enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Speicher belegt wurde, durch einen Aufruf von `SplitDialogTemplate`, und für alle gehosteten ActiveX-Steuerelemente im Dialogfeld verwendet wurde.  
  
 Überschreiben Sie diese Funktion, um den Prozess des Bereinigen aller Ressourcen, die von der Dialogfeldobjekt verwendet anzupassen.  
  
##  <a name="setdefaultbutton"></a>  COccManager::SetDefaultButton  
 Rufen Sie diese Funktion, um das Steuerelement als Standardschaltfläche festzulegen.  
  
```  
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,  
    BOOL bDefault);
```  
  
### <a name="parameters"></a>Parameter  
 *Aufnehmen*  
 Ein Zeiger auf das Fenster, das das Steuerelement enthält.  
  
 *bStandardstufe*  
 Ungleich NULL, wenn das Steuerelement die Standardschaltfläche werden soll; andernfalls 0 (null).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement muss OLEMISC_ACTSLIKEBUTTON Status-bit-Satz verfügen. Weitere Informationen zu OLEMISC-Flags finden Sie unter den [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Thema in der Windows-SDK.  
  
##  <a name="splitdialogtemplate"></a>  COccManager::SplitDialogTemplate  
 Vom Framework aufgerufen, die ActiveX-Steuerelemente von Dialogfeld-Standardsteuerelementen aufzuteilen.  
  
```  
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,  
    DLGITEMTEMPLATE** ppOleDlgItems);
```  
  
### <a name="parameters"></a>Parameter  
 *pTemplate*  
 Ein Zeiger auf die Dialogfeldvorlage untersucht werden.  
  
 *ppOleDlgItems*  
 Eine Liste von Zeigern auf Elemente, die ActiveX-Steuerelemente sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Dialogfeld-Vorlagen: Struktur, die nur nicht-ActiveX-Steuerelemente enthält. Wenn keine ActiveX-Steuerelemente vorhanden sind, wird NULL zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn alle ActiveX-Steuerelemente gefunden werden, wird die Vorlage wird analysiert, und erstellt eine neue Vorlage, die nur nicht-ActiveX-Steuerelemente enthält. Alle ActiveX-Steuerelemente, die während dieses Vorgangs gefunden werden hinzugefügt *PpOleDlgItems*.  
  
 Wenn keine ActiveX-Steuerelemente in der Vorlage vorhanden sind, wird NULL zurückgegeben *.*  
  
> [!NOTE]
>  Die neue Vorlage freigegeben wird, im Arbeitsspeicher der `PostCreateDialog` Funktion.  
  
 Überschreiben Sie diese Funktion, um diesen Prozess anpassen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControlSite-Klasse](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer-Klasse](../../mfc/reference/colecontrolcontainer-class.md)
