---
title: COlePropertyPage-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6b6d011b40ebc9871baec1a1e57636499a58963
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851573"
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
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Gibt an, ob der Benutzer den Wert im Steuerelement geändert wurde.|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Gibt zurück, das Array von Objekten, die von der Eigenschaftenseite bearbeitet wird.|  
|[COlePropertyPage::GetPageSite](#getpagesite)|Gibt einen Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Bestimmt, welche Steuerelemente nicht die Schaltfläche "anwenden" aktivieren.|  
|[COlePropertyPage::IsModified](#ismodified)|Gibt an, ob der Benutzer auf die Eigenschaftenseite geändert hat.|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Wird vom Framework aufgerufen, wenn der Benutzer eine Eigenschaft bearbeitet.|  
|[COlePropertyPage::OnHelp](#onhelp)|Wird vom Framework aufgerufen, wenn der Benutzer Hilfe aufruft.|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Vom Framework aufgerufen, wenn die Eigenschaftenseite initialisiert wird.|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Vom Framework aufgerufen, wenn ein anderes OLE-Steuerelement, mit neuen Eigenschaften, ausgewählt wird.|  
|[COlePropertyPage:: OnSetPageSite](#onsetpagesite)|Vom Framework aufgerufen, wenn der Eigenschaftenrahmen die Site der Seite bereitstellt.|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Legt ein Flag, der angibt, ob der Benutzer den Wert im Steuerelement geändert wurde.|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Legt fest, der Eigenschaftenseite des Dialog-Ressource.|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Legt fest, die Eigenschaftenseite kurzen Hilfetext, den Namen des seine Hilfedatei sowie die Hilfekontext.|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Legt ein Flag, der angibt, ob der Benutzer auf die Eigenschaftenseite geändert hat.|  
|[COlePropertyPage::SetPageName](#setpagename)|Legt die Eigenschaftenseite Namen (Beschriftung) fest.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Eigenschaftenseite kann z. B. ein Edit-Steuerelement enthalten, mit dem Benutzer anzeigen und ändern die Caption-Eigenschaft des Steuerelements.  
  
 Jede Eigenschaft des benutzerdefinierten oder vordefinierten Steuerelements haben ein dialogsteuerelement, die Benutzer des Steuerelements, um den aktuellen Eigenschaftswert anzeigen und ändern diesen Wert bei Bedarf ermöglicht.  
  
 Weitere Informationen zur Verwendung von `COlePropertyPage`, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="colepropertypage"></a>  COlePropertyPage::COlePropertyPage  
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
 Ressourcen-ID der Beschriftung für die Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Implementierung einer Unterklasse von `COlePropertyPage`, sollten die Unterklasse Konstruktor verwenden, die `COlePropertyPage` Konstruktor, um der Dialogfeldvorlagen-Ressource zu identifizieren die basiert auf der Seite der und Zeichenfolgenressource mit der Beschriftung.  
  
##  <a name="getcontrolstatus"></a>  COlePropertyPage::GetControlStatus  
 Bestimmt, ob der Benutzer den Wert des Steuerelements die Seite mit der angegebenen Ressourcen-ID geändert wurde  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Ressourcen-ID eines Steuerelements Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Wert des Steuerelements geändert wurde. andernfalls "false".  
  
##  <a name="getobjectarray"></a>  COlePropertyPage::GetObjectArray  
 Gibt zurück, das Array von Objekten, die von der Eigenschaftenseite bearbeitet wird.  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>Parameter  
 *pnObjects*  
 Zeiger auf eine lange Ganzzahl ohne Vorzeichen, die die Anzahl der Objekte, die bearbeitet wird, von der Seite erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Array von `IDispatch` Zeigern, die Zugriff auf die Eigenschaften der einzelnen Steuerelemente auf der Eigenschaftenseite verwendet werden. Der Aufrufer muss diese Schnittstellenzeiger nicht freigegeben.  
  
### <a name="remarks"></a>Hinweise  
 Jede Eigenschaft Page-Objekt verwaltet ein Array von Zeigern auf die `IDispatch` Schnittstellen die Objekte, die von der Seite bearbeitet wird. Diese Funktion legt die *PnObjects* Argument für die Anzahl der Elemente im Array und gibt einen Zeiger auf das erste Element des Arrays zurück.  
  
##  <a name="getpagesite"></a>  COlePropertyPage::GetPageSite  
 Ruft einen Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Steuerelemente und Containern arbeiten zusammen, damit Benutzer durchsuchen und Bearbeiten von Steuerelementeigenschaften können. Das Steuerelement bietet Eigenschaftenseiten, von die jeder ein OLE-Objekt, die dem Benutzer ermöglicht ist, eine zusammengehörige Gruppe von Eigenschaften zu bearbeiten. Der Container enthält, ein eigenschaftenrahmens, in dem die Eigenschaftenseiten angezeigt wird. Für jede Seite, stellt der Eigenschaftenrahmen die Site eine Seite, die unterstützt die `IPropertyPageSite` Schnittstelle.  
  
##  <a name="ignoreapply"></a>  COlePropertyPage::IgnoreApply  
 Bestimmt, welche Steuerelemente nicht die Schaltfläche "anwenden" aktivieren.  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Die ID des Steuerelements, ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaftenseite der Schaltfläche "anwenden" ist nur aktiviert, wenn Werte von Seitensteuerelementen Eigenschaft geändert wurden. Verwenden Sie diese Funktion an Steuerelementen, die nicht, dass die Schaltfläche "anwenden bewirken" aktiviert werden, wenn sich ihre Werte ändern.  
  
##  <a name="ismodified"></a>  COlePropertyPage::IsModified  
 Bestimmt, ob der Benutzer alle Werte auf der Eigenschaftenseite geändert hat.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Eigenschaftenseite geändert wurde.  
  
##  <a name="oneditproperty"></a>  COlePropertyPage::OnEditProperty  
 Das Framework ruft diese Funktion auf, wenn eine bestimmte Eigenschaft ist bearbeitet werden.  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 *DISPID*  
 Dispatch-ID der bearbeiteten Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt "false" zurück. Außerkraftsetzungen für diese Funktion sollte "true" zurückgeben.  
  
### <a name="remarks"></a>Hinweise  
 Sie können überschreiben, um den Fokus auf das entsprechende Steuerelement auf der Seite festgelegt. Die Standardimplementierung führt keine Aktion aus und gibt FALSE zurück.  
  
##  <a name="onhelp"></a>  COlePropertyPage::OnHelp  
 Das Framework ruft diese Funktion auf, wenn der Benutzer Hilfe anfordert.  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszHelpDir*  
 Verzeichnis, das die Eigenschaftenseite Hilfedatei enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt "false" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie sie aus, wenn Ihr Eigenschaftenseite alle speziellen Aktionen durchführen muss, wenn der Benutzer Hilfe aufruft. Die Standardimplementierung führt keine Aktion aus und gibt FALSE zurück, den angewiesen wird, das Aufrufen von WinHelp-Framework.  
  
##  <a name="oninitdialog"></a>  COlePropertyPage::OnInitDialog  
 Das Framework ruft diese Funktion auf, wenn das Dialogfeld für die Eigenschaftenseite initialisiert wird.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt "false" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie sie aus, wenn alle speziellen Aktionen erforderlich ist, wenn das Dialogfeld initialisiert wird. Die Standardimplementierung ruft `CDialog::OnInitDialog` und gibt FALSE zurück.  
  
##  <a name="onobjectschanged"></a>  COlePropertyPage::OnObjectsChanged  
 Vom Framework aufgerufen, wenn ein anderes OLE-Steuerelement, mit neuen Eigenschaften, ausgewählt wird.  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Anzeigen der Eigenschaften eines OLE-Steuerelements in der entwicklerumgebung wird ein nicht modales Dialogfeld verwendet, um die Eigenschaftenseiten angezeigt. Wenn ein anderes Steuerelement ausgewählt ist, muss ein anderen Satz von Eigenschaftenseiten für den neuen Satz an Eigenschaften angezeigt werden. Das Framework ruft diese Funktion, um die Eigenschaftenseite der Änderung zu benachrichtigen.  
  
 Überschreiben Sie diese Funktion für den Empfang von Benachrichtigungen über diese Aktion aus, und führen Sie alle speziellen Aktionen an.  
  
##  <a name="onsetpagesite"></a>  COlePropertyPage:: OnSetPageSite  
 Das Framework ruft diese Funktion auf, wenn der Eigenschaftenrahmen die Site der Seite der Eigenschaftenseite bereitstellt.  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung lädt die Seite der Beschriftung und versucht, die Seitengröße aus der Dialogfeldressource zu ermitteln. Überschreiben Sie diese Funktion, wenn Ihr Eigenschaftenseite weitere Aktion erforderlich ist; die Außerkraftsetzung sollten die Implementierung der Basisklasse aufrufen.  
  
##  <a name="setcontrolstatus"></a>  COlePropertyPage::SetControlStatus  
 Ändert den Status des Steuerelements eine Seite.  
  
```  
BOOL SetControlStatus(
    UINT nID,  
    BOOL bDirty);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Enthält die ID eines Steuerelements Eigenschaft.  
  
 *bDirty*  
 Gibt an, wenn ein Feld der Eigenschaftenseite geändert wurde. Legen Sie auf "true", wenn das Feld geändert wurde, FALSE, wenn er nicht geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn das angegebene Steuerelement festgelegt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Status des Steuerelements eine Seite fehlerhaft, ist wenn die Eigenschaftenseite geschlossen ist, oder die Schaltfläche "anwenden" ausgewählt ist, wird die Eigenschaft des Steuerelements mit dem entsprechenden Wert aktualisiert werden.  
  
##  <a name="setdialogresource"></a>  COlePropertyPage::SetDialogResource  
 Legt fest, der Eigenschaftenseite des Dialog-Ressource.  
  
```  
void SetDialogResource(HGLOBAL hDialog);
```  
  
### <a name="parameters"></a>Parameter  
 *hDialog*  
 Handle für die Eigenschaftenseite des Dialog-Ressource.  
  
##  <a name="sethelpinfo"></a>  COlePropertyPage::SetHelpInfo  
 Gibt QuickInfo-Informationen, die Hilfe-Dateinamen und den Hilfekontext für Ihr Eigenschaftenseite.  
  
```  
void SetHelpInfo(
    LPCTSTR lpszDocString,  
    LPCTSTR lpszHelpFile = NULL,  
    DWORD dwHelpContext = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszDocString*  
 Eine Zeichenfolge mit kurzen Hilfeinformationen für die Anzeige in einer Statusleiste oder einem anderen Speicherort.  
  
 *lpszHelpFile*  
 Der Name der Hilfedatei für die Eigenschaftenseite.  
  
 *dwHelpContext*  
 Der Hilfekontext für die Eigenschaftenseite.  
  
##  <a name="setmodifiedflag"></a>  COlePropertyPage::SetModifiedFlag  
 Gibt an, ob der Benutzer auf die Eigenschaftenseite geändert hat.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bModified*  
 Gibt den neuen Wert für die Eigenschaftenseite Änderungsflag an.  
  
##  <a name="setpagename"></a>  COlePropertyPage::SetPageName  
 Legt die Eigenschaftenseite-Namen, der Eigenschaftenrahmen in der Regel auf der Registerkarte der Seite angezeigt wird.  
  
```  
void SetPageName(LPCTSTR lpszPageName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszPageName*  
 Zeiger auf eine Zeichenfolge, die die Eigenschaftenseite Namen enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CIRC3](../../visual-cpp-samples.md)   
 [MFC-Beispiel TESTHELP](../../visual-cpp-samples.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)
