---
title: Klasse COlePasteSpecialDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- Paste Special dialog box
- dialog boxes, Paste Special
- OLE Paste Special dialog box
- COlePasteSpecialDialog class
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
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
ms.openlocfilehash: 6984d714248815b062c564c7eed5c315990855af
ms.lasthandoff: 02/24/2017

---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog-Klasse
Wird für das OLE-Dialogfeld "Inhalte einfügen" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Erstellt ein `COlePasteSpecialDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|Die Liste der Formate, die Ihre Anwendung einfügen kann hinzugefügt benutzerdefinierte Formate.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Fügt einen neuen Eintrag zur Liste der unterstützten Formate der Zwischenablage.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Fügt **CF_BITMAP**, **CF_DIB**, `CF_METAFILEPICT`, und optional `CF_LINKSOURCE` in der Liste der Formate Ihrer Anwendung einfügen kann.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Erstellt das Element im Containerdokument mit dem angegebenen Format.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE einfügen.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Legt fest, ob das Element als ein Symbol oder nicht gezeichnet.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle auf die Metadatei iconic Form dieses Elements zugeordnet.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Ruft den Index der verfügbaren Einfügen-Optionen, der vom Benutzer ausgewählt wurde.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Ruft den Typ der getroffenen Auswahl ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|Eine Struktur vom Typ **OLEUIPASTESPECIAL** , die die Funktion des Dialogfelds gesteuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COlePasteSpecialDialog` Wenn Sie dieses Dialogfeld aufrufen möchten. Nach einer `COlePasteSpecialDialog` -Objekts, können Sie die [AddFormat](#addformat) und [AddStandardFormats](#addstandardformats) Memberfunktionen des Dialogfelds Zwischenablageformate hinzu. Sie können auch die [M_ps](#m_ps) Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_ps` Struktur ist vom Typ **OLEUIPASTESPECIAL**.  
  
 Weitere Informationen finden Sie unter der [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="addformat"></a>COlePasteSpecialDialog::AddFormat  
 Rufen Sie diese Funktion zum Hinzufügen neuer Formate für der Liste der Formate, die Ihre Anwendung in einem einfügen-Vorgang unterstützt.  
  
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
 Verweis auf den Datentyp hinzu.  
  
 `lpszFormat`  
 Eine Zeichenfolge, die das Format für den Benutzer beschreibt.  
  
 *lpszResult*  
 Eine Zeichenfolge, die das Ergebnis beschrieben, wenn dieses Format im Dialogfeld ausgewählt wird.  
  
 `flags`  
 Die verschiedenen verknüpfen und Einbetten von Optionen für dieses Format zur Verfügung. Dieses Flag ist eine Kombination aus einem oder mehreren der anderen Werte in der **OLEUIPASTEFLAG** Enumerationstyps.  
  
 `cf`  
 Das Format der Zwischenablage hinzu.  
  
 *TYMED*  
 Die Typen von Medien in diesem Format verfügbar sind. Dies ist eine bitweise Kombination von mindestens einem der Werte in der **TYMED** Enumerationstyps.  
  
 `nFormatID`  
 Die ID der Zeichenfolge, die dieses Format identifiziert. Das Format dieser Zeichenfolge ist zwei separate Zeichenfolgen, die durch ein '\n'-Zeichen getrennt. Die erste Zeichenfolge entspricht, die übergeben werden würde die *LpstrFormat* -Parameter, und der zweite ist identisch mit der *LpstrResult* Parameter.  
  
 *bEnableIcon*  
 Flag, die bestimmt, ob das Kontrollkästchen als Symbol aktiviert ist, wenn dieses Format im Listenfeld ausgewählt wird.  
  
 *bLink*  
 Flag, die bestimmt, ob das Optionsfeld Verknüpfen aktiviert ist, wenn dieses Format im Listenfeld ausgewählt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion kann aufgerufen werden, um entweder Standardformate hinzufügen, z. B. **CF_TEXT** oder **CF_TIFF** oder benutzerdefinierte Formate, die Ihre Anwendung mit dem System registriert wurden. Weitere Informationen zum Einfügen von Datenobjekten in Ihrer Anwendung finden Sie im Artikel [Datenobjekte und Datenquellen: Bearbeitung](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Weitere Informationen finden Sie unter der [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) Enumerationstyp und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter der [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Enumerationstyps in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="addlinkentry"></a>COlePasteSpecialDialog::AddLinkEntry  
 Fügt einen neuen Eintrag zur Liste der unterstützten Formate der Zwischenablage.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 Das Format der Zwischenablage hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) -Struktur, die Informationen für den neuen linkeintrag enthält.  
  
##  <a name="addstandardformats"></a>COlePasteSpecialDialog::AddStandardFormats  
 Rufen Sie diese Funktion, um die folgenden Formate der Zwischenablage in die Liste der Formate hinzufügen, die Ihre Anwendung in einem einfügen-Vorgang unterstützt:  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bEnableLink*  
 Flag, das bestimmt, ob die hinzuzufügenden `CF_LINKSOURCE` in der Liste der Formate Ihrer Anwendung einfügen kann.  
  
### <a name="remarks"></a>Hinweise  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **"Eingebettetes Objekt"**  
  
-   (optional) **"Verknüpfung"**  
  
 Diese Formate werden zur Unterstützung von einbetten und Verknüpfen von verwendet.  
  
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
 Erstellung-Flag enthält eine beliebige Anzahl von die folgenden Flags, die mit dem bitweisen OR-Operator kombiniert:  
  
- `PSF_SELECTPASTE`Gibt an, dass das Optionsfeld einfügen wird zunächst überprüft werden, wenn das Dialogfeld aufgerufen wird. Kann nicht verwendet werden, in Kombination mit `PSF_SELECTPASTELINK`. Dies ist die Standardeinstellung.  
  
- `PSF_SELECTPASTELINK`Gibt an, dass das Optionsfeld werden verknüpfen anfänglich aktiviert, wenn das Dialogfeld aufgerufen wird. Kann nicht verwendet werden, in Kombination mit `PSF_SELECTPASTE`.  
  
- `PSF_CHECKDISPLAYASICON`Gibt an, dass das Kontrollkästchen als Symbol wird zunächst überprüft werden, wenn das Dialogfeld aufgerufen wird.  
  
- `PSF_SHOWHELP`Gibt an, dass die Hilfeschaltfläche angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
 `pDataObject`  
 Verweist auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) einfügen. Wenn dieser Wert **NULL**, ruft es die `COleDataObject` aus der Zwischenablage.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, das übergeordnete Fenster des Dialogfelds zum Hauptfenster der Anwendung festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Nur diese Funktion erstellt ein `COlePasteSpecialDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen Sie die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) Enumerationstyps in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createitem"></a>COlePasteSpecialDialog::CreateItem  
 Erstellt das neue Element, das im Dialogfeld "Inhalte einfügen" ausgewählt wurde.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pNewItem*  
 Verweist auf eine `COleClientItem` Instanz. Nicht **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur aufgerufen werden, nachdem [DoModal](#domodal) gibt **IDOK**.  
  
##  <a name="domodal"></a>COlePasteSpecialDialog::DoModal  
 Zeigt das Dialogfeld OLE einfügen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** , wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_ps](#m_ps) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
##  <a name="getdrawaspect"></a>COlePasteSpecialDialog::GetDrawAspect  
 Bestimmt, ob der Benutzer das ausgewählte Element als Symbol angezeigt hat.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode, die zum Rendern des Objekts erforderlich sind.  
  
- `DVASPECT_CONTENT`Zurückgegeben, wenn das Kontrollkästchen als Symbol nicht überprüft wurde, wenn das Dialogfeld geschlossen wurde.  
  
- `DVASPECT_ICON`Zurückgegeben, wenn das Kontrollkästchen als Symbol aktiviert wurde, wenn das Dialogfeld geschlossen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion nach [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen zum Zeichnen von Aspekt, finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonicmetafile"></a>COlePasteSpecialDialog::GetIconicMetafile  
 Ruft die Metadatei, die vom Benutzer ausgewählten Element zugeordnet.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei mit den iconic Aspekt des ausgewählten Elements, wenn das Kontrollkästchen als Symbol ausgewählt wurde, wenn das Dialogfeld, durch Auswahl geschlossen wurde **OK**andernfalls **NULL**.  
  
##  <a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex  
 Ruft der Indexwert dem Eintrag zugeordneten ausgewählt wurden.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index im Array von **OLEUIPASTEENTRY** -Strukturen, die vom Benutzer ausgewählt wurde. Das Format, das dem ausgewählten Index entspricht sollte verwendet werden, wenn den Einfügevorgang ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
 Weitere Informationen finden Sie unter der [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)

