---
title: COlePropertyPage Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::OVERWRITEApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
dev_langs: C++
helpviewer_keywords:
- COlePropertyPage [MFC], COlePropertyPage
- COlePropertyPage [MFC], GetControlStatus
- COlePropertyPage [MFC], GetObjectArray
- COlePropertyPage [MFC], GetPageSite
- COlePropertyPage [MFC], IgnoreApply
- COlePropertyPage [MFC], IsModified
- COlePropertyPage [MFC], OnEditProperty
- COlePropertyPage [MFC], OnHelp
- COlePropertyPage [MFC], OnInitDialog
- COlePropertyPage [MFC], OnObjectsChanged
- COlePropertyPage [MFC], OnSetPageSite
- COlePropertyPage [MFC], SetControlStatus
- COlePropertyPage [MFC], SetDialogResource
- COlePropertyPage [MFC], SetHelpInfo
- COlePropertyPage [MFC], SetModifiedFlag
- COlePropertyPage [MFC], SetPageName
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cac788f0e7f691f28a6751d15971f117d753428c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="colepropertypage-class"></a>COlePropertyPage-Klasse
Wird verwendet, um die Eigenschaften eines benutzerdefinierten Steuerelements in einer grafischen Oberfläche anzuzeigen, ähnlich wie in einem Dialogfeld.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Erstellt ein `COlePropertyPage`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Gibt an, ob der Benutzer den Wert im Steuerelement geändert hat.|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Das Array von Objekten, die bearbeitet wird, indem Sie die Eigenschaftsseite "zurückgegeben wird.|  
|[COlePropertyPage::GetPageSite](#getpagesite)|Gibt einen Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Bestimmt, welche steuert nicht die Schaltfläche "anwenden" aktivieren.|  
|[COlePropertyPage::IsModified](#ismodified)|Gibt an, ob der Benutzer auf die Eigenschaftenseite geändert hat.|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Vom Framework aufgerufen, wenn der Benutzer eine Eigenschaft bearbeitet wird.|  
|[COlePropertyPage::OnHelp](#onhelp)|Vom Framework aufgerufen, wenn der Benutzer die Hilfe aufruft.|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Vom Framework aufgerufen, wenn die Eigenschaftenseite initialisiert wird.|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Vom Framework aufgerufen, wenn eine andere OLE-Steuerelements mit neuen Eigenschaften ausgewählt wird.|  
|[COlePropertyPage:: OnSetPageSite](#onsetpagesite)|Vom Framework aufgerufen, wenn die Eigenschaft Frame den Anzeigezustand der Seite Standort bereitstellt.|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Setzt ein Flag, das angibt, ob der Benutzer den Wert im Steuerelement geändert hat.|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Legt die Eigenschaftenseite Dialogfeldressource fest.|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Legt fest, der Eigenschaftenseite kurze Hilfetext, den Namen der der Hilfedatei sowie der Hilfekontext.|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Setzt ein Flag, das angibt, ob der Benutzer auf die Eigenschaftenseite geändert hat.|  
|[COlePropertyPage::SetPageName](#setpagename)|Legt die Eigenschaftenseite Namen (Beschriftung) fest.|  
  
## <a name="remarks"></a>Hinweise  
 Beispielsweise kann eine Eigenschaftenseite ein Bearbeitungssteuerelement eingeschlossen werden soll den Benutzer anzeigen und Ändern der Caption-Eigenschaft des Steuerelements.  
  
 Jeder benutzerdefinierten oder vordefinierten-Steuerelement-Eigenschaft kann ein dialogsteuerelement verfügen, die Benutzer des Steuerelements, um den aktuellen Eigenschaftenwert anzeigen und ändern diesen Wert ggf. ermöglicht.  
  
 Weitere Informationen zur Verwendung von `COlePropertyPage`, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="colepropertypage"></a>COlePropertyPage::COlePropertyPage  
 Erstellt ein `COlePropertyPage`-Objekt.  
  
```  
COlePropertyPage(
    UINT idDlg,  
    UINT idCaption);
```  
  
### <a name="parameters"></a>Parameter  
 *idDlg*  
 Ressourcen-ID der Dialogfeldvorlage.  
  
 *idCaption*  
 Ressourcen-ID der Titel der Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Beim Implementieren Sie einer Unterklasse von `COlePropertyPage`, sollten die Unterklasse-Konstruktor verwenden die `COlePropertyPage` Konstruktor zum Identifizieren der Dialogfeldvorlagen-Ressource in die Eigenschaftenseite basiert und eine Zeichenfolgenressource, die die Beschriftung enthält.  
  
##  <a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus  
 Bestimmt, ob der Benutzer den Wert des Steuerelements mit der angegebenen Ressource-ID. die Seite geändert hat  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ressourcen-ID eines Steuerelements Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn der Steuerelementwert, andernfalls geänderte wurde **"false"**.  
  
##  <a name="getobjectarray"></a>COlePropertyPage::GetObjectArray  
 Das Array von Objekten, die bearbeitet wird, indem Sie die Eigenschaftsseite "zurückgegeben wird.  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>Parameter  
 `pnObjects`  
 Ein Zeiger auf eine lange Ganzzahl ohne Vorzeichen, die die Anzahl der Objekte, die bearbeitet wird, von der Seite zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Array von `IDispatch` Zeigern, die Zugriff auf die Eigenschaften jedes Steuerelements auf der Eigenschaftenseite verwendet werden. Der Aufrufer muss diese Schnittstellenzeiger nicht freigegeben.  
  
### <a name="remarks"></a>Hinweise  
 Jede Eigenschaft Page-Objekt verwaltet ein Array von Zeigern auf die `IDispatch` Schnittstellen der Objekte, die von der Seite bearbeitet wird. Diese Funktion legt seine `pnObjects` Argument für die Anzahl der Elemente im Array und gibt einen Zeiger auf das erste Element des Arrays zurück.  
  
##  <a name="getpagesite"></a>COlePropertyPage::GetPageSite  
 Ruft einen Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Steuerelemente und Containern arbeiten zusammen, damit Benutzer durchsuchen und Bearbeiten von Steuerelementeigenschaften können. Das Steuerelement enthält Eigenschaftenseiten, von die jeder ein OLE-Objekt, die dem Benutzer ermöglicht ist, eine zusammengehörige Gruppe von Eigenschaften zu bearbeiten. Der Container enthält eine Eigenschaft Frames, in dem die Eigenschaftenseiten angezeigt. Für jede Seite enthält die Eigenschaft Frame eine Seite-Website unterstützt die `IPropertyPageSite` Schnittstelle.  
  
##  <a name="ignoreapply"></a>COlePropertyPage::IgnoreApply  
 Bestimmt, welche steuert nicht die Schaltfläche "anwenden" aktivieren.  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die ID des Steuerelements, ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaftenseite der Schaltfläche "anwenden" ist nur aktiviert, wenn Werte der Eigenschaft Seitensteuerelemente geändert wurden. Verwenden Sie diese Funktion, geben Sie Steuerelemente an, die nicht, dass die Schaltfläche "anwenden bewirken" aktiviert werden, wenn deren Werte zu ändern.  
  
##  <a name="ismodified"></a>COlePropertyPage::IsModified  
 Bestimmt, ob der Benutzer alle Werte auf der Eigenschaftenseite geändert hat.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn die Eigenschaftenseite geändert wurde.  
  
##  <a name="oneditproperty"></a>COlePropertyPage::OnEditProperty  
 Das Framework ruft diese Funktion auf, wenn eine bestimmte Eigenschaft zur Bearbeitung ist.  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Dispatch-ID, der der bearbeiteten Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die standardmäßige Implementierung **"false"**. Außerkraftsetzungen von dieser Funktion sollte zurückgeben **"true"**.  
  
### <a name="remarks"></a>Hinweise  
 Außer Kraft setzen, um den Fokus auf das entsprechende Steuerelement auf der Seite festgelegt. Bei der Standardimplementierung wird keine Aktion ausgeführt, und gibt **"false"**.  
  
##  <a name="onhelp"></a>COlePropertyPage::OnHelp  
 Das Framework ruft diese Funktion auf, wenn der Benutzer die Onlinehilfe anfordert.  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszHelpDir*  
 Das Verzeichnis, das die Eigenschaftenseite Hilfedatei enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die standardmäßige Implementierung **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie sie aus, wenn die Eigenschaftenseite alle speziellen Aktionen durchführen muss, wenn der Benutzer die Hilfe zugreift. Bei der Standardimplementierung wird keine Aktion ausgeführt, und gibt **"false"**, weist das Framework WinHelp aufrufen.  
  
##  <a name="oninitdialog"></a>COlePropertyPage::OnInitDialog  
 Das Framework ruft diese Funktion aus, wenn die Eigenschaftenseite Dialog initialisiert wird.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die standardmäßige Implementierung **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie sie aus, wenn keine besonderen Maßnahmen erforderlich ist, wenn der Dialog initialisiert wird. Die Standardimplementierung ruft `CDialog::OnInitDialog` und gibt **"false"**.  
  
##  <a name="onobjectschanged"></a>COlePropertyPage::OnObjectsChanged  
 Vom Framework aufgerufen, wenn eine andere OLE-Steuerelements mit neuen Eigenschaften ausgewählt wird.  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Anzeigen der Eigenschaften eines OLE-Steuerelements in der Developer-Umgebung ist ein nicht modales Dialogfeld verwendet, um dessen Eigenschaftenseiten anzuzeigen. Wenn ein anderes Steuerelement ausgewählt ist, muss ein anderen Satz von Eigenschaftenseiten für die neue Gruppe von Eigenschaften angezeigt werden. Das Framework ruft diese Funktion, um die Eigenschaftenseite der Änderung zu benachrichtigen.  
  
 Überschreiben Sie diese Funktion, um eine Benachrichtigung über diese Aktion empfangen und keine besondere Aktionen.  
  
##  <a name="onsetpagesite"></a>COlePropertyPage:: OnSetPageSite  
 Das Framework ruft diese Funktion auf, wenn die Eigenschaft Frame der Eigenschaftenseite Seite Site enthält.  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung lädt die Seite Beschriftung und versucht, die Seitengröße aus dem Dialog-Ressource zu ermitteln. Überschreiben Sie diese Funktion, wenn die Eigenschaftenseite "" ist weitere Aktion erforderlich; die Außerkraftsetzung sollten die Implementierung der Basisklasse aufrufen.  
  
##  <a name="setcontrolstatus"></a>COlePropertyPage::SetControlStatus  
 Ändert den Status eines Steuerelements Eigenschaft.  
  
```  
BOOL SetControlStatus(
    UINT nID,  
    BOOL bDirty);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Enthält die ID eines Steuerelements Eigenschaft.  
  
 `bDirty`  
 Gibt an, ob ein Feld der Eigenschaftenseite geändert wurde. Legen Sie auf **"true"** , wenn das Feld geändert wurde, **"false"** , wenn es nicht geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"**, wenn das angegebene Steuerelement, andernfalls war **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Status eines Steuerelements Eigenschaft fehlerhaft, ist wenn die Eigenschaftenseite geschlossen ist oder die Schaltfläche "anwenden" ausgewählt ist, wird das Steuerelement-Eigenschaft mit dem entsprechenden Wert aktualisiert werden.  
  
##  <a name="setdialogresource"></a>COlePropertyPage::SetDialogResource  
 Legt die Eigenschaftenseite Dialogfeldressource fest.  
  
```  
void SetDialogResource(HGLOBAL hDialog);
```  
  
### <a name="parameters"></a>Parameter  
 *hDialog*  
 Handle für die Eigenschaftenseite Dialogfeldressource.  
  
##  <a name="sethelpinfo"></a>COlePropertyPage::SetHelpInfo  
 Gibt an, QuickInfo-Informationen, die den Hilfe-Dateinamen und den Hilfekontext für die Eigenschaftenseite.  
  
```  
void SetHelpInfo(
    LPCTSTR lpszDocString,  
    LPCTSTR lpszHelpFile = NULL,  
    DWORD dwHelpContext = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszDocString*  
 Eine Zeichenfolge mit kurzen Hilfeinformationen für die Anzeige in einer Statusleiste oder einen anderen Speicherort.  
  
 `lpszHelpFile`  
 Der Name der Hilfedatei die Eigenschaftenseite.  
  
 *dwHelpContext*  
 Der Hilfekontext für die Eigenschaftsseite ".  
  
##  <a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag  
 Gibt an, ob der Benutzer auf die Eigenschaftenseite geändert hat.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Gibt den neuen Wert für die Eigenschaftenseite Änderungsflag an.  
  
##  <a name="setpagename"></a>COlePropertyPage::SetPageName  
 Legt die Eigenschaftenseite-Name, der Eigenschaft Frames in der Regel auf der Registerkarte der Seite angezeigt werden.  
  
```  
void SetPageName(LPCTSTR lpszPageName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszPageName*  
 Ein Zeiger auf eine Zeichenfolge, die die Eigenschaftenseite Namen enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CIRC3](../../visual-cpp-samples.md)   
 [MFC-Beispiel TESTHELP](../../visual-cpp-samples.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)
