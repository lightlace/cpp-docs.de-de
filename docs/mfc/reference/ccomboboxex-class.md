---
title: CComboBoxEx-Klasse | Microsoft Docs
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
ms.openlocfilehash: fd7d2c5bbd3445e604620dc1f23f45004b7a3b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|[CComboBoxEx::Create](#create)|Erstellt das Kombinationsfeld und fügt es der `CComboBoxEx` Objekt.|  
|[CComboBoxEx::CreateEx](#createex)|Erstellt ein Kombinationsfeld mit der angegebenen erweiterten Fensterstile und fügt es einer **ComboBoxEx** Objekt.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|Entfernt ein Element aus einem **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Ruft einen Zeiger auf ein Kombinationsfeld-Steuerelement untergeordnete ab.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Ruft das Handle für den Bearbeitungsbereich des Steuerelements des eine **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile, die für in Gebrauch sind eine **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::GetImageList](#getimagelist)|Ruft einen Zeiger auf die Bildliste zugewiesene eine **ComboBoxEx** Steuerelement.|  
|[:: GetItem](#getitem)|Ruft die Elementinformationen für einen bestimmten **ComboBoxEx** Element.|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Bestimmt, ob der Benutzer den Inhalt der geänderten der **ComboBoxEx** Steuerelement bearbeiten, indem Sie eingeben.|  
|[CComboBoxEx:: InsertItem](#insertitem)|Fügt ein neues Element in einem **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile, die innerhalb einer **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx:: SetImageList](#setimagelist)|Legt eine Bildliste für eine **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::SetItem](#setitem)|Legt die Attribute für ein Element in einem **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil der erweiterten Kombinationsfeld-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Mithilfe von `CComboBoxEx` zum Kombinationsfeld-Steuerelemente erstellen, Sie nicht mehr benötigen Ihr eigenes Image zeichnen Code implementieren. Verwenden Sie stattdessen `CComboBoxEx` um den Zugriff von Bildern aus einer Bildliste.  
  
## <a name="image-list-support"></a>Unterstützung für Image-Liste  
 In einem standard-Kombinationsfeld ist der Besitzer des Kombinationsfelds verantwortlich für ein Bild zu zeichnen, indem Sie im Kombinationsfeld als Besitzer gezeichnetes Steuerelement erstellen. Bei Verwendung von `CComboBoxEx`, Sie müssen nicht die zeichnungsarten festzulegende **CBS_OWNERDRAWFIXED** und **CBS_HASSTRINGS** , da sie implizit sind. Andernfalls müssen Sie Code zum Ausführen von Vorgängen zeichnen schreiben. Ein `CComboBoxEx` Steuerelement unterstützt bis zu drei Images pro Element: eine für einen ausgewählten Zustand, nicht ausgewählt und ein Overlaybild.  
  
## <a name="styles"></a>Stile  
 `CComboBoxEx` unterstützt die Stile **CBS_SIMPLE**, **CBS_DROPDOWN**, **CBS_DROPDOWNLIST**, und **WS_CHILD**. Alle anderen Formate, die übergeben wird, wenn Sie das Fenster erstellen, werden vom Steuerelement ignoriert. Nachdem das Fenster erstellt wurde, Sie bieten andere Kombinationsfeld Kasten durch Aufrufen der `CComboBoxEx` Memberfunktion [SetExtendedStyle](#setextendedstyle). Mit diesen Formaten können Sie folgende Aktionen ausführen:  
  
-   Set-Zeichenfolgensuche in der Liste aus, um die Groß-/Kleinschreibung beachtet werden.  
  
-   Erstellen Sie ein Kombinationsfeld-Steuerelement, der mit den Schrägstrich ('/'), umgekehrter Schrägstrich ("\\"), und Punkt ('. ') Zeichen als Trennzeichen für Word. Dies können Benutzer aus einem Wort zum nächsten zu wechseln, mit der Tastenkombination STRG + Pfeiltaste.  
  
-   Legen Sie das Kombinationsfeld für den Steuerelement anzeigen oder ein Bild nicht angezeigt. Wenn kein Bild angezeigt wird, kann das Kombinationsfeld den Texteinzug entfernen, der auf ein Bild zutrifft.  
  
-   Erstellen Sie ein schmales Kombinationsfeld-Steuerelement, einschließlich Größe, damit sie im Kombinationsfeld breiter clips darin enthaltenen.  
  
 Diese Style Flags sind in der beschriebenen [Verwenden von CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="item-retention-and-callback-item-attributes"></a>Aufbewahrungszeit und Rückrufattribute-Element  
 Elementinformationen, wie z. B. Indizes, die für Elemente und Bilder, Werte für die Einzüge und Textzeichenfolgen, in der Win32-Struktur gespeichert [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746)gemäß der Beschreibung im Windows SDK. Die Struktur enthält auch Member, die Rückruf-Flags entsprechen.  
  
 Ein ausführlicher und konzeptionelle Erläuterung finden Sie unter [Verwenden von CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
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
 Erstellt das Kombinationsfeld und fügt es der `CComboBoxEx` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Kombination von Kombinationsfeld Feld Stile angewendet werden, um das Kombinationsfeld an. Finden Sie unter **"Hinweise"** unten für Weitere Informationen zu Stilen.  
  
 `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Position und Größe des Kombinationsfelds ist.  
  
 `pParentWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Kombinationsfelds ist (in der Regel eine `CDialog`). Es muss nicht **NULL**.  
  
 `nID`  
 Gibt an, das Kombinationsfeld-Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CComboBoxEx` Objekt in zwei Schritten:  
  
1.  Rufen Sie [CComboBoxEx](#ccomboboxex) zum Erstellen einer `CComboBoxEx` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die die erweiterte Windows-Kombinationsfelds erstellt und fügt es der `CComboBoxEx` Objekt.  
  
 Beim Aufruf **erstellen**, MFC initialisiert die Standardsteuerelemente.  
  
 Wenn Sie im Kombinationsfeld erstellen, können Sie einige oder alle der folgenden kombinationsfeldstile angeben:  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 Alle anderen Formate, die übergeben wird, wenn Sie das Fenster erstellen, werden ignoriert. Die **ComboBoxEx** Steuerelement unterstützt auch die erweiterten Stile, die zusätzliche Funktionen bereitstellen. Diese Formate werden in beschrieben [ComboBoxEx steuern die erweiterten Stile](http://msdn.microsoft.com/library/windows/desktop/bb775742), im Windows SDK. Legen Sie diese Formate durch Aufrufen von [SetExtendedStyle](#setextendedstyle).  
  
 Wenn Sie die erweiterten Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
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
 `dwExStyle`  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `dwStyle`  
 Ein Kombinationsfeld-Steuerelement Stil. Finden Sie unter [erstellen](#create) eine Liste der Stile.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
 `CreateEx` das Steuerelement erstellt, mit der erweiterten Fensterstile gemäß `dwExStyle`. Sie müssen verbindungsspezifische erweiterten Stile, die ein Steuerelement mit erweiterten Kombinationsfeld Feld [SetExtendedStyle](#setextendedstyle). Verwenden Sie z. B. `CreateEx` festzulegende Stile als **WS_EX_CONTEXTHELP**, verwenden jedoch `SetExtendedStyle` festzulegende Stile als **CBES_EX_CASESENSITIVE**. Weitere Informationen finden Sie unter die Stile, die in diesem Thema beschriebenen [erweiterte ComboBoxEx-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb775742) im Windows SDK.  
  
##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem  
 Entfernt ein Element aus einem **ComboBoxEx** Steuerelement.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Nullbasierte Index des zu entfernenden Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Steuerelement Verbleibend. Wenn `iIndex` ungültig ist, gibt die Funktion **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768)gemäß der Beschreibung im Windows SDK. Beim Aufruf von DeleteItem, eine [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) -Nachricht mit **CBEN_DELETEITEM** Benachrichtigung wird an das übergeordnete Fenster gesendet werden.  
  
##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf ein Kombinationsfeld-Steuerelement in einem `CComboBoxEx` Objekt.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CComboBox` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CComboBoxEx` -Steuerelement besteht aus einem übergeordneten Fenster der kapselt einen `CComboBox`.  
  
 Die `CComboBox` Objekt verweist, zu der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf das Steuerelement zum Bearbeiten für ein Kombinationsfeld zu erhalten.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CEdit](../../mfc/reference/cedit-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CComboBoxEx` Steuerelement verwendet ein Bearbeitungsfeld, während der Erstellung mit der **CBS_DROPDOWN** Stil.  
  
 Die `CEdit` Objekt verweist, zu der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle  
 Rufen Sie diese Memberfunktion, um die erweiterten Stile, die zum Abrufen einer `CComboBoxEx` Steuerelement.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `DWORD` Wert, der die erweiterten Stile enthält, die für ein Kombinationsfeld-Steuerelement verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ComboBoxEx-Steuerelementtypen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb775742) in das Windows SDK für Weitere Informationen zu diesen Formaten.  
  
##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf die Bildliste von verwendet eine `CComboBoxEx` Steuerelement.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt. Falls dies fehlschlägt, gibt diese Memberfunktion **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Die `CImageList` Objekt verweist, zu der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="getitem"></a>  :: GetItem  
 Ruft die Elementinformationen für einen bestimmten **ComboBoxEx** Element.  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pCBItem`  
 Ein Zeiger auf eine [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) -Struktur, die die Elementinformationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged  
 Bestimmt, ob der Benutzer den Inhalt der geänderten der **ComboBoxEx** Steuerelement bearbeiten, indem Sie eingeben.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer im Eingabefeld für das Steuerelement eingegeben hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="insertitem"></a>  CComboBoxEx:: InsertItem  
 Fügt ein neues Element in einem **ComboBoxEx** Steuerelement.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pCBItem`  
 Ein Zeiger auf eine [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) -Struktur, die die Elementinformationen erhält. Diese Struktur enthält die Rückruf-Flagwerte für das Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index, an dem das neue Element im Erfolgsfall eingefügt wurde; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufruf `InsertItem`, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) -Nachricht mit [CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764) Benachrichtigung wird an das übergeordnete Fenster gesendet werden.  
  
##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle  
 Rufen Sie diese Memberfunktion, um die erweiterten Stile, die für ein Steuerelement erweiterte Kombinationsfeld verwendet festzulegen.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExMask`  
 Ein `DWORD` -Wert, der gibt an, welche Formate in `dwExStyles` betroffen sein werden. Nur die erweiterten Stile in `dwExMask` geändert werden. Alle anderen Arten werden unverändert beibehalten. Wenn dieser Parameter 0 (null), und klicken Sie dann alle Formate in `dwExStyles` beeinflusst werden.  
  
 `dwExStyles`  
 Ein `DWORD` Wert, der im Kombinationsfeld enthält steuern die erweiterten Stile, die für das Steuerelement festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert, der die erweiterten Stile, die zuvor verwendet für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ComboBoxEx-Steuerelementtypen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb775742) in das Windows SDK für Weitere Informationen zu diesen Formaten.  
  
 Verwenden Sie zum Erstellen von einem Kombinationsfeld-Steuerelement mit erweiterten Fensterstile erweiterte [CreateEx](#createex).  
  
##  <a name="setimagelist"></a>  CComboBoxEx:: SetImageList  
 Legt eine Bildliste für eine **ComboBoxEx** Steuerelement.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf eine `CImageList` Objekt, das die Bilder für die Verwendung mit enthält die `CComboBoxEx` Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt, das die zuvor vom verwendet Bilder enthält die `CComboBoxEx` Steuerelement. **NULL** , wenn keine Bildliste vorher festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787)gemäß der Beschreibung im Windows SDK. Wenn Sie die Höhe des Standard-Edit-Steuerelements ändern, rufen Sie die Win32-Funktion [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Ihre Steuerelements ändern, nach dem Aufruf `SetImageList`, oder es wird nicht ordnungsgemäß angezeigt.  
  
 Die `CImageList` Objekt verweist, zu der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="setitem"></a>  CComboBoxEx::SetItem  
 Legt die Attribute für ein Element in einem **ComboBoxEx** Steuerelement.  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pCBItem`  
 Ein Zeiger auf eine [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) -Struktur, die die Elementinformationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme  
 Legt den visuellen Stil der erweiterten Kombinationsfeld-Steuerelement fest.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 `pszSubAppName`  
 Ein Zeiger auf eine Unicode-Zeichenfolge, die den erweiterten Kombinationsfeld visuellen Stil festzulegende Feld enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) Nachricht, wie im Windows SDK beschrieben.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel-MFCIE](../../visual-cpp-samples.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)
