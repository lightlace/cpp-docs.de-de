---
title: COleInsertDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aaf60141747f1ff1db2256815f24e6708307ab7
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042169"
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog-Klasse
Wird für das OLE-Dialogfeld "Objekt einfügen" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Erstellt ein `COleInsertDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](#createitem)|Erstellt im Dialogfeld ausgewählten Elements an.|  
|[COleInsertDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Objekt einfügen.|  
|[COleInsertDialog::GetClassID](#getclassid)|Ruft die **CLSID** dem ausgewählten Element zugeordnet sind.|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Legt fest, ob das Element als Symbol gezeichnet werden soll.|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle für die Metadatei Elementsymbol Form dieses Elements zugeordnet.|  
|[COleInsertDialog::GetPathName](#getpathname)|Ruft den vollständigen Pfad zu der Sie im Dialogfeld ausgewählte Datei ab.|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Ruft den Typ des ausgewählten Objekts ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|Eine Struktur des Typs **OLEUIINSERTOBJECT** , steuert das Verhalten des Dialogfelds.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleInsertDialog` Wenn Sie das Dialogfeld aufgerufen werden soll. Nach einem `COleInsertDialog` -Objekts können Sie mithilfe der [M_io](#m_io) Struktur initialisiert werden, die Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_io` Struktur ist vom Typ **OLEUIINSERTOBJECT**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Memberfunktion.  
  
> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.  
  
 Weitere Informationen finden Sie unter der [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) Struktur im Windows SDK.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog  
 Diese Funktion nur bildet eine `COleInsertDialog` Objekt.  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *dwFlags*  
 Erstellung-Flag, die einer beliebigen Anzahl von die folgenden Werte hinzu, mit dem bitweisen OR-Operator kombiniert werden:  
  
- **IOF_SHOWHELP** gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_SELECTCREATENEW** gibt an, dass die neu erstellen Optionsfeld anfänglich aktiviert sein wird, wenn das Dialogfeld aufgerufen wird. Dies ist der Standardwert und kann nicht verwendet werden, mit **IOF_SELECTCREATEFROMFILE**.  
  
- **IOF_SELECTCREATEFROMFILE** gibt an, dass das Optionsfeld aus Datei erstellen zunächst ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Kann nicht verwendet werden, mit **IOF_SELECTCREATENEW**.  
  
- **IOF_CHECKLINK** gibt an, dass das Kontrollkästchen links zunächst geprüft wird, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_DISABLELINK** gibt an, dass das Kontrollkästchen links deaktiviert wird, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_CHECKDISPLAYASICON** gibt an, die das Kontrollkästchen als Symbol wird anfänglich überprüft werden, wird das aktuelle Symbol angezeigt werden und die Schaltfläche "Symbol ändern" wird aktiviert, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_VERIFYSERVERSEXIST** gibt an, dass das Dialogfeld überprüfen soll, der Klassen werden hinzugefügt, in das Listenfeld sicherstellen, dass der in der Registrierungsdatenbank angegebenen Server vorhanden sind, bevor Sie das Dialogfeld angezeigt wird. Dieses Flag kann die Leistung erheblich beeinträchtigen.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster eines jedoch stattdessen das Dialogfeld auf das Hauptanwendungsfenster festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
##  <a name="createitem"></a>  COleInsertDialog::CreateItem  
 Mit dieser Funktion können Sie ein Objekt des Typs erstellen [COleClientItem](../../mfc/reference/coleclientitem-class.md) nur, wenn [DoModal](#domodal) gibt **IDOK**.  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pItem*  
 Verweist auf das Element erstellt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen außerdem Zuordnen der `COleClientItem` -Objekt, bevor Sie diese Funktion aufrufen können.  
  
##  <a name="domodal"></a>  COleInsertDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld OLE Objekt einfügen anzuzeigen.  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwFlags*  
 Einer der folgenden Werte:  
  
 `COleInsertDialog::DocObjectsOnly` Fügt nur DocObjects an.  
  
 `COleInsertDialog::ControlsOnly` Fügt ein nur-ActiveX-Steuerelemente.  
  
 0 (null) Fügt DocObject weder ein ActiveX-Steuerelement. Dieser Wert führt dieselbe Implementierung als erste Prototyp oben aufgeführten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
-   IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
-   IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
-   IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIInsertObject](http://msdn.microsoft.com/library/windows/desktop/ms694325) Funktion im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_io](#m_io) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder der Eingabe von Informationen in das Dialogfeld vom Benutzer.  
  
##  <a name="getclassid"></a>  COleInsertDialog::GetClassID  
 Mit dieser Funktion wird zum Abrufen der **CLSID** nur, wenn das ausgewählte Element zugeordneten [DoModal](#domodal) gibt **IDOK** und der Auswahltyp **COleInsertDialog:: CreateNewItem**.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die **CLSID** mit dem ausgewählten Element verknüpft sind.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) im Windows SDK.  
  
##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte das ausgewählte Element als Symbol anzuzeigen.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode, die zum Rendern des Objekts erforderlich sind.  
  
- `DVASPECT_CONTENT` Zurückgegeben, wenn das Kontrollkästchen für die Anzeige als Symbol nicht aktiviert wurde.  
  
- `DVASPECT_ICON` Zurückgegeben, wenn das Kontrollkästchen für die Anzeige als Symbol aktiviert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion nur, wenn [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen zum Zeichnen der Aspekt, finden Sie unter [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Datenstruktur im Windows SDK.  
  
##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile  
 Mit dieser Funktion können Sie ein Handle für die Metadatei abzurufen, die das Elementsymbol Aspekt des ausgewählten Elements enthält.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei, die das Elementsymbol Aspekt des ausgewählten Elements enthält, wenn das Kontrollkästchen als Symbol wurde überprüft, wenn das Dialogfeld geschlossen wurde, indem Sie auswählen **OK**andernfalls **NULL**.  
  
##  <a name="getpathname"></a>  COleInsertDialog::GetPathName  
 Mit dieser Funktion wird zum Abrufen des vollständigen Pfads des ausgewählten Datei nur, wenn [DoModal](#domodal) gibt **IDOK** und der Auswahltyp nicht **COleInsertDialog::createNewItem**.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vollständige Pfad, die im Dialogfeld ausgewählte Datei. Wenn der Auswahltyp ist `createNewItem`, diese Funktion gibt eine bedeutungslos `CString` im Releasemodus oder verursacht eine Assertion im Debugmodus befindet.  
  
##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType  
 Mit dieser Funktion wird zum Abrufen des Auswahltyps ausgewählt wird, wenn das Dialogfeld "Objekt einfügen" durch Auswahl verworfen wurde **OK**.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Typ der Auswahl.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp Werte werden angegeben, indem die **Auswahl** Enumerationstyp deklariert wird, der `COleInsertDialog` Klasse.  
  
```  
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };  
```  
  
 Führen Sie die kurze Beschreibungen der folgenden Werte:  
  
- **COleInsertDialog::createNewItem** das Erstellen neuer Optionsfeld aktiviert wurde.  
  
- **COleInsertDialog::insertFromFile** das Erstellen von Datei-Optionsfeld aktiviert wurde, und aktivieren Sie das Kontrollkästchen links nicht aktiviert wurde.  
  
- **COleInsertDialog::linkToFile** das Erstellen von Datei-Optionsfeld aktiviert wurde und das Kontrollkästchen "Link" aktiviert wurde.  
  
##  <a name="m_io"></a>  COleInsertDialog::m_io  
 Struktur des Typs **OLEUIINSERTOBJECT** zum Steuern des Verhaltens im Dialogfeld "Objekt einfügen" verwendet.  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können weder direkt noch über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
