---
title: Klasse COleConvertDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- COleConvertDialog class
- OLE Convert dialog box
- dialog boxes, OLE
- OLE dialog boxes, Convert
- Convert dialog box
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
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
ms.openlocfilehash: 6db5caf443e7f71c58e2c65b46794c2c9d246d38
ms.lasthandoff: 02/24/2017

---
# <a name="coleconvertdialog-class"></a>COleConvertDialog-Klasse
Weitere Informationen finden Sie unter der [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Erstellt ein `COleConvertDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|Führt die Konvertierung in das Dialogfeld angegeben.|  
|[COleConvertDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Change-Element.|  
|[COleConvertDialog::GetClassID](#getclassid)|Ruft die **CLSID** dem ausgewählten Element zugeordnet.|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Gibt an, ob das Element als ein Symbol zu zeichnen.|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle auf die Metadatei iconic Form dieses Elements zugeordnet.|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Ruft den Typ der getroffenen Auswahl ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Klasse wird von Anwendung Container vom Assistenten generierten Code verwendet.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog  
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
  
- **CF_SELECTACTIVATEAS** gibt an, dass das Optionsfeld aktivieren als anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **CF_SETCONVERTDEFAULT** gibt an, dass die Klasse, deren **CLSID** wird angegeben, indem die **ClsidConvertDefault** Mitglied der `m_cv` Struktur wird als Standardauswahl im Feld verwendet werden, wenn das Konvertieren in Optionsfeld ausgewählt ist.  
  
- **CF_SETACTIVATEDEFAULT** gibt an, dass die Klasse, deren **CLSID** wird angegeben, indem die **ClsidActivateDefault** Mitglied der `m_cv` Struktur wird als Standardauswahl im Feld verwendet werden, wenn das Optionsfeld aktivieren als aktiviert ist.  
  
- **CF_SHOWHELPBUTTON** gibt an, dass die Hilfeschaltfläche angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
 `pClassID`  
 Verweist auf die CLSID des Elements konvertiert oder aktiviert werden. Wenn **NULL**, **CLSID** zugeordneten `pItem` verwendet werden.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, das übergeordnete Fenster des Dialogfelds zum Hauptfenster der Anwendung festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen Sie die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter [CLSID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/ms691424) und [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Struktur.  
  
##  <a name="doconvert"></a>COleConvertDialog::DoConvert  
 Rufen Sie diese Funktion, nach der Rückgabe erfolgreich vom [DoModal](#domodal), entweder um konvertieren oder aktivieren ein Objekt vom Typ [COleClientItem](../../mfc/reference/coleclientitem-class.md).  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Verweist auf das Element konvertiert oder aktiviert werden. Nicht **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Element konvertiert oder aktiviert wird, anhand der Informationen, die vom Benutzer im Dialogfeld "konvertieren" ausgewählt.  
  
##  <a name="domodal"></a>COleConvertDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld OLE konvertieren anzuzeigen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** , wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cv](#m_cv) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.  
  
##  <a name="getclassid"></a>COleConvertDialog::GetClassID  
 Rufen Sie diese Funktion zum Abrufen der **CLSID** dem Element zugeordnete in das Dialogfeld konvertieren ausgewählt wurden.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die **CLSID** Verbindung mit den Elementen, die im Dialogfeld "konvertieren" ausgewählt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen finden Sie unter [CLSID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/ms691424) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdrawaspect"></a>COleConvertDialog::GetDrawAspect  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das ausgewählte Element als Symbol angezeigt hat.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode, die zum Rendern des Objekts erforderlich sind.  
  
- `DVASPECT_CONTENT`Zurückgegeben, wenn das Kontrollkästchen als Symbol nicht aktiviert wurde.  
  
- `DVASPECT_ICON`Zurückgegeben, wenn das Kontrollkästchen als Symbol aktiviert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen zum Zeichnen von Aspekt, finden Sie unter der [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Datenstruktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonicmetafile"></a>COleConvertDialog::GetIconicMetafile  
 Rufen Sie diese Funktion, um ein Handle für die Metadatei abzurufen, die den iconic Aspekt des ausgewählten Elements enthält.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei mit den iconic Aspekt des ausgewählten Elements, wenn das Kontrollkästchen als Symbol wurde aktiviert, wenn das Dialogfeld geschlossen wurde, indem Sie auswählen **OK**andernfalls **NULL**.  
  
##  <a name="getselectiontype"></a>COleConvertDialog::GetSelectionType  
 Rufen Sie diese Funktion, um zu bestimmen, die Art der Konvertierung in das Dialogfeld konvertieren ausgewählt.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Typ der ausgewählten Optionen.  
  
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
  
- **COleConvertDialog::noConversion** zurückgegeben, wenn das Dialogfeld abgebrochen wurde oder der Benutzer keine Konvertierung ausgewählt. Wenn `COleConvertDialog::DoModal` zurückgegebenen **IDOK**, es ist möglich, dass der Benutzer ein anderes Symbol als der zuvor ausgewählten ausgewählt.  
  
- **COleConvertDialog::convertItem** zurückgegeben, wenn das Optionsfeld konvertieren in aktiviert war, aktiviert der Benutzer ein anderes Element zu konvertieren und `DoModal` zurückgegebenen **IDOK**.  
  
- **COleConvertDialog::activateAs** zurückgegeben, wenn das Optionsfeld aktivieren als ausgecheckt wurde, wird der Benutzer ein anderes Element zu aktivieren, ausgewählt und `DoModal` zurückgegebenen **IDOK**.  
  
##  <a name="m_cv"></a>COleConvertDialog::m_cv  
 Struktur des Typs **OLEUICONVERT** verwendet, um das Verhalten des Dialogfelds konvertieren.  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)

