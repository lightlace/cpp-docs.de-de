---
title: COlePasteSpecialDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8680842f0aeeebf98eabc0f278089781290ad902
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[COlePasteSpecialDialog::AddFormat](#addformat)|Die Liste der Formate, die Ihre Anwendung einfügen kann hinzugefügt benutzerdefinierte Formate.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Fügt einen neuen Eintrag zur Liste der unterstützten Zwischenablageformate.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Fügt **CF_BITMAP**, **CF_DIB**, `CF_METAFILEPICT`, und optional `CF_LINKSOURCE` zur Liste der Formate kann Ihre Anwendung einfügen.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Erstellt das Element im Containerdokument mit dem angegebenen Format.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Inhalte einfügen.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Legt fest, ob das Element als ein Symbol oder nicht gezeichnet.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle für die Metadatei Elementsymbol Form dieses Elements zugeordnet.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Ruft den Index der verfügbaren Einfügeoptionen, der vom Benutzer ausgewählt wurde.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Ruft den Typ der getroffenen Auswahl ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|Eine Struktur des Typs **OLEUIPASTESPECIAL** ab, der die Funktion des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COlePasteSpecialDialog` Wenn Sie das Dialogfeld aufgerufen werden soll. Nach einem `COlePasteSpecialDialog` -Objekts können Sie mithilfe der [AddFormat](#addformat) und [AddStandardFormats](#addstandardformats) Memberfunktionen Zwischenablageformate zum Dialogfeld hinzufügen. Sie können auch die [M_ps](#m_ps) Struktur, um die Werte oder Zustände von Steuerelementen in das Dialogfeld zu initialisieren. Die `m_ps` Struktur ist vom Typ **OLEUIPASTESPECIAL**.  
  
 Weitere Informationen finden Sie unter der [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Struktur im Windows SDK.  
  
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
  
##  <a name="addformat"></a>COlePasteSpecialDialog::AddFormat  
 Mit dieser Funktion wird zum Hinzufügen neuer Formate für der Liste der Formate, die Ihre Anwendung in einem Vorgang Inhalte einfügen unterstützen kann.  
  
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
  
 `lpszFormat`  
 Eine Zeichenfolge, die das Format für den Benutzer beschreibt.  
  
 *lpszResult*  
 Eine Zeichenfolge, die Beschreibung des Ergebnisses, wenn dieses Format im Dialogfeld ausgewählt wird.  
  
 `flags`  
 Die anderen verlinken und Einbetten für dieses Format verfügbaren Optionen. Dieses Flag ist eine bitweise Kombination von mindestens einer der anderen Werte in der **OLEUIPASTEFLAG** Aufzählungstyp.  
  
 `cf`  
 Das Format der Zwischenablage hinzufügen.  
  
 *TYMED*  
 Die Typen von Medien in diesem Format verfügbar sind. Dies ist eine bitweise Kombination von mindestens einer der Werte in der **TYMED** Aufzählungstyp.  
  
 `nFormatID`  
 Die ID der Zeichenfolge, die dieses Format bezeichnet. Das Format dieser Zeichenfolge wird zwei separate Zeichenfolgen, die jeweils durch ein "\n" getrennt sind. Die erste Zeichenfolge ist identisch, die im übergeben werden die *LpstrFormat* Parameter und das zweite ist identisch mit der *LpstrResult* Parameter.  
  
 *bEnableIcon*  
 Flag, die bestimmt, ob das Symbol "Anzeige als" Kontrollkästchen aktiviert ist, wenn dieses Format in der Liste ausgewählt ist.  
  
 *bLink*  
 Flag, die bestimmt, ob das Optionsfeld Verknüpfen aktiviert ist, wenn dieses Format in der Liste ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion kann aufgerufen werden, um entweder Standardformaten hinzufügen, z. B. **HIERSVR** oder **CF_TIFF** oder benutzerdefinierte Formate, die Ihre Anwendung mit dem System registriert wurden. Weitere Informationen zum Einfügen von Datenobjekten in Ihrer Anwendung finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) Enumerationstyp und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter der [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Aufzählungstyp im Windows SDK.  
  
##  <a name="addlinkentry"></a>COlePasteSpecialDialog::AddLinkEntry  
 Fügt einen neuen Eintrag zur Liste der unterstützten Zwischenablageformate.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 Das Format der Zwischenablage hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Struktur, die die Informationen für den neuen linkeintrag enthält.  
  
##  <a name="addstandardformats"></a>COlePasteSpecialDialog::AddStandardFormats  
 Rufen Sie diese Funktion, um die folgenden Zwischenablageformate zur Liste der Formate hinzufügen, die Ihre Anwendung in einem Vorgang Inhalte einfügen unterstützen kann:  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bEnableLink*  
 Flag, das bestimmt, ob die hinzuzufügende `CF_LINKSOURCE` zur Liste der Formate kann Ihre Anwendung einfügen.  
  
### <a name="remarks"></a>Hinweise  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **"Eingebettetes Objekt"**  
  
-   (optional) **"Verknüpfung"**  
  
 Diese Formate werden verwendet, um unterstützen das Einbetten von und verknüpfen.  
  
##  <a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog  
 Erstellt ein `COlePasteSpecialDialog`-Objekt.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Erstellung-Flag enthält eine beliebige Anzahl von die folgenden Flags, die mit dem bitweisen OR-Operator kombiniert werden:  
  
- `PSF_SELECTPASTE`Gibt an, dass das Optionsfeld einfügen zunächst geprüft wird, wenn das Dialogfeld aufgerufen wird. Kann nicht verwendet werden, in Kombination mit `PSF_SELECTPASTELINK`. Dies ist die Standardeinstellung.  
  
- `PSF_SELECTPASTELINK`Gibt an, dass die Verknüpfung einfügen Optionsfeld werden zu Beginn aktiviert, wenn das Dialogfeld aufgerufen wird. Kann nicht verwendet werden, in Kombination mit `PSF_SELECTPASTE`.  
  
- `PSF_CHECKDISPLAYASICON`Gibt an, dass das Kontrollkästchen als Symbol zunächst geprüft wird, wenn das Dialogfeld aufgerufen wird.  
  
- `PSF_SHOWHELP`Gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) einfügen. Wenn dieser Wert ist **NULL**, erhält er die `COleDataObject` aus der Zwischenablage.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur bildet eine `COlePasteSpecialDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Aufzählungstyp im Windows SDK.  
  
##  <a name="createitem"></a>COlePasteSpecialDialog::CreateItem  
 Erstellt das neue Element, das im Dialogfeld "Inhalte einfügen" ausgewählt wurde.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pNewItem*  
 Verweist auf eine `COleClientItem` Instanz. Nicht mit **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur aufgerufen werden, nachdem [DoModal](#domodal) gibt **IDOK**.  
  
##  <a name="domodal"></a>COlePasteSpecialDialog::DoModal  
 Zeigt das Dialogfeld OLE Inhalte einfügen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** wird das Dialogfeld erfolgreich angezeigt.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) Funktion im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_ps](#m_ps) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
##  <a name="getdrawaspect"></a>COlePasteSpecialDialog::GetDrawAspect  
 Bestimmt, ob der Benutzer möchte das ausgewählte Element als Symbol anzuzeigen.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode, die zum Rendern des Objekts erforderlich sind.  
  
- `DVASPECT_CONTENT`Zurückgegeben, wenn das Kontrollkästchen als Symbol nicht überprüft wurde, wenn das Dialogfeld geschlossen wurde.  
  
- `DVASPECT_ICON`Zurückgegeben, wenn das Kontrollkästchen als Symbol aktiviert wurde, wenn das Dialogfeld geschlossen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Nur mit dieser Funktion werden nach [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen zum Zeichnen der Aspekt, finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur im Windows SDK.  
  
##  <a name="geticonicmetafile"></a>COlePasteSpecialDialog::GetIconicMetafile  
 Ruft die Verbindung mit den Elementen, die vom Benutzer ausgewählten Metadatei ab.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei, die das Elementsymbol Aspekt des ausgewählten Elements enthält, wenn das Kontrollkästchen als Symbol aktiviert wurde, wenn das Dialogfeld, durch Auswahl geschlossen wurde **OK**andernfalls **NULL**.  
  
##  <a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex  
 Ruft der Indexwert ab dem Eintrag zugeordneten den Benutzer ausgewählt.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index im Array der **OLEUIPASTEENTRY** Strukturen, die vom Benutzer ausgewählt wurde. Das Format aus, das um den ausgewählten Index entspricht, sollte verwendet werden, wenn der Einfügevorgang ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) Struktur im Windows SDK.  
  
##  <a name="getselectiontype"></a>COlePasteSpecialDialog::GetSelectionType  
 Bestimmt den Typ der Auswahl der Benutzer.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der Auswahl.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp Werte werden angegeben, indem die **Auswahl** Enumerationstyp deklariert wird, der `COlePasteSpecialDialog` Klasse.  
  
```  
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };  
```  
  
 Führen Sie die kurze Desccriptions der folgenden Werte:  
  
- **COlePasteSpecialDialog::pasteLink** der verknüpfen Optionsfeld aktiviert wurde und das ausgewählte Format wurde ein OLE-Standardformat.  
  
- **COlePasteSpecialDialog::pasteNormal** der einfügen-Optionsfeld aktiviert wurde und das ausgewählte Format wurde ein OLE-Standardformat.  
  
- **COlePasteSpecialDialog::pasteOther** das ausgewählte Format ist ein OLE-Standardformat.  
  
- **COlePasteSpecialDialog::pasteStatic** das ausgewählte Format wurde eine Metadatei.  
  
##  <a name="m_ps"></a>COlePasteSpecialDialog::m_ps  
 Struktur des Typs **OLEUIPASTESPECIAL** zum Steuern des Verhaltens im Dialogfeld "Inhalte einfügen" verwendet.  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
