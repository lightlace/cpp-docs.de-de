---
title: CToolBar-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
dev_langs:
- C++
helpviewer_keywords:
- Windows toolbar common controls [C++]
- control bars [C++], CToolBar class
- toolbars [C++], CToolBar class
- buttons [C++], MFC toolbars
- bitmaps [C++], button controls
- CToolBar class
- Windows common controls [C++], CToolBar class
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
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
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: d7fea85426eef09f3694bd26e037acaaccc63f01
ms.lasthandoff: 02/24/2017

---
# <a name="ctoolbar-class"></a>CToolBar-Klasse
Steuerleisten, die eine Zeile mit Bitmapschaltflächen und optionalen Trennzeichen enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CToolBar : public CControlBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolBar::CToolBar](#ctoolbar)|Erstellt ein `CToolBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolBar::CommandToIndex](#commandtoindex)|Gibt den Index einer Schaltfläche mit der angegebenen Befehls-ID.|  
|[Symbolleistenformate](#create)|Erstellt die Windows-Symbolleiste, und fügt es der `CToolBar` Objekt.|  
|[CToolBar::CreateEx](#createex)|Erstellt eine `CToolBar` Objekt mit Weitere Formate für das eingebettete `CToolBarCtrl` Objekt.|  
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Ruft die ID, Stil und Image-Anzahl der Schaltfläche.|  
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Ruft den Stil für eine Schaltfläche ab.|  
|[CToolBar::GetButtonText](#getbuttontext)|Ruft den Text ab, der auf eine Schaltfläche angezeigt wird.|  
|[CToolBar::GetItemID](#getitemid)|Gibt die Befehls-ID einer Schaltfläche oder Trennzeichen am angegebenen Index zurück.|  
|[CToolBar::GetItemRect](#getitemrect)|Ruft das Anzeigerechteck für das Element am angegebenen Index ab.|  
|[GetToolBarCtrl](#gettoolbarctrl)|Ermöglicht den direkten Zugriff auf das zugrunde liegende Standardsteuerelement.|  
|[CToolBar::LoadBitmap](#loadbitmap)|Lädt die Bitmap, die Bitmap-Bilder enthält.|  
|[CToolBar::LoadToolBar](#loadtoolbar)|Lädt eine Symbolleistenressource mit dem Ressourcen-Editor erstellt.|  
|[CToolBar::SetBitmap](#setbitmap)|Legt ein Bitmapbild fest.|  
|[CToolBar::SetButtonInfo](#setbuttoninfo)|ID, Stil und Image-Anzahl der Schaltfläche festgelegt.|  
|[CToolBar::SetButtons](#setbuttons)|Legt die Schaltfläche Formatvorlagen und einen Index der Bilder innerhalb der Bitmap.|  
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Legt das Format für eine Schaltfläche.|  
|[CToolBar::SetButtonText](#setbuttontext)|Legt den Text, der angezeigt wird auf einer Schaltfläche fest.|  
|[CToolBar::SetHeight](#setheight)|Legt die Höhe der Symbolleiste.|  
|[CToolBar::SetSizes](#setsizes)|Legt die Größe der Schaltflächen und ihre Bitmaps.|  
  
## <a name="remarks"></a>Hinweise  
 Die Schaltflächen können wie Druckknöpfe, Kontrollkästchen Schaltflächen oder Optionsfelder reagieren. `CToolBar`-Objekte sind in der Regel eingebettete Elemente der Rahmenfenster-Objekte, die von der Klasse abgeleitet [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).  
  
 [GetToolBarCtrl](#gettoolbarctrl), eine Memberfunktion neue MFC 4.0, können Sie die allgemeinen Windows-Steuerelements-Unterstützung für die Anpassung von Symbolleisten und zusätzliche Funktionen nutzen. `CToolBar`Member-Funktionen bieten Ihnen die meisten Funktionen des allgemeinen Windows-Steuerelemente; allerdings beim Aufruf `GetToolBarCtrl`, Symbolleisten noch mehr Merkmale der Windows 95/98 Symbolleisten erteilen. Beim Aufruf von `GetToolBarCtrl`, es gibt einen Verweis auf ein `CToolBarCtrl` Objekt. Finden Sie unter [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) für Weitere Informationen zum Entwerfen von Symbolleisten mithilfe der allgemeinen Windows-Steuerelemente. Weitere allgemeine Informationen über allgemeine Steuerelemente, finden Sie unter [Standardsteuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775493) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Visual C++ bietet zwei Methoden zum Erstellen einer Symbolleiste. Um eine Symbolleistenressource mit dem Ressourcen-Editor zu erstellen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen Sie eine Symbolleistenressource.  
  
2.  Erstellen der `CToolBar` Objekt.  
  
3.  Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex))-Funktion die Windows-Symbolleiste erstellen und Anfügen an die `CToolBar` Objekt.  
  
4.  Rufen Sie [LoadToolBar](#loadtoolbar) zum Laden der Symbolleistenressource.  
  
 Andernfalls gehen Sie folgendermaßen vor:  
  
1.  Erstellen der `CToolBar` Objekt.  
  
2.  Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex))-Funktion die Windows-Symbolleiste erstellen und Anfügen an die `CToolBar` Objekt.  
  
3.  Rufen Sie [LoadBitmap](#loadbitmap) Bitmap zu laden, die die Symbolleisten-Schaltflächen enthält.  
  
4.  Rufen Sie [SetButtons](#setbuttons) um den Schaltflächenstil festgelegt, und ordnen Sie jede Schaltfläche ein Bild in der Bitmap.  
  
 Die Schaltflächenbilder auf der Symbolleiste stammen aus einer Bitmap, ein Bild für jede Schaltfläche enthalten muss. Alle Bilder müssen die gleiche Größe aufweisen; Der Standardwert ist 16 Pixel breit und 15 Pixel hoch. Bilder müssen nebeneinander in der Bitmap sein.  
  
 Die `SetButtons` Funktion akzeptiert einen Zeiger auf ein Array von Steuerelement-IDs und eine ganze Zahl, die die Anzahl der Elemente im Array angibt. Die Funktion legt jede Schaltfläche-ID auf den Wert des entsprechenden Elements des Arrays und weist jeder Schaltfläche einen Image-Index, der die Position des Bild der Schaltfläche in der Bitmap angibt. Wenn ein Arrayelement den Wert **ID_SEPARATOR**, keine Abbildindex zugewiesen ist.  
  
 Die Reihenfolge der Bilder in der Bitmap ist in der Regel die Reihenfolge, in der sie auf dem Bildschirm gezeichnet werden, jedoch können Sie, die [SetButtonInfo](#setbuttoninfo) Funktion, um die Beziehung zwischen Bild und Zeichnungsreihenfolge ändern.  
  
 Alle Schaltflächen einer Symbolleiste sind gleich groß. Der Standardwert ist 24 x 22 Pixel in Übereinstimmung mit *Richtlinien der Windows-Benutzeroberfläche für den Softwareentwurf*. Alle zusätzlichen Leerraum zwischen Bild und Schaltfläche Dimensionen wird verwendet, um einen Rahmen um das Bild zu bilden.  
  
 Jede Schaltfläche verfügt über ein Bild. Die verschiedenen Zustände Schaltfläche und Stile (gedrückt, oben, unten, deaktiviert, Sie deaktiviert und unbestimmt) aus generiert wird, dass ein Bild. Obwohl Bitmaps auf eine beliebige Farbe sein kann, können Sie mit Bildern in Schwarz und Graustufen die besten Ergebnisse erzielen.  
  
> [!WARNING]
> `CToolBar`unterstützt Bitmaps mit maximal 16 Farben. Wenn Sie ein Bild in einem Symbolleisten-Editor laden, Visual Studio automatisch konvertiert das Bild in eine 16-Farben-Bitmap, bei Bedarf und eine Warnung angezeigt, wenn das Bild konvertiert wurde. Wenn Sie ein Bild mit mehr als 16 Farben (mit einem externen Editor Bearbeiten der Grafik) verwenden, kann die Anwendung unerwartetes Verhalten zeigen.  
  
 Schaltflächen der Symbolleiste imitieren Druckknöpfe standardmäßig. Schaltflächen der Symbolleiste können jedoch auch Schaltflächen Kontrollkästchen oder Optionsfelder imitieren. Aktivieren Sie das Kontrollkästchen Schaltflächen über drei Zustände verfügen: aktiviert, deaktiviert und unbestimmt. Optionsfelder gibt es nur zwei Zustände: aktiviert und deaktiviert.  
  
 Aufrufen, um eine einzelne Schaltfläche oder die Trennzeichen festlegen, ohne auf ein Array verweist, [GetButtonStyle](#getbuttonstyle) , rufen die Formatvorlage, und rufen dann [SetButtonStyle](#setbuttonstyle) anstelle von `SetButtons`. `SetButtonStyle`ist besonders hilfreich, wenn Sie eine Schaltfläche zur Laufzeit ändern möchten.  
  
 Rufen Sie zum Zuweisen von Text, der auf eine Schaltfläche angezeigt [GetButtonText](#getbuttontext) zum Abrufen des Text auf der Schaltfläche angezeigt, und rufen Sie anschließend [SetButtonText](#setbuttontext) um den Text festzulegen.  
  
 Um ein Kontrollkästchen-Schaltfläche erstellen, weisen sie die Formatvorlage **TBBS_CHECKBOX** oder verwenden Sie eine `CCmdUI` des Objekts `SetCheck` Memberfunktion in einer `ON_UPDATE_COMMAND_UI` Handler. Aufrufen von `SetCheck` aktiviert eine Schaltfläche in einem Kontrollkästchen-Schaltfläche. Übergeben Sie `SetCheck` Argument 0 für die Option deaktiviert, 1 für aktiviert ist, oder 2 für unbestimmt.  
  
 Um ein Optionsfeld zu erstellen, rufen Sie eine [CCmdUI](../../mfc/reference/ccmdui-class.md) des Objekts [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) Memberfunktion ein `ON_UPDATE_COMMAND_UI` Handler. Übergeben Sie `SetRadio` Argument 0 für deaktiviert oder ungleich NULL für überprüft. Um eine Radio Gruppe sich gegenseitig ausschließende Verhalten bereitzustellen, benötigen Sie `ON_UPDATE_COMMAND_UI` Handler für alle Schaltflächen in der Gruppe.  
  
 Weitere Informationen zur Verwendung von `CToolBar`, finden Sie im Artikel [Implementieren der MFC-Symbolleiste](../../mfc/mfc-toolbar-implementation.md) und [Technische Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="commandtoindex"></a>CToolBar::CommandToIndex  
 Diese Memberfunktion gibt den Index der ersten Symbolleisten-Schaltfläche, beginnend an Position 0, dessen Befehls-ID entspricht `nIDFind`.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDFind`  
 Befehls-ID für eine Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der Schaltfläche oder –&1;, wenn keine Schaltfläche der angegebenen Befehls-ID verfügt.  
  
##  <a name="create"></a>Symbolleistenformate  
 Diese Member-Funktion erstellt eine Windows-Symbolleiste (ein untergeordnetes Fenster), und ordnet sie der `CToolBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das Sie auf der Symbolleiste das übergeordnete Element ist.  
  
 `dwStyle`  
 Der Toolbar-Stil. Zusätzliche Toolbar-Stile, die unterstützt werden:  
  
- `CBRS_TOP`Titelleiste wird am oberen Rand des Frame-Fensters.  
  
- `CBRS_BOTTOM`Steuerleiste ist am unteren Rand des Rahmenfensters.  
  
- `CBRS_NOALIGN`Steuerleiste ist nicht neu angeordnet, die übergeordnetem Element geändert wird.  
  
- `CBRS_TOOLTIPS`Steuerleiste werden QuickInfos angezeigt.  
  
- **CBRS_SIZE_DYNAMIC** Steuerleiste ist dynamisch.  
  
- **CBRS_SIZE_FIXED** Steuerleiste ist fest.  
  
- **CBRS_FLOATING** Steuerleiste ist nicht verankert.  
  
- `CBRS_FLYBY`Statusleiste zeigt Informationen über die Schaltfläche.  
  
- **CBRS_HIDE_INPLACE** Steuerleiste wird dem Benutzer nicht angezeigt.  
  
 `nID`  
 Die Symbolleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Außerdem wird die Höhe der Symbolleiste auf einen Standardwert festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#179;](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]  
  
##  <a name="createex"></a>CToolBar::CreateEx  
 Rufen Sie diese Funktion zum Erstellen einer Windows-Symbolleiste (ein untergeordnetes Fenster), und ordnen sie die `CToolBar` Objekt.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,  
    CRect rcBorders = CRect(
    0, 
    0, 
    0, 
    0), 
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das Sie auf der Symbolleiste das übergeordnete Element ist.  
  
 `dwCtrlStyle`  
 Weitere Formate für die Erstellung der eingebetteten [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Objekt. Standardmäßig ist dieser Wert auf festgelegt **TBSTYLE_FLAT**. Eine vollständige Liste der Toolbar-Stile finden Sie unter `dwStyle`.  
  
 `dwStyle`  
 Der Toolbar-Stil. Finden Sie unter [Symbolleisten-Steuerelements und Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb760439) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der entsprechenden Stile.  
  
 *rcBorders*  
 Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Breite der Symbolleiste Fensterrahmen definiert. Dieser Rahmen werden standardmäßig in einem Symbolleistenfenster ohne Rahmen somit auf 0,0,0,0 festgelegt.  
  
 `nID`  
 Die Symbolleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Außerdem wird die Höhe der Symbolleiste auf einen Standardwert festgelegt.  
  
 Verwendung `CreateEx`, anstelle von [erstellen](#create), wenn bestimmte Formatvorlagen während der Erstellung der eingebetteten ToolBar-Steuerelement vorhanden sein müssen. Legen Sie z. B. `dwCtrlStyle` auf **TBSTYLE_FLAT | TBSTYLE_TRANSPARENT** zum Erstellen einer Symbolleiste, die die Internet Explorer 4 Symbolleisten ähnelt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#180;](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]  
  
##  <a name="ctoolbar"></a>CToolBar::CToolBar  
 Diese Member-Funktion erstellt ein `CToolBar` -Objekt und legt die Standardgröße.  
  
```  
CToolBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [erstellen](#create) Memberfunktion, um das Symbolleistenfenster zu erstellen.  
  
##  <a name="getbuttoninfo"></a>CToolBar::GetButtonInfo  
 Diese Memberfunktion Ruft die Steuerelement-ID Stil und Image-Index der Symbolleisten-Schaltfläche oder Trennzeichen am angegebenen Speicherort *nIndex.*  
  
```  
void GetButtonInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& iImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index der Symbolleisten-Schaltfläche oder Separator, deren Informationen abgerufen werden sollen.  
  
 `nID`  
 Ein Verweis auf eine **UINT** , um die Befehls-ID der Schaltfläche festgelegt wird.  
  
 `nStyle`  
 Ein Verweis auf eine **UINT** , um den Stil der Schaltfläche festgelegt wird.  
  
 `iImage`  
 Verweis auf eine ganze Zahl, die auf den Index, der das Bild der Schaltfläche innerhalb der Bitmap festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Werte werden den Variablen, auf die verwiesen wird zugewiesen `nID`, `nStyle`, und `iImage`. Die Image-Index ist die Position des Bilds innerhalb der Bitmap, die Bilder für Schaltflächen der Symbolleiste enthält. Das erste Bild wird an Position 0.  
  
 Wenn `nIndex` gibt ein Trennzeichen `iImage` der Trennzeichen Breite in Pixel festgelegt ist.  
  
##  <a name="getbuttonstyle"></a>CToolBar::GetButtonStyle  
 Rufen Sie diese Memberfunktion, um den Stil einer Schaltfläche oder Trennzeichen auf der Symbolleiste abzurufen.  
  
```  
UINT GetButtonStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index der Symbolleiste Schaltfläche oder ein Trennzeichen Formatvorlage abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stil der Schaltfläche oder durch angegebene Trennzeichen `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Schaltflächen-Formatvorlage bestimmt, wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert. Finden Sie unter [SetButtonStyle](#setbuttonstyle) Beispiele Schaltflächenstile.  
  
##  <a name="getbuttontext"></a>CToolBar::GetButtonText  
 Rufen Sie diese Memberfunktion zum Abrufen des Texts, der auf eine Schaltfläche angezeigt wird.  
  
```  
CString GetButtonText(int nIndex) const;  
  
void GetButtonText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Textes abgerufen werden sollen.  
  
 `rString`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekts, enthält den Text abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den Text der Schaltfläche enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das zweite Formular dieses Members-Funktion füllt eine `CString` Objekt mit dem Zeichenfolgentext.  
  
##  <a name="getitemid"></a>CToolBar::GetItemID  
 Diese Memberfunktion gibt die Befehls-ID der Schaltfläche oder die angegebenen Trennzeichen `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Elements, dessen ID abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID der Schaltfläche oder die angegebenen Trennzeichen `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Zurückgeben von Trennzeichen **ID_SEPARATOR**.  
  
##  <a name="getitemrect"></a>CToolBar::GetItemRect  
 Diese Memberfunktion füllt die `RECT` Struktur, deren Adresse ist in `lpRect` mit den Koordinaten der Schaltfläche oder die angegebenen Trennzeichen `nIndex`.  
  
```  
virtual void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Elements (Schaltfläche oder ein Trennzeichen), dessen Koordinaten für das Rechteck abgerufen werden sollen.  
  
 `lpRect`  
 Adresse der [RECT](../../mfc/reference/rect-structure1.md) Struktur, die Koordinaten des Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zur linken oberen Ecke der Symbolleiste.  
  
 Verwendung `GetItemRect` um die Koordinaten eines Trennzeichens abzurufen, mit einem Kombinationsfeld oder einem anderen Steuerelement ersetzen soll.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CToolBar::SetSizes](#setsizes).  
  
##  <a name="gettoolbarctrl"></a>GetToolBarCtrl  
 Diese Memberfunktion ermöglicht den direkten Zugriff auf das zugrunde liegende Standardsteuerelement.  
  
```  
CToolBarCtrl& GetToolBarCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein `CToolBarCtrl`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `GetToolBarCtrl` die Funktionalität des allgemeinen Symbolleisten-Steuerelements von Windows nutzen und die Unterstützung nutzen [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Anpassen von Symbolleisten bereit.  
  
 Weitere Informationen zum Verwenden von allgemeinen Steuerelementen finden Sie im Artikel [Steuerelemente](../../mfc/controls-mfc.md) und [Standardsteuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775493) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocViewSDI&#15;](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]  
  
##  <a name="loadbitmap"></a>CToolBar::LoadBitmap  
 Rufen Sie diese Memberfunktion zum Laden von angegebenen Bitmap `lpszResourceName` oder `nIDResource`.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Ein Zeiger auf den Ressourcennamen der Bitmap geladen werden.  
  
 `nIDResource`  
 Ressourcen-ID der Bitmap geladen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap sollte es sich um ein Bild für jede Symbolleisten-Schaltfläche enthalten. Wenn die Bilder nicht Aufruf von die Standardgröße (16 Pixel breit und 15 Pixel hoch), sind [SetSizes](#setsizes) die Schaltfläche und ihre Bilder festlegen.  
  
> [!WARNING]
> `CToolBar`unterstützt Bitmaps mit maximal 16 Farben. Wenn Sie ein Bild in einem Symbolleisten-Editor laden, Visual Studio automatisch konvertiert das Bild in eine 16-Farben-Bitmap, bei Bedarf und eine Warnung angezeigt, wenn das Bild konvertiert wurde. Wenn Sie ein Bild mit mehr als 16 Farben (mit einem externen Editor Bearbeiten der Grafik) verwenden, kann die Anwendung unerwartetes Verhalten zeigen.  
  
##  <a name="loadtoolbar"></a>CToolBar::LoadToolBar  
 Rufen Sie diese Memberfunktion zum Laden der durch angegebenen Symbolleiste `lpszResourceName` oder `nIDResource`.  
  
```  
BOOL LoadToolBar(LPCTSTR lpszResourceName);  
BOOL LoadToolBar(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Ein Zeiger auf den Ressourcennamen der Symbolleiste geladen werden.  
  
 `nIDResource`  
 Ressourcen-ID der Symbolleiste geladen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Symbolleisten-Editor](../../windows/toolbar-editor.md) in Weitere Informationen zum Erstellen einer Symbolleistenressource.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CToolBar::CreateEx](#createex).  
  
##  <a name="setbitmap"></a>CToolBar::SetBitmap  
 Rufen Sie diese Memberfunktion, um das Bitmap-Bild für die Symbolleiste festlegen.  
  
```  
BOOL SetBitmap(HBITMAP hbmImageWell);
```  
  
### <a name="parameters"></a>Parameter  
 *hbmImageWell*  
 Handle für eine Bitmap, die eine Symbolleiste zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie z. B. `SetBitmap` als Bitmap verfügbares Bild zu ändern, nachdem der Benutzer eine Aktion in einem Dokument ausgeführt wird, die die Aktion einer Schaltfläche ändert.  
  
##  <a name="setbuttoninfo"></a>CToolBar::SetButtonInfo  
 Rufen Sie diese Memberfunktion zum Festlegen der Befehls-ID, Stil und Image-Anzahl der Schaltfläche.  
  
```  
void SetButtonInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index der Schaltfläche oder Trennzeichen für die Informationen ist, festgelegt werden.  
  
 `nID`  
 Der Wert für den Befehls-ID der Schaltfläche festgelegt wird.  
  
 `nStyle`  
 Der neue Schaltflächenstil. Die folgenden Schaltflächenformate werden unterstützt:  
  
- **TBBS_BUTTON** Standard Pushbutton (Standard)  
  
- **TBBS_SEPARATOR** Trennzeichen  
  
- **TBBS_CHECKBOX** Kontrollkästchen-Schaltfläche "Auto"  
  
- **TBBS_GROUP** kennzeichnet den Anfang einer Gruppe von Schaltflächen  
  
- **TBBS_CHECKGROUP** kennzeichnet den Anfang einer Gruppe von Kontrollkästchen Schaltflächen  
  
- **TBBS_DROPDOWN** erstellt eine Schaltfläche Dropdown-Liste.  
  
- **TBBS_AUTOSIZE** die Breite der Schaltfläche wird basierend auf den Text der Schaltfläche, nicht auf die Größe des Bilds berechnet.  
  
- **TBBS_NOPREFIX** der Text der Schaltfläche müssen sich nicht auf einer Zugriffstaste Präfix zugeordnet.  
  
 `iImage`  
 Neue Index für das Bild der Schaltfläche innerhalb der Bitmap.  
  
### <a name="remarks"></a>Hinweise  
 Für Trennzeichen, die den Stil haben **TBBS_SEPARATOR**, setzt diese Funktion das Trennzeichen Breite in Pixel, um den Wert in gespeicherten `iImage`.  
  
> [!NOTE]
>  Zudem lassen sich mithilfe von Schaltflächenstatus der `nStyle` Parameter jedoch da Schaltflächenstatus, indem gesteuert werden die [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) Ereignishandler einen Zustand mit festlegen `SetButtonInfo` während der Verarbeitung der nächsten Leerlauf verloren. Finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Schiebeleisten-](../../mfc/tn031-control-bars.md) für Weitere Informationen.  
  
 Informationen über Bitmaps und Schaltflächen, finden Sie unter der [CToolBar](../../mfc/reference/ctoolbar-class.md) Überblick und [CToolBar::LoadBitmap](#loadbitmap).  
  
##  <a name="setbuttons"></a>CToolBar::SetButtons  
 Diese Memberfunktion setzt jede Symbolleistenschaltfläche Befehls-ID auf den Wert, der durch das entsprechende Element im Array angegeben `lpIDArray`.  
  
```  
BOOL SetButtons(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpIDArray`  
 Ein Zeiger auf ein Array von Befehls-Ids. Es kann sein **NULL** leere Schaltflächen zuweisen.  
  
 `nIDCount`  
 Anzahl der Elemente im Array auf die `lpIDArray`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Element des Arrays den Wert hat **ID_SEPARATOR**, eine Trennzeichen wird in der entsprechenden Position der Symbolleiste erstellt. Setzt diese Funktion auch jede der Stil der Schaltfläche auf **TBBS_BUTTON** und jedes Trennzeichen Formatvorlagen in **TBBS_SEPARATOR**, und jede Schaltfläche einen Bildindex zugewiesen. Image-Index gibt die Position der Schaltfläche Bilds innerhalb der Bitmap.  
  
 Sie müssen nicht für Trennzeichen in der Bitmap zu berücksichtigen, da diese Funktion nicht Bildindizes für Trennzeichen zuweist. Wenn eine Symbolleiste Schaltflächen an der Position 0 hat, werden 1 und 3 und Trennzeichen an Position 2, die Bilder an der Position 0, 1 und 2 in der Bitmap auf die Schaltflächen an Position 0, 1 und 3, zugewiesen.  
  
 Wenn `lpIDArray` ist **NULL**, diese Funktion weist den Speicherplatz für die Anzahl der Elemente, die durch angegebene `nIDCount`. Verwendung [SetButtonInfo](#setbuttoninfo) Attribute des Elements festgelegt.  
  
##  <a name="setbuttonstyle"></a>CToolBar::SetButtonStyle  
 Rufen Sie diese Memberfunktion zum legen Sie des Stils einer Schaltfläche oder Trennzeichen oder gruppieren.  
  
```  
void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index der Schaltfläche oder Separator, deren Informationen festgelegt werden.  
  
 `nStyle`  
 Das Schaltflächenformat. Die folgenden Schaltflächenformate werden unterstützt:  
  
- **TBBS_BUTTON** Standard Pushbutton (Standard)  
  
- **TBBS_SEPARATOR** Trennzeichen  
  
- **TBBS_CHECKBOX** Kontrollkästchen-Schaltfläche "Auto"  
  
- **TBBS_GROUP** kennzeichnet den Anfang einer Gruppe von Schaltflächen  
  
- **TBBS_CHECKGROUP** kennzeichnet den Anfang einer Gruppe von Kontrollkästchen Schaltflächen  
  
- **TBBS_DROPDOWN** erstellt eine Schaltfläche Dropdown-Liste  
  
- **TBBS_AUTOSIZE** berechnet wird, die Breite der Schaltfläche basierend auf den Text der Schaltfläche, nicht auf die Größe des Bilds  
  
- **TBBS_NOPREFIX** der Text der Schaltfläche müssen sich nicht auf einer Zugriffstaste Präfix zugeordnet  
  
### <a name="remarks"></a>Hinweise  
 Ein Schaltflächen-Formatvorlage bestimmt, wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert.  
  
 Vor dem Aufruf von `SetButtonStyle`, rufen Sie die [GetButtonStyle](#getbuttonstyle) Member-Funktion, um den Stil Schaltfläche oder ein Trennzeichen abzurufen.  
  
> [!NOTE]
>  Zudem lassen sich mithilfe von Schaltflächenstatus der `nStyle` Parameter jedoch da Schaltflächenstatus, indem gesteuert werden die [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) Ereignishandler einen Zustand mit festlegen `SetButtonStyle` während der Verarbeitung der nächsten Leerlauf verloren. Finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Schiebeleisten-](../../mfc/tn031-control-bars.md) für Weitere Informationen.  
  
##  <a name="setbuttontext"></a>CToolBar::SetButtonText  
 Rufen Sie diese Funktion, um den Text in einer Schaltfläche festzulegen.  
  
```  
BOOL SetButtonText(
    int nIndex,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index der Schaltfläche, deren Text ist, festgelegt werden.  
  
 `lpszText`  
 Zeigt auf den Text auf einer Schaltfläche festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetToolBarCtrl](#gettoolbarctrl).  
  
##  <a name="setheight"></a>CToolBar::SetHeight  
 Diese Memberfunktion wird die Symbolleiste Höhe auf den Wert in Pixel im angegebenen `cyHeight`.  
  
```  
void SetHeight(int cyHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `cyHeight`  
 Die Höhe in Pixel der Symbolleiste.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von [SetSizes](#setsizes), diese Member-Funktion verwenden, um die Höhe der Symbolleiste standard zu überschreiben. Wenn die Höhe zu klein ist, werden die Schaltflächen am unteren Rand abgeschnitten.  
  
 Wenn diese Funktion nicht aufgerufen wird, verwendet das Framework die Größe der Schaltfläche zum Bestimmen der Höhe der Symbolleiste.  
  
##  <a name="setsizes"></a>CToolBar::SetSizes  
 Rufen Sie diese Memberfunktion zum Festlegen von Schaltflächen der Symbolleiste auf die Größe in Pixel im angegebenen *SizeButton*.  
  
```  
void SetSizes(
    SIZE sizeButton,  
    SIZE sizeImage);
```  
  
### <a name="parameters"></a>Parameter  
 *sizeButton*  
 Die Größe der einzelnen Schaltflächen in Pixel.  
  
 `sizeImage`  
 Die Größe des jedes Bilds in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Die `sizeImage` Parameter darf die Größe der Bilder in der Symbolleiste auf die Bitmap in Pixel. Die Dimensionen in *SizeButton* ausreichend sein, das Abbild plus 7 Pixel breit zusätzliche und zusätzliche in Höhe von 6 Pixel zu halten. Diese Funktion legt auch die Höhe der Symbolleiste die Schaltflächen an.  
  
 Rufen Sie diese Memberfunktion nur für Symbolleisten, die nicht folgen *Richtlinien der Windows-Benutzeroberfläche für den Softwareentwurf* Empfehlungen für die Größe der Schaltfläche und Image.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCListView&#8;](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Muster CTRLBARS](../../visual-cpp-samples.md)   
 [MFC-Beispiel DLGCBR32](../../visual-cpp-samples.md)   
 [MFC-Beispiel DOCKTOOL](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl-Klasse](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)

