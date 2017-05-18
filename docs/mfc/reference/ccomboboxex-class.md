---
title: CComboBoxEx-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- extended combo boxes, CComboBoxEx class
- Windows common controls [C++], extended combo boxes
- common controls [C++], extended combo boxes
- combo boxes [C++], CComboBoxEx class
- Internet Explorer 4.0 common controls
- CComboBoxEx class
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
caps.latest.revision: 26
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e88ed701111b49e3a5d3b32868bfad8e77206086
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomboboxex-class"></a>CComboBoxEx-Klasse
Erweitert das Kombinationsfeld-Steuerelement durch die Unterstützung für Bildlisten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Erstellt ein `CComboBoxEx`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|Das Kombinationsfeld erstellt, und fügt es der `CComboBoxEx` Objekt.|  
|[CComboBoxEx::CreateEx](#createex)|Erstellt ein Kombinationsfeld mit dem angegebenen erweiterten Fensterstile und fügt es einer **ComboBoxEx** Objekt.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|Entfernt ein Element aus einer **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Ruft einen Zeiger auf das Kombinationsfeld-Steuerelement untergeordnete ab.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Ruft das Handle für den Bearbeitungsbereich des Steuerelements ein **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile, die in Verwendung sind ein **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::GetImageList](#getimagelist)|Ruft einen Zeiger auf die Bildliste zugewiesene ein **ComboBoxEx** Steuerelement.|  
|[:: GetItem](#getitem)|Ruft die Elementinformationen für einen bestimmten **ComboBoxEx** Element.|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Bestimmt, ob der Benutzer den Inhalt des geänderten der **ComboBoxEx** edit-Steuerelement eingeben.|  
|[CComboBoxEx:: InsertItem](#insertitem)|Fügt ein neues Element in einem **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile, die innerhalb einer **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx:: SetImageList](#setimagelist)|Eine Bildliste für eine **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::SetItem](#setitem)|Legt die Attribute für ein Element in einem **ComboBoxEx** Steuerelement.|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil der erweiterten Kombinationsfeld-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Mithilfe von `CComboBoxEx` zum Kombinationsfeld-Steuerelemente erstellen, mehr müssen Ihr eigenes Bild zeichnen Code implementieren. Verwenden Sie stattdessen `CComboBoxEx` zu Zugriff von Bildern aus einer Bildliste.  
  
## <a name="image-list-support"></a>Bildlisten unterstützt  
 In einem standard-Kombinationsfeld ist der Besitzer des Kombinationsfelds verantwortlich für das Kombinationsfeld als Ownerdrawn-Steuerelement erstellen und ein Bild zu zeichnen. Bei Verwendung `CComboBoxEx`, Sie müssen nicht die zeichnungsarten festgelegt **CBS_OWNERDRAWFIXED** und **CBS_HASSTRINGS** , da sie implizit sind. Andernfalls müssen Sie Code zum Ausführen von Zeichenoperationen schreiben. Ein `CComboBoxEx` Steuerelement unterstützt bis zu drei Images pro Element: eine für ausgewählt, nicht ausgewählt und ein Overlaybild.  
  
## <a name="styles"></a>Stile  
 `CComboBoxEx`unterstützt die Formate **CBS_SIMPLE**, **CBS_DROPDOWN**, **CBS_DROPDOWNLIST**, und **WS_CHILD**. Alle anderen Formate, die übergeben wird, wenn Sie das Fenster erstellen, werden vom Steuerelement ignoriert. Nachdem das Fenster erstellt wurde, Sie bieten andere Kombinationsfeld Kasten durch Aufrufen der `CComboBoxEx` Memberfunktion [SetExtendedStyle](#setextendedstyle). Mit diesen Formaten können Sie folgende Aktionen ausführen:  
  
-   Set Zeichenfolge sucht in der Liste, um die Groß-/Kleinschreibung beachtet werden.  
  
-   Erstellen Sie ein Kombinationsfeld-Steuerelement, das den Schrägstrich ('/'), umgekehrter Schrägstrich ('\\'), und Punkt ('. ') Zeichen als Trennzeichen zwischen Wörtern verwenden. Dadurch werden Benutzer von einem Wort zum nächsten wechseln, mit der Tastenkombination STRG + Pfeiltaste.  
  
-   Legen Sie entweder nicht anzeigen oder ein Bild-Steuerelement. Wenn kein Bild angezeigt wird, kann das Kombinationsfeld den Texteinzug entfernen, der ein Bild aufnehmen kann.  
  
-   Erstellen Sie ein schmales Kombinationsfeld-Steuerelement, einschließlich Größe, sodass das Kombinationsfeld breiter zugeschnitten, darin enthaltenen.  
  
 Dieser Stil Flags werden ausführlich in [Verwenden von CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="item-retention-and-callback-item-attributes"></a>Aufbewahrungszeit und Rückruf-Elementattribute  
 Anzeigen, wie z. B. Indizes für Elemente und Bilder, Werte für die Einzüge und Textzeichenfolgen, in der Win32-Struktur gespeichert [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Die Struktur enthält auch Member, die Rückruf-Flags entsprechen.  
  
 Eine detaillierte, grundlegende Erläuterung finden Sie unter [Verwenden von CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>CComboBoxEx::CComboBoxEx  
 Rufen Sie diese Memberfunktion zum Erstellen einer `CComboBoxEx` Objekt.  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>CComboBoxEx::Create  
 Das Kombinationsfeld erstellt, und fügt es der `CComboBoxEx` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Kombination der kombinationsfeldformate im Kombinationsfeld angewendet. Finden Sie unter **Hinweise** unten für Weitere Informationen zu Stilen.  
  
 `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die Position und Größe des Kombinationsfelds ist.  
  
 `pParentWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Kombinationsfelds ist (in der Regel eine `CDialog`). Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Kombinationsfeld-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie ein `CComboBoxEx` Objekt in zwei Schritten:  
  
1.  Rufen Sie [CComboBoxEx](#ccomboboxex) zum Erstellen einer `CComboBoxEx` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die im erweiterten Windows-Kombinationsfeld erstellt, und fügt es der `CComboBoxEx` Objekt.  
  
 Beim Aufruf von **erstellen**, MFC initialisiert die Standardsteuerelemente.  
  
 Wenn Sie das Kombinationsfeld erstellen, können Sie einige oder alle der folgenden kombinationsfeldstile angeben:  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 Alle Stile, die beim Erstellen des Fensters übergeben werden ignoriert. Die **ComboBoxEx** -Steuerelement unterstützt auch die erweiterten Stile, die zusätzliche Funktionen bereitstellen. Diese Stile werden im Abschnitt [ComboBoxEx steuern Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb775742)in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Legen Sie diese Formate durch Aufrufen von [SetExtendedStyle](#setextendedstyle).  
  
 Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="createex"></a>CComboBoxEx::CreateEx  
 Rufen Sie diese Funktion zum Erstellen eines erweiterten Kombinationsfeld-Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CComboBoxEx` Objekt.  
  
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
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Art des Kombinationsfeld-Steuerelements. Finden Sie unter [erstellen](#create) für eine Liste der Formate.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
 `CreateEx`das Steuerelement erstellt, mit der erweiterten Fensterstile angegebenen `dwExStyle`. Sie müssen Erweiterte Stile bestimmten festlegen, auf einem erweiterten Kombinationsfeld ein Steuerelement [SetExtendedStyle](#setextendedstyle). Verwenden Sie z. B. `CreateEx` solche Stile als festlegen **WS_EX_CONTEXTHELP**, jedoch verwenden `SetExtendedStyle` solche Stile als festlegen **CBES_EX_CASESENSITIVE**. Weitere Informationen finden Sie die Stile, die in diesem Thema beschriebenen [ComboBoxEx Steuerelementtypen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb775742) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deleteitem"></a>CComboBoxEx::DeleteItem  
 Entfernt ein Element aus einer **ComboBoxEx** Steuerelement.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Nullbasierte Index des zu entfernenden Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Steuerelement verbleiben. Wenn `iIndex` ungültig ist, gibt die Funktion **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Beim Aufruf von DeleteItem, ein [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) message mit **CBEN_DELETEITEM wird** Benachrichtigung wird an das übergeordnete Fenster gesendet werden.  
  
##  <a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf ein Kombinationsfeld-Steuerelement in ein `CComboBoxEx` Objekt.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CComboBox` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CComboBoxEx` Steuerelement besteht aus einem übergeordneten Fenster der kapselt ein `CComboBox`.  
  
 Das `CComboBox` Objekt, auf das durch den Rückgabewert ist ein temporäres Objekt und wird während der nächsten Verarbeitung Leerlaufzeit zerstört.  
  
##  <a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf das Steuerelement zum Bearbeiten für ein Kombinationsfeld.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CEdit](../../mfc/reference/cedit-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CComboBoxEx` Steuerelement verwendet ein Bearbeitungsfeld, bei der Erstellung mit der **CBS_DROPDOWN** Stil.  
  
 Das `CEdit` Objekt, auf das durch den Rückgabewert ist ein temporäres Objekt und wird während der nächsten Verarbeitung Leerlaufzeit zerstört.  
  
##  <a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle  
 Rufen Sie diese Memberfunktion, um die erweiterten Stile, die zum Abrufen einer `CComboBoxEx` Steuerelement.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der `DWORD` -Wert, der die erweiterten Stile enthält, die für das Kombinationsfeld-Steuerelement verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ComboBoxEx Steuerelementtypen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb775742) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu diesen Formaten.  
  
##  <a name="getimagelist"></a>CComboBoxEx::GetImageList  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf die Bildliste durch ein `CComboBoxEx` Steuerelement.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt. Wenn dies fehlschlägt, gibt diese Memberfunktion **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das `CImageList` Objekt, auf das durch den Rückgabewert ist ein temporäres Objekt und wird während der nächsten Verarbeitung Leerlaufzeit zerstört.  
  
##  <a name="getitem"></a>:: GetItem  
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
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="haseditchanged"></a>CComboBoxEx::HasEditChanged  
 Bestimmt, ob der Benutzer den Inhalt des geänderten der **ComboBoxEx** edit-Steuerelement eingeben.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer das Steuerelement bearbeiten im Feld eingegeben hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="insertitem"></a>CComboBoxEx:: InsertItem  
 Fügt ein neues Element in einem **ComboBoxEx** Steuerelement.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pCBItem`  
 Ein Zeiger auf eine [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) -Struktur, die die Elementinformationen erhält. Diese Struktur enthält Rückruf Flagwerte für das Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index, an dem das neue Element im Erfolgsfall eingefügt wurde; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufruf von `InsertItem`, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) message mit [CBEN_INSERTITEM wird](http://msdn.microsoft.com/library/windows/desktop/bb775764) Benachrichtigung wird an das übergeordnete Fenster gesendet werden.  
  
##  <a name="setextendedstyle"></a>CComboBoxEx::SetExtendedStyle  
 Rufen Sie diese Memberfunktion zum legen Sie die erweiterten Stile, die für ein Kombinationsfeld, das erweiterte Steuerelement verwendet.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExMask`  
 Ein `DWORD` -Wert, der gibt an, welche Stile im `dwExStyles` betroffen sind. Nur die erweiterten Stile in `dwExMask` geändert werden. Alle anderen Arten werden unverändert beibehalten. Wenn dieser Parameter&0; (null), und klicken Sie dann alle Formatvorlagen in `dwExStyles` betroffen.  
  
 `dwExStyles`  
 Ein `DWORD` Wert, der im Kombinationsfeld enthält steuern die erweiterten Stile, die für das Steuerelement festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert, der die erweiterten Stile, die zuvor für das Steuerelement verwendete enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ComboBoxEx Steuerelementtypen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb775742) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu diesen Formaten.  
  
 Verwenden Sie zum Erstellen ein Kombinationsfeld-Steuerelement mit erweiterten Fensterstile erweiterte [CreateEx](#createex).  
  
##  <a name="setimagelist"></a>CComboBoxEx:: SetImageList  
 Eine Bildliste für eine **ComboBoxEx** Steuerelement.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf eine `CImageList` -Objekt, enthält die Bilder, die mit der `CComboBoxEx` Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, das die zuvor verwendeten Bildern enthält die `CComboBoxEx` Steuerelement. **NULL** Wenn keine Bildliste zuvor festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn Sie die Höhe des Standard-Edit-Steuerelements ändern, rufen Sie die Win32-Funktion [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) , ändern Sie die Größe des Steuerelements, nach dem Aufruf von `SetImageList`, oder es wird nicht ordnungsgemäß angezeigt.  
  
 Das `CImageList` Objekt, auf das durch den Rückgabewert ist ein temporäres Objekt und wird während der nächsten Verarbeitung Leerlaufzeit zerstört.  
  
##  <a name="setitem"></a>CComboBoxEx::SetItem  
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
 Diese Memberfunktion implementiert die Funktionalität der Nachricht [CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setwindowtheme"></a>CComboBoxEx::SetWindowTheme  
 Legt den visuellen Stil der erweiterten Kombinationsfeld-Steuerelement fest.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 `pszSubAppName`  
 Ein Zeiger auf eine Unicode-Zeichenfolge mit den erweiterten Kombinationsfeld Feld visuellen Stil fest.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCIE](../../visual-cpp-samples.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)

