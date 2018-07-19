---
title: COlePasteSpecialDialog-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
dev_langs:
- C++
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42f4a45dc2b49b784f74175203e892c253ea1f5e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851431"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog-Klasse
Wird für das OLE-Dialogfeld "Inhalte einfügen" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Erstellt ein `COlePasteSpecialDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|Fügt benutzerdefinierte Formate zur Liste der Formate, die Ihre Anwendung einfügen kann.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Fügt einen neuen Eintrag zur Liste der unterstützten Zwischenablageformate an.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Fügt der CF_BITMAP, CF_DIB, CF_METAFILEPICT und optional CF_LINKSOURCE zur Liste der Formate Ihre Anwendung kann einfügen.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Erstellt das Element im Containerdokument mit dem angegebenen Format.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Inhalte einfügen.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Gibt an, ob das Element als ein Symbol oder nicht zu zeichnen.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle der Metadatei zugeordnete Symbol Form dieses Elements ab.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Ruft den Index der Optionen zur Verfügung einfügen, der vom Benutzer ausgewählt wurde.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Ruft den Typ der getroffenen Auswahl ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|Eine Struktur vom Typ OLEUIPASTESPECIAL, die die Funktion des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COlePasteSpecialDialog` Wenn das Dialogfeld aufgerufen werden soll. Nach einem `COlePasteSpecialDialog` -Objekts wird, können Sie mit der [AddFormat](#addformat) und [AddStandardFormats](#addstandardformats) Memberfunktionen zum Hinzufügen von Standardformaten der Zwischenablage in das Dialogfeld. Sie können auch die [M_ps](#m_ps) Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_ps` Struktur des Typs OLEUIPASTESPECIAL ist.  
  
 Weitere Informationen finden Sie unter den [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Struktur im Windows SDK.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="addformat"></a>  COlePasteSpecialDialog::AddFormat  
 Rufen Sie diese Funktion zum Hinzufügen neuer Formate für der Liste der Formate, die Ihre Anwendung in einem Inhalte einfügen-Vorgang unterstützen kann.  
  
```  
void AddFormat(
    const FORMATETC& formatEtc,  
    LPTSTR lpszFormat,  
    LPTSTR lpszResult,  
    DWORD flags);

 
void AddFormat(
    UINT cf,  
    DWORD tymed,  
    UINT nFormatID,  
    BOOL bEnableIcon,  
    BOOL bLink);
```  
  
### <a name="parameters"></a>Parameter  
 *FMT*  
 Verweis auf den Datentyp hinzufügen.  
  
 *lpszFormat*  
 Eine Zeichenfolge, die das Format für den Benutzer beschreibt.  
  
 *lpszResult*  
 Eine Zeichenfolge, die Beschreibung des Ergebnisses, wenn dieses Format im Dialogfeld ausgewählt wird.  
  
 *flags*  
 Die verschiedenen verlinken und Einbetten für dieses Format verfügbaren Optionen. Dieses Flag ist eine bitweise Kombination eines oder mehrere der anderen Werte in der OLEUIPASTEFLAG Enumerationstyp.  
  
 *CF*  
 Das Zwischenablageformat hinzufügen.  
  
 *TYMED*  
 Die Typen der Medien, die im folgenden Format zur Verfügung. Dies ist eine bitweise Kombination eines oder mehrere der Werte in der TYMED Enumerationstyp.  
  
 *nFormatID*  
 Die ID der Zeichenfolge, die dieses Format identifiziert. Das Format dieser Zeichenfolge ist, zwei separate Zeichenfolgen durch eine '\n'-Zeichen voneinander getrennt. Die erste Zeichenfolge ist identisch, die in übergeben werden die *LpstrFormat* -Parameter, und die zweite ist identisch mit der *LpstrResult* Parameter.  
  
 *bEnableIcon*  
 Flag, die bestimmt, ob das als Symbol Kontrollkästchen aktiviert ist, wenn dieses Format in das Listenfeld ausgewählt wird.  
  
 *bLink*  
 Flag, die bestimmt, ob das Optionsfeld "Link einfügen" aktiviert ist, wenn dieses Format in das Listenfeld ausgewählt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion kann aufgerufen werden, zum Hinzufügen von entweder standard-Formate wie z. B. HIERSVR oder CF_TIFF oder benutzerdefinierte Formate, die Ihre Anwendung mit dem System registriert wurden. Weitere Informationen zum Einfügen von Datenobjekten in Ihrer Anwendung, finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter den [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) Enumerationstyp und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter den [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Enumerationstyp im Windows SDK.  
  
##  <a name="addlinkentry"></a>  COlePasteSpecialDialog::AddLinkEntry  
 Fügt einen neuen Eintrag zur Liste der unterstützten Zwischenablageformate an.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Parameter  
 *CF*  
 Das Zwischenablageformat hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Struktur, die die Informationen für den neuen linkeintrag enthält.  
  
##  <a name="addstandardformats"></a>  COlePasteSpecialDialog::AddStandardFormats  
 Rufen Sie diese Funktion, um die Liste der Formate die folgenden Formate der Zwischenablage hinzugefügt, die Ihre Anwendung in einem Inhalte einfügen-Vorgang unterstützen kann:  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bEnableLink*  
 Flag, die bestimmt, ob die Liste der Formate CF_LINKSOURCE Hinzufügen Ihrer Anwendung können einfügen.  
  
### <a name="remarks"></a>Hinweise  
  
- CF_BITMAP  
  
- CF_DIB  
  
- CF_METAFILEPICT  
  
- **"Eingebettetes Objekt"**  
  
-   (optional) **"Quelle verknüpfen"**  
  
 Diese Formate werden verwendet, um einbetten und Verknüpfen zu unterstützen.  
  
##  <a name="colepastespecialdialog"></a>  COlePasteSpecialDialog::COlePasteSpecialDialog  
 Erstellt ein `COlePasteSpecialDialog`-Objekt.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *dwFlags*  
 Flag für Erstellung, enthält eine beliebige Anzahl von den folgenden Flags, die mit dem bitweisen OR-Operator kombiniert werden:  
  
- PSF_SELECTPASTE gibt an, die das Optionsfeld einfügen überprüft zunächst Wenn das Dialogfeld aufgerufen wird. Kann nicht in Kombination mit PSF_SELECTPASTELINK verwendet werden. Dies ist die Standardeinstellung.  
  
- PSF_SELECTPASTELINK gibt an, die das Optionsfeld für die Verknüpfung einfügen überprüft zunächst Wenn das Dialogfeld aufgerufen wird. Kann nicht in Kombination mit PSF_SELECTPASTE verwendet werden.  
  
- PSF_CHECKDISPLAYASICON angibt, das als Symbol Kontrollkästchen wird überprüft, anfänglich Wenn das Dialogfeld aufgerufen wird.  
  
- PSF_SHOWHELP gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
 *pDataObject*  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) zum Einfügen. Wenn dieser Wert NULL ist, ruft es die `COleDataObject` aus der Zwischenablage.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt, nur eine `COlePasteSpecialDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter den [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Enumerationstyp im Windows SDK.  
  
##  <a name="createitem"></a>  COlePasteSpecialDialog::CreateItem  
 Erstellt das neue Element, das das Dialogfeld "Inhalte einfügen" ausgewählt wurde.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pNewItem*  
 Verweist auf eine `COleClientItem` Instanz. Darf nicht NULL sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn das Element erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur aufgerufen werden, nachdem [DoModal](#domodal) IDOK zurückgibt.  
  
##  <a name="domodal"></a>  COlePasteSpecialDialog::DoModal  
 Zeigt das Dialogfeld OLE Inhalte einfügen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) -Funktion in das Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_ps](#m_ps) Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Informationen, die vom Benutzer eingegebene in das Dialogfeld.  
  
##  <a name="getdrawaspect"></a>  COlePasteSpecialDialog::GetDrawAspect  
 Bestimmt, ob der Benutzer hat das ausgewählte Element als Symbol anzuzeigen.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode, die zum Rendern des Objekts erforderlich sind.  
  
- DVASPECT_CONTENT zurückgegeben, wenn das als Symbol Kontrollkästchen nicht überprüft, wenn das Dialogfeld geschlossen wurde.  
  
- DVASPECT_ICON zurückgegeben, wenn das als Symbol Kontrollkästchen aktiviert wurde, wenn das Dialogfeld geschlossen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion nach [DoModal](#domodal) IDOK zurückgibt.  
  
 Weitere Informationen zum Zeichnen der Aspekt, finden Sie unter den [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
##  <a name="geticonicmetafile"></a>  COlePasteSpecialDialog::GetIconicMetafile  
 Ruft ab, der Metadatei, die vom Benutzer ausgewählten Element zugeordnet.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei, die den iconic Aspekt, der das ausgewählte Element enthält, wenn das als Symbol Kontrollkästchen ausgewählt wurde, wenn das Dialogfeld, dazu geschlossen wurde **OK**; andernfalls NULL.  
  
##  <a name="getpasteindex"></a>  COlePasteSpecialDialog::GetPasteIndex  
 Ruft der Indexwert dem Eintrag zugeordneten vom Benutzer ausgewählten.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index im Array von `OLEUIPASTEENTRY` Strukturen, die vom Benutzer ausgewählt wurde. Das Format, das den ausgewählten Index entspricht, sollte verwendet werden, wenn den Einfügevorgang ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter den [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) Struktur im Windows SDK.  
  
##  <a name="getselectiontype"></a>  COlePasteSpecialDialog::GetSelectionType  
 Bestimmt den Typ der Auswahl des Benutzers hergestellt.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der Auswahl getroffen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp Werte angegeben sind die `Selection` Enumerationstyp deklariert wird, der `COlePasteSpecialDialog` Klasse.  
  
```  
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };  
```  
  
 Führen Sie die kurze Desccriptions der folgenden Werte:  
  
- `COlePasteSpecialDialog::pasteLink` Das Optionsfeld "Link einfügen" aktiviert wurde, und das ausgewählte Dateiformat wurde ein OLE-Standardformat.  
  
- `COlePasteSpecialDialog::pasteNormal` Das Optionsfeld einfügen überprüft wurde, und das ausgewählte Dateiformat wurde ein OLE-Standardformat.  
  
- `COlePasteSpecialDialog::pasteOther` Das ausgewählte Format ist kein OLE-Standardformat.  
  
- `COlePasteSpecialDialog::pasteStatic` Das ausgewählte Format war eine Metadatei an.  
  
##  <a name="m_ps"></a>  COlePasteSpecialDialog::m_ps  
 Struktur des Typs OLEUIPASTESPECIAL verwendet zur Steuerung des Verhaltens im Dialogfeld "Inhalte einfügen".  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter den [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
