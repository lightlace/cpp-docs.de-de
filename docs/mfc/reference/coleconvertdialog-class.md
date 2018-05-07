---
title: COleConvertDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs:
- C++
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90453d4e8550038493545b691c978b59bda90fad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog-Klasse
Weitere Informationen finden Sie unter der [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Struktur im Windows SDK.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Erstellt ein `COleConvertDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|Führt die Konvertierung in das Dialogfeld angegeben.|  
|[COleConvertDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Change-Element.|  
|[COleConvertDialog::GetClassID](#getclassid)|Ruft die **CLSID** dem ausgewählten Element zugeordnet sind.|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Gibt an, ob das Element als ein Symbol gezeichnet werden soll.|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle für die Metadatei Elementsymbol Form dieses Elements zugeordnet.|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Ruft den Typ der getroffenen Auswahl ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog  
 Erstellt nur eine `COleConvertDialog` Objekt.  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Verweist auf das Element konvertiert oder aktiviert werden.  
  
 `dwFlags`  
 Erstellung-Flag, das eine beliebige Anzahl von die folgenden Werte enthält kombiniert mit dem bitweisen- or -Operator:  
  
- **CF_SELECTCONVERTTO** gibt an, dass das Optionsfeld konvertieren in anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung.  
  
- **CF_SELECTACTIVATEAS** gibt an, dass das Optionsfeld aktivieren als ursprünglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **CF_SETCONVERTDEFAULT** gibt an, dass die Klasse, deren **CLSID** wird angegeben, indem die **ClsidConvertDefault** Mitglied der `m_cv` Struktur als Standardauswahl verwendet werden in der Liste der Klasse wird beim Konvertieren in Optionsfeld aktiviert.  
  
- **CF_SETACTIVATEDEFAULT** gibt an, dass die Klasse, deren **CLSID** wird angegeben, indem die **ClsidActivateDefault** Mitglied der `m_cv` Struktur wird als Standard verwendet werden die Auswahl im Feld Klassenliste, wenn das Optionsfeld aktivieren als ausgewählt ist.  
  
- **CF_SHOWHELPBUTTON** gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
 `pClassID`  
 Verweist auf die CLSID des Elements, das konvertiert oder aktiviert werden. Wenn **NULL**, **CLSID** zugeordneten `pItem` verwendet werden.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) und [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Struktur.  
  
##  <a name="doconvert"></a>  COleConvertDialog::DoConvert  
 Mit dieser Funktion werden, nach der Rückgabe erfolgreich vom [DoModal](#domodal), konvertieren oder aktivieren Sie ein Objekt des Typs [COleClientItem](../../mfc/reference/coleclientitem-class.md).  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Verweist auf das Element konvertiert oder aktiviert werden. Nicht mit **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Element wird konvertiert oder anhand der Informationen, die vom Benutzer im Dialogfeld "konvertieren" ausgewählten aktiviert.  
  
##  <a name="domodal"></a>  COleConvertDialog::DoModal  
 Mit dieser Funktion können im konvertiert OLE-Dialogfeld angezeigt.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** wird das Dialogfeld erfolgreich angezeigt.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) Funktion im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cv](#m_cv) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder der Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.  
  
##  <a name="getclassid"></a>  COleConvertDialog::GetClassID  
 Mit dieser Funktion wird zum Abrufen der **CLSID** Verbindung mit den Elementen den Benutzer das Dialogfeld "konvertieren" ausgewählt.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die **CLSID** Verbindung mit den Elementen, die im Dialogfeld "konvertieren" ausgewählt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach dem Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) im Windows SDK.  
  
##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte das ausgewählte Element als Symbol anzuzeigen.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode, die zum Rendern des Objekts erforderlich sind.  
  
- `DVASPECT_CONTENT` Zurückgegeben, wenn das Kontrollkästchen für die Anzeige als Symbol nicht aktiviert wurde.  
  
- `DVASPECT_ICON` Zurückgegeben, wenn das Kontrollkästchen für die Anzeige als Symbol aktiviert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach dem Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen zum Zeichnen der Aspekt, finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Datenstruktur im Windows SDK.  
  
##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile  
 Mit dieser Funktion können Sie ein Handle für die Metadatei abzurufen, die das Elementsymbol Aspekt des ausgewählten Elements enthält.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei, die das Elementsymbol Aspekt des ausgewählten Elements enthält, wenn das Kontrollkästchen als Symbol wurde überprüft, wenn das Dialogfeld geschlossen wurde, indem Sie auswählen **OK**andernfalls **NULL**.  
  
##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType  
 Mit dieser Funktion können Sie bestimmen die Art der Konvertierung in das Dialogfeld "konvertieren" ausgewählt.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Typ der Auswahl.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp Werte werden angegeben, indem die **Auswahl** Enumerationstyp deklariert wird, der `COleConvertDialog` Klasse.  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 Führen Sie die kurze Beschreibungen der folgenden Werte:  
  
- **COleConvertDialog::noConversion** zurückgegeben, wenn das Dialogfeld abgebrochen wurde oder Auswahl des Benutzers keine Konvertierung. Wenn `COleConvertDialog::DoModal` zurückgegebene **IDOK**, es ist möglich, dass der Benutzer ein anderes Symbol als an denjenigen, die zuvor ausgewählte ausgewählt.  
  
- **COleConvertDialog::convertItem** zurückgegeben, wenn das Konvertieren in Optionsfeld aktiviert wurde, wird der Benutzer ein anderes Element konvertiert, ausgewählt und `DoModal` zurückgegebene **IDOK**.  
  
- **COleConvertDialog::activateAs** zurückgegeben, wenn das Optionsfeld aktivieren als aktiviert wurde, wird der Benutzer ein anderes Element für die Aktivierung, ausgewählt und `DoModal` zurückgegebene **IDOK**.  
  
##  <a name="m_cv"></a>  COleConvertDialog::m_cv  
 Struktur des Typs **OLEUICONVERT** zum Steuern des Verhaltens des Dialogfelds Convert verwendet.  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können weder direkt noch über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
