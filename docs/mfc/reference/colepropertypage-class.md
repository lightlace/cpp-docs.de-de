---
title: COlePropertyPage Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::IgnoreApply
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
- OLE property pages
- custom controls [MFC], properties
- COlePropertyPage class
- properties [C++], displaying
- displaying properties
- property pages, OLE
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 20d70cc25305fc5d17860314d9cfbe927df65c70
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertypage-class"></a>COlePropertyPage-Klasse
Wird verwendet, um die Eigenschaften eines benutzerdefinierten Steuerelements in einer grafischen Oberfläche anzuzeigen, ähnlich wie in einem Dialogfeld.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Erstellt ein `COlePropertyPage`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Gibt an, ob der Benutzer den Wert im Steuerelement geändert hat.|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Gibt das Array von Objekten, die von der Eigenschaftenseite bearbeitet wird.|  
|[COlePropertyPage::GetPageSite](#getpagesite)|Gibt einen Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Bestimmt, welche Steuerelemente die Schaltfläche übernehmen nicht aktivieren.|  
|[COlePropertyPage::IsModified](#ismodified)|Gibt an, ob der Benutzer die Eigenschaftenseite geändert wurde.|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Wird vom Framework aufgerufen, wenn der Benutzer eine Eigenschaft bearbeitet.|  
|[COlePropertyPage::OnHelp](#onhelp)|Wird vom Framework aufgerufen, wenn der Benutzer die Hilfe aufruft.|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Wird vom Framework aufgerufen, wenn die Eigenschaftenseite initialisiert wird.|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Wird vom Framework aufgerufen, wenn ein anderes OLE-Steuerelement, mit neuen Eigenschaften ausgewählt wird.|  
|[COlePropertyPage:: OnSetPageSite](#onsetpagesite)|Vom Framework aufgerufen, wenn die Eigenschaft Frame die Site der Seite bereitstellt.|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Legt ein Flag gibt an, ob der Benutzer den Wert im Steuerelement geändert hat.|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Legt die Eigenschaftenseite des Dialog-Ressource.|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Wird die Eigenschaftenseite kurzen Hilfetext, den Namen der Hilfe und den Hilfekontext festgelegt.|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Legt ein Flag gibt an, ob der Benutzer die Eigenschaftenseite geändert wurde.|  
|[COlePropertyPage::SetPageName](#setpagename)|Legt die Eigenschaftenseite Namen (Beschriftung).|  
  
## <a name="remarks"></a>Hinweise  
 Beispielsweise kann eine Eigenschaftenseite ein Bearbeitungssteuerelement umfassen, können den Benutzer zum Anzeigen und ändern die Caption-Eigenschaft des Steuerelements.  
  
 Aller benutzerdefinierten oder vordefinierten Eigenschaften kann es sich um ein Dialogfeldsteuerelement haben, in dem das Steuerelement Benutzer zeigt den aktuellen Eigenschaftenwert, und ändern diesen Wert bei Bedarf.  
  
 Weitere Informationen zur Verwendung von `COlePropertyPage`, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Ressourcen-ID, der die Dialogfeldvorlage.  
  
 *idCaption*  
 Ressourcen-ID der Titel der Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Implementierung einer Unterklasse von `COlePropertyPage`, Ihrer Unterklasse-Konstruktor verwenden, sollten die `COlePropertyPage` Konstruktor zum Identifizieren der Dialogfeldvorlagen-Ressource in die Eigenschaftenseite basiert und die Zeichenfolgenressource, die die Beschriftung enthält.  
  
##  <a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus  
 Bestimmt, ob der Benutzer den Wert des Eigenschaft-Steuerelement mit der angegebenen Ressource-ID geändert hat  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ressourcen-ID eines Steuerelements Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn der Steuerelementwert, andernfalls geänderte wurde **FALSE**.  
  
##  <a name="getobjectarray"></a>COlePropertyPage::GetObjectArray  
 Gibt das Array von Objekten, die von der Eigenschaftenseite bearbeitet wird.  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>Parameter  
 `pnObjects`  
 Zeiger auf eine lange Ganzzahl ohne Vorzeichen, die die Anzahl der Objekte, die gerade von der Seite erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Array von `IDispatch` Zeigern, die Zugriff auf die Eigenschaften der einzelnen Steuerelemente auf der Eigenschaftenseite verwendet werden. Der Aufrufer muss diese Schnittstellenzeiger nicht freigegeben.  
  
### <a name="remarks"></a>Hinweise  
 Jede Eigenschaft Page-Objekt verwaltet einen Array von Zeigern auf die `IDispatch` Schnittstellen die Objekte, die von der Seite bearbeitet wird. Diese Funktion legt die `pnObjects` Argument für die Anzahl der Elemente im Array und gibt einen Zeiger auf das erste Element des Arrays zurück.  
  
##  <a name="getpagesite"></a>COlePropertyPage::GetPageSite  
 Ruft einen Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf der Eigenschaftenseite `IPropertyPageSite` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Steuerelemente und Containern zusammen, damit Benutzer durchsuchen und Bearbeiten von Steuerelementeigenschaften können. Das Steuerelement bietet Eigenschaftenseiten, von die jede ein OLE-Objekt, die dem Benutzer ermöglicht ist, eine zusammengehörige Gruppe von Eigenschaften zu bearbeiten. Der Container enthält einen Eigenschaft Frame, in dem die Eigenschaftenseiten angezeigt. Für jede Seite bietet der Eigenschaftenrahmen eine Seite-Website, die unterstützt die `IPropertyPageSite` Schnittstelle.  
  
##  <a name="ignoreapply"></a>COlePropertyPage::IgnoreApply  
 Bestimmt, welche Steuerelemente die Schaltfläche übernehmen nicht aktivieren.  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die ID des Steuerelements, ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaftenseite übernehmen-Schaltfläche ist nur aktiviert, wenn Werte der Eigenschaft Seitensteuerelemente geändert wurden. Verwenden Sie diese Funktion an Steuerelemente, die nicht, dass die Schaltfläche "anwenden bewirken" aktiviert werden soll, wenn die Werte zu ändern.  
  
##  <a name="ismodified"></a>COlePropertyPage::IsModified  
 Bestimmt, ob der Benutzer alle Werte auf der Eigenschaftenseite geändert hat.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die Eigenschaftenseite geändert wurde.  
  
##  <a name="oneditproperty"></a>COlePropertyPage::OnEditProperty  
 Das Framework ruft diese Funktion wird eine bestimmte Eigenschaft bearbeitet werden kann.  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>Parameter  
 `dispid`  
 Dispatch-ID, der der bearbeiteten Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung gibt **FALSE**. Außerkraftsetzungen für diese Funktion sollte zurückgeben **TRUE**.  
  
### <a name="remarks"></a>Hinweise  
 Außer Kraft setzen, um den Fokus auf das entsprechende Steuerelement auf der Seite festgelegt. Die standardmäßige Implementierung keine Aktion aus und gibt **FALSE**.  
  
##  <a name="onhelp"></a>COlePropertyPage::OnHelp  
 Das Framework ruft diese Funktion auf, wenn der Benutzer online-Hilfe anfordert.  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszHelpDir*  
 Verzeichnis, das die Eigenschaftenseite Hilfedatei enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung gibt **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaftenseite spezielle Aktion ausführen muss, wenn der Benutzer Hilfe zugreift überschreiben. Die standardmäßige Implementierung keine Aktion aus und gibt **FALSE**, wodurch das Aufrufen von WinHelp-Framework angewiesen.  
  
##  <a name="oninitdialog"></a>COlePropertyPage::OnInitDialog  
 Das Framework ruft diese Funktion auf, wenn die Eigenschaftenseite Dialogfeld initialisiert wird.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung gibt **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben sie, wenn besondere Aktion erforderlich ist, wenn das Dialogfeld initialisiert wird. Die standardmäßige Implementierung ruft `CDialog::OnInitDialog` und gibt **FALSE**.  
  
##  <a name="onobjectschanged"></a>COlePropertyPage::OnObjectsChanged  
 Wird vom Framework aufgerufen, wenn ein anderes OLE-Steuerelement, mit neuen Eigenschaften ausgewählt wird.  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Anzeigen der Eigenschaften eines OLE-Steuerelements in der Developer-Umgebung ist ein nicht modales Dialogfeld verwendet, um seine Eigenschaftenseiten anzuzeigen. Wenn ein anderes Steuerelement ausgewählt ist, muss ein anderen Satz von Eigenschaftenseiten für den neuen Satz von Eigenschaften angezeigt werden. Das Framework ruft diese Funktion, um die Eigenschaftenseite der Änderung zu benachrichtigen.  
  
 Überschreiben Sie diese Funktion, um die Benachrichtigung zu empfangen und speziellen Aktionen ausführen.  
  
##  <a name="onsetpagesite"></a>COlePropertyPage:: OnSetPageSite  
 Das Framework ruft diese Funktion auf, wenn Eigenschaftenfenster der Eigenschaftenseite Seite Standort bereitstellt.  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung der Beschriftung für die Seite lädt und versucht, die Seitengröße aus der Ressource zu ermitteln. Überschreiben Sie diese Funktion, wenn die Eigenschaftenseite weitere Aktion erforderlich ist; überschreiben, sollten die Implementierung der Basisklasse aufrufen.  
  
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
 Gibt an, ob ein Feld der Eigenschaftenseite geändert wurde. Legen Sie auf **TRUE** , wenn das Feld geändert wurde, **FALSE** , wenn es nicht geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,**, wenn das angegebene Steuerelement; andernfalls wurde **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Status eines Steuerelements Eigenschaft fehlerhaft, ist wenn die Eigenschaftenseite geschlossen ist oder die Schaltfläche "anwenden" ausgewählt ist, wird die Eigenschaft des Steuerelements mit dem entsprechenden Wert aktualisiert werden.  
  
##  <a name="setdialogresource"></a>COlePropertyPage::SetDialogResource  
 Legt die Eigenschaftenseite des Dialog-Ressource.  
  
```  
void SetDialogResource(HGLOBAL hDialog);
```  
  
### <a name="parameters"></a>Parameter  
 *hDialog*  
 Handle für die Eigenschaftenseite des Dialog-Ressource.  
  
##  <a name="sethelpinfo"></a>COlePropertyPage::SetHelpInfo  
 Gibt an, QuickInfo-Informationen und den Dateinamen für die Hilfe in den Hilfekontext für die Eigenschaftenseite.  
  
```  
void SetHelpInfo(
    LPCTSTR lpszDocString,  
    LPCTSTR lpszHelpFile = NULL,  
    DWORD dwHelpContext = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszDocString*  
 Eine Zeichenfolge mit kurzen Hilfeinformationen für die Anzeige in einer Statusleiste oder einem anderen Speicherort.  
  
 `lpszHelpFile`  
 Der Name der Hilfedatei für die Eigenschaftenseite.  
  
 *dwHelpContext*  
 Der Hilfekontext für die Eigenschaftenseite.  
  
##  <a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag  
 Gibt an, ob der Benutzer die Eigenschaftenseite geändert wurde.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Gibt den neuen Wert für die Eigenschaftenseite Änderungsflag an.  
  
##  <a name="setpagename"></a>COlePropertyPage::SetPageName  
 Legt die Eigenschaftenseite Name der Eigenschaft Frame in der Regel auf der Seite Registerkarte angezeigt wird.  
  
```  
void SetPageName(LPCTSTR lpszPageName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszPageName*  
 Ein Zeiger auf eine Zeichenfolge mit der Eigenschaftenseite Namen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CIRC3](../../visual-cpp-samples.md)   
 [MFC-Beispiel TESTHELP](../../visual-cpp-samples.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)

