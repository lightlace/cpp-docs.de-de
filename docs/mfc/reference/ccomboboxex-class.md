---
title: CComboBoxEx-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
dev_langs:
- C++
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca12ba74df7099aa137e5e7dc9c1b8b75131ab66
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336617"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx-Klasse
Erweitert das Kombinationsfeld-Steuerelement durch die Unterstützung für Bildlisten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Erstellt ein `CComboBoxEx`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|Das Kombinationsfeld erstellt, und fügt es der `CComboBoxEx` Objekt.|  
|[CComboBoxEx::CreateEx](#createex)|Wird ein Kombinationsfeld erstellt, mit der angegebenen erweiterten Windows-Stile und fügt sie an einer `ComboBoxEx` Objekt.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|Entfernt ein Element aus einem `ComboBoxEx` Steuerelement.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Ruft einen Zeiger auf das Kombinationsfeld-Steuerelement untergeordnete ab.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Ruft das Handle für den Bearbeitungsbereich des Steuerelements von einem `ComboBoxEx` Steuerelement.|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile, die in Verwendung sind eine `ComboBoxEx` Steuerelement.|  
|[CComboBoxEx::GetImageList](#getimagelist)|Ruft einen Zeiger auf die Liste der Bilder zugewiesen eine `ComboBoxEx` Steuerelement.|  
|[:: GetItem](#getitem)|Ruft Element zu einem bestimmten `ComboBoxEx` Element.|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Bestimmt, ob der Benutzer den Inhalt des geändert hat die `ComboBoxEx` Steuerelement bearbeiten, indem Sie eingeben.|  
|[CComboBoxEx:: InsertItem](#insertitem)|Fügt ein neues Element in einem `ComboBoxEx` Steuerelement.|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Legt erweiterte Stile in einem `ComboBoxEx` Steuerelement.|  
|[CComboBoxEx:: SetImageList](#setimagelist)|Legt eine Bildliste für eine `ComboBoxEx` Steuerelement.|  
|[CComboBoxEx::SetItem](#setitem)|Legt die Attribute für ein Element in einem `ComboBoxEx` Steuerelement.|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil des erweiterten Kombinationsfeld-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Mithilfe von `CComboBoxEx` zum Kombinationsfeld-Steuerelemente erstellen, Sie nicht mehr ein eigenes Bild Zeichnen von Code implementieren müssen. Verwenden Sie stattdessen `CComboBoxEx` für den Zugriff von Images aus einer Bildliste.  
  
## <a name="image-list-support"></a>Unterstützung von Images  
 Der Besitzer des Kombinationsfelds dient in einem standard-Kombinationsfeld ein Bild zu zeichnen, indem Sie im Kombinationsfeld als Ownerdrawn-Steuerelement zu erstellen. Bei Verwendung von `CComboBoxEx`, Sie müssen nicht die zeichnungsarten CBS_OWNERDRAWFIXED und CBS_HASSTRINGS festgelegt werden, da sie implizit sind. Andernfalls müssen Sie Code zum Ausführen von Zeichenoperationen schreiben. Ein `CComboBoxEx` -Steuerelement unterstützt bis zu drei Images pro Element: eine für den ausgewählten Zustand befindet, eine für nicht ausgewählt und eine für ein Overlaybild.  
  
## <a name="styles"></a>Stile  
 `CComboBoxEx` die Formate CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST und WS_CHILD unterstützt werden. Alle anderen Formate, die übergeben wird, wenn Sie das Fenster zu erstellen, werden vom Steuerelement ignoriert. Nachdem das Fenster erstellt wurde, Sie bieten andere Kombinationsfeld Kasten durch Aufrufen der `CComboBoxEx` Memberfunktion [SetExtendedStyle](#setextendedstyle). Mit diesen Formaten können Sie folgende Aktionen ausführen:  
  
-   Set-Zeichenfolgensuche in der Liste aus, um die Groß-/Kleinschreibung beachtet werden.  
  
-   Erstellen Sie ein Kombinationsfeld-Steuerelement, die den Schrägstrich ("/"), umgekehrter Schrägstrich ("\\"), und Punkt (".") Zeichen als Trennzeichen für Word. Dies ermöglicht Benutzern von Word, Wort wechseln mit der Tastenkombination STRG + Taste.  
  
-   Legen Sie das Kombinationsfeld für den Steuerelement anzeigen oder ein Bild nicht angezeigt. Wenn kein Bild angezeigt wird, kann das Kombinationsfeld den Texteinzug entfernen, der ein Bild aufnehmen kann.  
  
-   Erstellen Sie eine schmale Kombinationsfeld-Steuerelement, einschließlich, seine Größe, sodass sie im Kombinationsfeld breiter schneidet darin enthaltenen.  
  
 Diese Style Flags werden ausführlich in [Verwenden von CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="item-retention-and-callback-item-attributes"></a>Aufbewahrungszeit und Rückrufattribute-Element  
 Elementinformationen, wie z. B. Indizes, die für Elemente und Bilder, Werte für die Einzüge und Textzeichenfolgen, befindet sich in der Struktur Win32 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746), wie im Windows SDK beschrieben. Die Struktur enthält auch Member, die Rückruf-Flags entsprechen.  
  
 Eine Erläuterung der ausführliche und konzeptionelle Ebene, finden Sie unter [Verwenden von CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx  
 Rufen Sie diese Memberfunktion zum Erstellen einer `CComboBoxEx` Objekt.  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>  CComboBoxEx::Create  
 Das Kombinationsfeld erstellt, und fügt es der `CComboBoxEx` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *dwStyle*  
 Gibt die Kombination von kombinationsfeldformate angewendet werden, auf das Kombinationsfeld an. Finden Sie unter **"Hinweise"** unten für Weitere Informationen zu Stilen.  
  
 *Rect*  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Position und Größe des Kombinationsfelds ist.  
  
 *pParentWnd*  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Kombinationsfelds ist (in der Regel eine `CDialog`). Es darf nicht NULL sein.  
  
 *nID*  
 Gibt an, das Kombinationsfeld-Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Objekt wurde erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie eine `CComboBoxEx` Objekt in zwei Schritten:  
  
1.  Rufen Sie [CComboBoxEx](#ccomboboxex) zum Erstellen einer `CComboBoxEx` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die im erweiterten Windows-Kombinationsfeld erstellt, und fügt es der `CComboBoxEx` Objekt.  
  
 Beim Aufruf `Create`, MFC, initialisiert die allgemeinen Steuerelemente angezeigt.  
  
 Wenn Sie im Kombinationsfeld erstellen, können Sie einige oder alle der folgenden kombinationsfeldstile angeben:  
  
- CBS_SIMPLE  
  
- CBS_DROPDOWN  
  
- CBS_DROPDOWNLIST  
  
- CBS_AUTOHSCROLL  
  
- WS_CHILD  
  
 Alle anderen Formate, die übergeben wird, wenn Sie das Fenster zu erstellen, werden ignoriert. Die `ComboBoxEx` -Steuerelement unterstützt auch die erweiterten Stile, die zusätzliche Funktionen bereitstellen. Diese Formate werden in beschrieben [ComboBoxEx steuern Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb775742), im Windows SDK. Legen Sie durch Aufrufen dieser Stile [SetExtendedStyle](#setextendedstyle).  
  
 Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von `Create`.  
  
##  <a name="createex"></a>  CComboBoxEx::CreateEx  
 Mit dieser Funktion wird zum Erstellen eines erweiterten Kombinationsfeld-Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CComboBoxEx` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *dwExStyle*  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Windows-Stile, finden Sie unter den *DwExStyle* -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 *dwStyle*  
 Das Kombinationsfeld-Steuerelement Stil. Finden Sie unter [erstellen](#create) für eine Liste der Formate.  
  
 *Rect*  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.  
  
 *pParentWnd*  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 *nID*  
 Der ID des Steuerelements untergeordneten Fensters mit.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von `Create` anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.  
  
 `CreateEx` erstellt das Steuerelement mit den erweiterten Windows-Formatvorlagen, die anhand des *DwExStyle*. Sie müssen Erweiterte Stile bestimmten festlegen, auf ein Steuerelement mit erweiterten Kombinationsfeld Feld [SetExtendedStyle](#setextendedstyle). Verwenden Sie z. B. `CreateEx` solche Stile als WS_EX_CONTEXTHELP festgelegt, aber verwenden Sie `SetExtendedStyle` solche Stile als CBES_EX_CASESENSITIVE festgelegt. Weitere Informationen finden Sie die Stile, die in diesem Thema beschriebenen [Erweiterte Stile der ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775742) im Windows SDK.  
  
##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem  
 Entfernt ein Element aus einem `ComboBoxEx` Steuerelement.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *iIndex*  
 Nullbasierte Index des Elements, das entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Steuerelement Verbleibend. Wenn *iIndex* ist ungültig, die Funktion gibt CB_ERR.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768), wie im Windows SDK beschrieben. Wenn Sie DeleteItem, Aufrufen einer [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachricht CBEN_DELETEITEM-Benachrichtigung an das übergeordnete Fenster gesendet.  
  
##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf ein Kombinationsfeld-Steuerelement in einem `CComboBoxEx` Objekt.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CComboBox` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CComboBoxEx` -Steuerelement besteht aus einem übergeordneten Fenster, das kapselt einen `CComboBox`.  
  
 Die `CComboBox` Objekt der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf das Steuerelement zum Bearbeiten für ein Kombinationsfeld.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CEdit](../../mfc/reference/cedit-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CComboBoxEx` Steuerelement verwendet ein Bearbeitungsfeld, wenn sie mit der Formatvorlage CBS_DROPDOWN erstellt wird.  
  
 Die `CEdit` Objekt der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle  
 Diese Memberfunktion rufen Sie die erweiterten Stile, die zum Aufrufen einer `CComboBoxEx` Steuerelement.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der DWORD-Wert, der die erweiterten Stile enthält, die für das Kombinationsfeld-Steuerelement verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Erweiterte Stile der ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775742) im Windows SDK für Weitere Informationen zu dieser Stile.  
  
##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf die Liste der Bilder ein, die eine `CComboBoxEx` Steuerelement.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt. Wenn ein Fehler auftritt, gibt diese Member-Funktion NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die `CImageList` Objekt der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="getitem"></a>  :: GetItem  
 Ruft Element zu einem bestimmten `ComboBoxEx` Element.  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pCBItem*  
 Ein Zeiger auf eine [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) -Struktur, die die Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779), wie im Windows SDK beschrieben.  
  
##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged  
 Bestimmt, ob der Benutzer den Inhalt des geändert hat die `ComboBoxEx` Steuerelement bearbeiten, indem Sie eingeben.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Benutzer im Bearbeitungsfeld des Steuerelements eingegeben hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782), wie im Windows SDK beschrieben.  
  
##  <a name="insertitem"></a>  CComboBoxEx:: InsertItem  
 Fügt ein neues Element in einem `ComboBoxEx` Steuerelement.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pCBItem*  
 Ein Zeiger auf eine [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) -Struktur, die die Informationen zu erhalten. Diese Struktur enthält die Rückruf-Flagwerte für das Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index, an dem das neue Element im Erfolgsfall eingefügt wurde; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufruf `InsertItem`, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) -Nachricht mit [CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764) Benachrichtigung wird an das übergeordnete Fenster gesendet werden.  
  
##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle  
 Rufen Sie diese Memberfunktion, um die erweiterten Stile verwendet, die für ein Kombinationsfeld, das erweiterte Steuerelement festzulegen.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Parameter  
 *dwExMask*  
 Ein DWORD-Wert, der gibt an, welche Formate in *DwExStyles* betroffen sind. Nur die erweiterten Stile in *DwExMask* wird geändert. Alle anderen Formate werden unverändert beibehalten. Wenn dieser Parameter 0 (null), und klicken Sie dann alle Formatvorlagen in *DwExStyles* wirkt sich auf.  
  
 *dwExStyles*  
 Ein DWORD-Wert, der das Kombinationsfeld-Steuerelement enthält erweiterte Stile für das Steuerelement festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine DWORD-Wert, der die erweiterten Stile, die zuvor verwendet, für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Erweiterte Stile der ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775742) im Windows SDK für Weitere Informationen zu dieser Stile.  
  
 Verwenden Sie zum Erstellen ein Kombinationsfeld-Steuerelement mit erweiterten Fensterstile erweiterte [CreateEx](#createex).  
  
##  <a name="setimagelist"></a>  CComboBoxEx:: SetImageList  
 Legt eine Bildliste für eine `ComboBoxEx` Steuerelement.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 *pImageList*  
 Ein Zeiger auf eine `CImageList` Objekt mit den Bildern für die Verwendung mit der `CComboBoxEx` Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, das die zuvor vom verwendeten Images enthält die `CComboBoxEx` Steuerelement. NULL, wenn keine Bildliste zuvor festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787), wie im Windows SDK beschrieben. Wenn Sie die Höhe des Standard-Edit-Steuerelements ändern, rufen Sie die Win32-Funktion [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Ihres Steuerelements ändern der Größe nach dem Aufruf von `SetImageList`, oder es wird nicht korrekt angezeigt.  
  
 Die `CImageList` Objekt der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="setitem"></a>  CComboBoxEx::SetItem  
 Legt die Attribute für ein Element in einem `ComboBoxEx` Steuerelement.  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pCBItem*  
 Ein Zeiger auf eine [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) -Struktur, die die Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788), wie im Windows SDK beschrieben.  
  
##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme  
 Legt den visuellen Stil des erweiterten Kombinationsfeld-Steuerelement fest.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 *pszSubAppName*  
 Ein Zeiger auf eine Unicode-Zeichenfolge mit den erweiterten Kombinationsfeld Feld visuellen Stil festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) Nachricht, wie im Windows SDK beschrieben.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel-MFCIE](../../visual-cpp-samples.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)
