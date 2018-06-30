---
title: CToolBar-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d6dc2c196e40daf4aa793f6643da95206b12be0
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123135"
---
# <a name="ctoolbar-class"></a>CToolBar-Klasse
Steuerleisten, die eine Zeile mit Bitmapschaltflächen und optionalen Trennzeichen enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CToolBar : public CControlBar  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolBar::CToolBar](#ctoolbar)|Erstellt ein `CToolBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CToolBar::CommandToIndex](#commandtoindex)|Gibt den Index einer Schaltfläche mit der angegebenen Befehls-ID.|  
|[Symbolleistenformate](#create)|Erstellt die Windows-Symbolleiste, und fügt es der `CToolBar` Objekt.|  
|[CToolBar::CreateEx](#createex)|Erstellt eine `CToolBar` Objekt mit zusätzlichen Formatvorlagen für das eingebettete `CToolBarCtrl` Objekt.|  
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Die ID, Stil und Image-Anzahl der eine Schaltfläche abgerufen.|  
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Ruft den Stil für eine Schaltfläche ab.|  
|[CToolBar::GetButtonText](#getbuttontext)|Ruft den Text, der auf eine Schaltfläche angezeigt wird.|  
|[CToolBar::GetItemID](#getitemid)|Gibt die Befehls-ID, eine Schaltfläche oder eines als Trennzeichen am angegebenen Index zurück.|  
|[CToolBar::GetItemRect](#getitemrect)|Ruft das Anzeigerechteck für das Element am angegebenen Index ab.|  
|[GetToolBarCtrl](#gettoolbarctrl)|Ermöglicht den direkten Zugriff auf die zugrunde liegenden Standardsteuerelements.|  
|[CToolBar::LoadBitmap](#loadbitmap)|Lädt die Bitmap, die mithilfe einer Bitmap-Bilder enthält.|  
|[CToolBar::LoadToolBar](#loadtoolbar)|Lädt eine Symbolleistenressource mit dem Ressourcen-Editor erstellt.|  
|[CToolBar::SetBitmap](#setbitmap)|Legt ein Bitmapbild fest.|  
|[CToolBar::SetButtonInfo](#setbuttoninfo)|Legt fest, die ID, Stil und Image-Anzahl der eine Schaltfläche.|  
|[CToolBar::SetButtons](#setbuttons)|Legt die Schaltfläche Formatvorlagen und einen Index der Schaltflächenbilder innerhalb der Bitmap.|  
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Legt das Format für eine Schaltfläche.|  
|[CToolBar::SetButtonText](#setbuttontext)|Legt den Text, der angezeigt wird, auf eine Schaltfläche fest.|  
|[CToolBar::SetHeight](#setheight)|Legt die Höhe der Symbolleiste.|  
|[CToolBar::SetSizes](#setsizes)|Legt die Größe der Schaltflächen und ihre Bitmaps fest.|  
  
## <a name="remarks"></a>Hinweise  
 Druckknöpfe, Kontrollkästchen Schaltflächen oder Optionsfelder können die Schaltflächen fungieren. `CToolBar` -Objekte sind in der Regel eingebettete Elemente des Rahmenfensters Objekte, die von der Klasse abgeleitet [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).  
  
 [GetToolBarCtrl](#gettoolbarctrl), eine Memberfunktion neue MFC 4.0, können Sie das allgemeine Windows-Steuerelement-Unterstützung für symbolleistenanpassung sowie zusätzliche Funktionen nutzen. `CToolBar` Memberfunktionen geben Ihnen die meisten Funktionen des allgemeinen Windows-Steuerelemente; allerdings beim Aufruf `GetToolBarCtrl`, den Symbolleisten sogar ein höherer Merkmale der Windows 95-und Windows 98 Symbolleisten erteilen. Beim Aufruf `GetToolBarCtrl`, er wird zurückgegeben, einen Verweis auf ein `CToolBarCtrl` Objekt. Finden Sie unter [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) für Weitere Informationen zum Entwerfen von Symbolleisten, die allgemeine Windows-Steuerelemente verwenden. Weitere allgemeine Informationen über allgemeine Steuerelemente finden Sie unter [Standardsteuerelementen](http://msdn.microsoft.com/library/windows/desktop/bb775493) im Windows SDK.  
  
 Visual C++ bietet Ihnen zwei Methoden zum Erstellen einer Symbolleiste. Um eine Symbolleistenressource mit dem Ressourcen-Editor zu erstellen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen Sie eine Symbolleistenressource.  
  
2.  Erstellen der `CToolBar` Objekt.  
  
3.  Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex)) Funktion zum Erstellen der Windows-Symbolleiste, und fügen Sie es auf die `CToolBar` Objekt.  
  
4.  Rufen Sie [LoadToolBar](#loadtoolbar) beim Laden der Symbolleistenressource.  
  
 Andernfalls gehen Sie folgendermaßen vor:  
  
1.  Erstellen der `CToolBar` Objekt.  
  
2.  Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex)) Funktion zum Erstellen der Windows-Symbolleiste, und fügen Sie es auf die `CToolBar` Objekt.  
  
3.  Rufen Sie [LoadBitmap](#loadbitmap) Bitmap zu laden, die die Symbolleisten-Schaltflächen enthält.  
  
4.  Rufen Sie [SetButtons](#setbuttons) So legen Sie das Schaltflächenformat und ordnen jede Schaltfläche ein Bild im Bitmap.  
  
 Die Schaltflächenbilder auf der Symbolleiste stammen aus einer einzigen Bitmap, die für jede Schaltfläche ein Bild enthalten muss. Alle Bilder müssen gleich groß sein; Der Standardwert ist 16 Pixel breit und 15 Pixeln. Bilder müssen in der Bitmap nebeneinander sein.  
  
 Die `SetButtons` Funktion verwendet einen Zeiger auf ein Array von Steuerelement-IDs und eine ganze Zahl, die die Anzahl der Elemente im Array angibt. Die Funktion legt jede Schaltfläche-ID auf den Wert des entsprechenden Elements im Array fest und weist jede Schaltfläche einen Bildindex, der die Position des Bild der Schaltfläche in der Bitmap angibt. Wenn ein Arrayelement den Wert ID_SEPARATOR hat, wird keine Abbildindex zugewiesen.  
  
 Die Reihenfolge der Bilder in der Bitmap ist in der Regel die Reihenfolge, in dem sie auf dem Bildschirm gezeichnet werden, jedoch können Sie, die [SetButtonInfo](#setbuttoninfo) Funktion so ändern Sie die Beziehung zwischen Image Reihenfolge und Zeichnungsreihenfolge.  
  
 Alle Schaltflächen einer Symbolleiste haben die gleiche Größe. Der Standardwert ist 24 x 22 Pixel, in Abhängigkeit von *Richtlinien zur Windows-Benutzeroberfläche für den Softwareentwurf*. Alle zusätzlichen Leerraum zwischen den Dimensionen-Image und die Schaltfläche wird verwendet, um einen Rahmen um das Bild zu bilden.  
  
 Jede Schaltfläche enthält ein Bild. Die verschiedenen Zustände Schaltfläche und Formatvorlagen (gedrückt, oben, unten, deaktiviert ist, deaktiviert unten, und unbestimmt) werden generiert, von dem ein Abbild aus. Obwohl Bitmaps jede Farbe sein kann, können Sie mit Bildern in Schwarz und Graustufen die besten Ergebnisse erzielen.  
  
> [!WARNING]
> `CToolBar` Bitmaps mit maximal 16 Farben wird unterstützt. Wenn Sie ein Bild in einem Symbolleisten-Editor laden, Visual Studio automatisch konvertiert ggf. das Bild in eine Bitmap mit 16 Farben und wird eine Warnmeldung angezeigt, wenn das Bild konvertiert wurde. Wenn Sie ein Image mit mehr als 16 Farben (verwenden einen externen Editor so bearbeiten Sie das Bild) verwenden, wird die Anwendung kann unerwartetes Verhalten aufweisen.  
  
 Schaltflächen der Symbolleiste imitieren Pushbuttons standardmäßig. Schaltflächen der Symbolleiste können jedoch auch Schaltflächen Kontrollkästchen oder Optionsfelder imitieren. Das Kontrollkästchen Schaltflächen drei Zustände aufweisen: aktiviert, deaktiviert und unbestimmt. Optionsfelder werden nur zwei Zustände aufweisen: aktiviert und deaktiviert.  
  
 Aufrufen, um eine einzelne Schaltfläche oder die Trennzeichen festlegen, ohne auf ein Array verweist, [GetButtonStyle](#getbuttonstyle) den Stil abzurufen, und rufen Sie anschließend [SetButtonStyle](#setbuttonstyle) anstelle von `SetButtons`. `SetButtonStyle` ist besonders hilfreich, wenn Sie eine Schaltfläche zur Laufzeit ändern möchten.  
  
 Rufen Sie zum Zuweisen von Text, der auf eine Schaltfläche angezeigt [GetButtonText](#getbuttontext) zum Abrufen des Texts auf der Schaltfläche angezeigt, und rufen Sie anschließend ["SetButtonText"](#setbuttontext) auf den Text selbst festgelegt.  
  
 Eine Kontrollkästchen-Schaltfläche "erstellen", weisen sie die Formatvorlage TBBS_CHECKBOX oder verwenden Sie eine `CCmdUI` des Objekts `SetCheck` Memberfunktion in einer ON_UPDATE_COMMAND_UI-Handler. Aufrufen von `SetCheck` Pushbutton in eine Kontrollkästchen-Schaltfläche aktiviert. Übergeben Sie `SetCheck` Argument 0 für deaktiviert wurde, 1 für aktivierte oder 2 für unbestimmt.  
  
 Um ein Optionsfeld zu erstellen, rufen eine [CCmdUI](../../mfc/reference/ccmdui-class.md) des Objekts [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) Memberfunktion ein Ereignishandler ON_UPDATE_COMMAND_UI. Übergeben Sie `SetRadio` Argument 0 deaktiviert oder ungleich NULL überprüft werden. Um einen Sender Gruppe sich gegenseitig ausschließende Verhalten zu bieten, müssen Sie in der Gruppe ON_UPDATE_COMMAND_UI-Handler für alle Schaltflächen verfügen.  
  
 Weitere Informationen zur Verwendung von `CToolBar`, finden Sie im Artikel [Implementieren der MFC-Symbolleiste](../../mfc/mfc-toolbar-implementation.md) und [technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="commandtoindex"></a>  CToolBar::CommandToIndex  
 Diese Memberfunktion gibt den Index der ersten Symbolleisten-Schaltfläche, beginnend an Position 0 (null), dessen ID entspricht `nIDFind`.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIDFind*  
 Befehls-ID, eine Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der Schaltfläche oder-1 zurück, wenn keine Schaltfläche "die angegebene Befehls-ID. wurde  
  
##  <a name="create"></a>  Symbolleistenformate  
 Diese Memberfunktion erstellt eine Windows-Symbolleiste (ein untergeordnetes Fenster) und ordnet sie der `CToolBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Ein Zeiger auf das Fenster, das auf der Symbolleiste übergeordnet ist.  
  
 *dwStyle*  
 Das Toolbar-Stil. Zusätzliche Toolbar-Stile unterstützt werden:  
  
- CBRS_TOP Steuerleiste wird am oberen Rand des Fensters Frame.  
  
- CBRS_BOTTOM Steuerleiste wird am unteren Rand der Frame-Fensters.  
  
- CBRS_NOALIGN Steuerleiste ist nicht neu angeordnet, wenn die übergeordnetem Element geändert wird.  
  
- CBRS_TOOLTIPS Steuerleiste zeigt QuickInfos an.  
  
- CBRS_SIZE_DYNAMIC Steuerleiste ist dynamisch.  
  
- CBRS_SIZE_FIXED Steuerleiste ist unveränderlich.  
  
- CBRS_FLOATING Steuerleiste unverankert ist.  
  
- CBRS_FLYBY-Statusleiste zeigt Informationen über die Schaltfläche.  
  
- CBRS_HIDE_INPLACE Steuerleiste wird dem Benutzer nicht angezeigt.  
  
 *nID*  
 Die Symbolleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Außerdem wird die Symbolleiste Höhe auf einen Standardwert festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]  
  
##  <a name="createex"></a>  CToolBar::CreateEx  
 Mit dieser Funktion wird zum Erstellen einer Windows-Symbolleiste (ein untergeordnetes Fenster), und ordnen sie die `CToolBar` Objekt.  
  
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
 *pParentWnd*  
 Ein Zeiger auf das Fenster, das auf der Symbolleiste übergeordnet ist.  
  
 *dwCtrlStyle*  
 Weitere Formate für die Erstellung der eingebetteten [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Objekt. Standardmäßig ist dieser Wert auf TBSTYLE_FLAT festgelegt. Eine vollständige Liste der Symbolleiste Formatvorlagen, finden Sie unter *DwStyle*.  
  
 *dwStyle*  
 Das Toolbar-Stil. Finden Sie unter [Toolbar-Steuerelement und Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb760439) in das Windows SDK für eine Liste der entsprechenden Stile.  
  
 *rcBorders*  
 Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Breite der Fensterrahmen Symbolleiste definiert. Dieser Rahmen werden standardmäßig, wodurch eine Symbolleiste im Fenster ohne Rahmen auf 0,0,0,0 festgelegt.  
  
 *nID*  
 Die Symbolleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Außerdem wird die Symbolleiste Höhe auf einen Standardwert festgelegt.  
  
 Verwendung `CreateEx`, anstelle von [erstellen](#create), wenn bestimmte Formate während der Erstellung der eingebetteten ToolBar-Steuerelement vorhanden sein müssen. Legen Sie z. B. *DwCtrlStyle* zu TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT zum Erstellen einer Symbolleiste, die die Internet Explorer 4 Symbolleisten ähnelt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]  
  
##  <a name="ctoolbar"></a>  CToolBar::CToolBar  
 Diese Memberfunktion erstellt eine `CToolBar` -Objekt und legt die Standardgröße einzustellen.  
  
```  
CToolBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [erstellen](#create) Memberfunktion auf der im Symbolleistenfenster zu erstellen.  
  
##  <a name="getbuttoninfo"></a>  CToolBar::GetButtonInfo  
 Diese Memberfunktion Ruft die Steuerelement-ID, Stil und Abbildindex der Symbolleisten-Schaltfläche oder an der Position angegeben, die durch Trennzeichen *nIndex.*  
  
```  
void GetButtonInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& iImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index der Symbolleisten-Schaltfläche oder Separator, deren Informationen abgerufen werden sollen.  
  
 *nID*  
 Verweis auf eine "uint", die auf die Befehls-ID der Schaltfläche festgelegt ist.  
  
 *nStyle*  
 Verweis auf eine "uint", die den Stil der Schaltfläche festgelegt ist.  
  
 *iImage*  
 Verweis auf eine ganze Zahl, die auf den Index des Schaltflächenbild innerhalb der Bitmap festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Werte werden zugewiesen, auf die verwiesen wird, indem Sie Variablen *nID*, *nStyle*, und *iImage*. Der Image-Index ist die Position des Bilds in der Bitmap, die Bilder für die Symbolleisten-Schaltflächen enthält. Das erste Bild ist an Position 0.  
  
 Wenn *nIndex* gibt ein Trennzeichen *iImage* auf die trennzeichenbreite in Pixel festgelegt ist.  
  
##  <a name="getbuttonstyle"></a>  CToolBar::GetButtonStyle  
 Rufen Sie diese Memberfunktion um den Stil der eine Schaltfläche oder ein Trennzeichen auf der Symbolleiste abzurufen.  
  
```  
UINT GetButtonStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Symbolleisten-Schaltfläche oder eines Trennzeichens Formats abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Format der Schaltfläche oder Trennzeichen gemäß *nIndex*.  
  
### <a name="remarks"></a>Hinweise  
 Eine Schaltfläche Format bestimmt, wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert. Finden Sie unter [SetButtonStyle](#setbuttonstyle) Schaltflächenstile Beispiele.  
  
##  <a name="getbuttontext"></a>  CToolBar::GetButtonText  
 Rufen Sie diese Memberfunktion zum Abrufen des Texts, der auf eine Schaltfläche angezeigt wird.  
  
```  
CString GetButtonText(int nIndex) const;  
  
void GetButtonText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Texts abgerufen werden sollen.  
  
 *rString*  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das auf den Text abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den Text der Schaltfläche enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit dem Zeichenfolgentext.  
  
##  <a name="getitemid"></a>  CToolBar::GetItemID  
 Diese Memberfunktion gibt die Befehls-ID der Schaltfläche oder Trennzeichen gemäß *nIndex*.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Elements, dessen ID abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID der Schaltfläche oder Trennzeichen gemäß *nIndex*.  
  
### <a name="remarks"></a>Hinweise  
 Trennzeichen zurück ID_SEPARATOR  
  
##  <a name="getitemrect"></a>  CToolBar::GetItemRect  
 Diese Memberfunktion füllt die `RECT` Struktur, deren Adresse sich in befindet *LpRect* mit den Koordinaten der Schaltfläche oder Trennzeichen, die gemäß *nIndex*.  
  
```  
virtual void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Elements (Schaltfläche oder ein Trennzeichen), dessen Rechteckkoordinaten sind, abgerufen werden sollen.  
  
 *lpRect*  
 Der Adresse der [RECT](../../mfc/reference/rect-structure1.md) Struktur, die Koordinaten für das Element enthalten soll.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zur linken oberen Ecke der Symbolleiste.  
  
 Verwendung `GetItemRect` , die Koordinaten eines Trennzeichens erhalten Sie durch ein Kombinationsfeld oder ein anderes Steuerelement ersetzen möchten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CToolBar::SetSizes](#setsizes).  
  
##  <a name="gettoolbarctrl"></a>  GetToolBarCtrl  
 Diese Memberfunktion ermöglicht den direkten Zugriff auf die zugrunde liegenden Standardsteuerelements.  
  
```  
CToolBarCtrl& GetToolBarCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein `CToolBarCtrl`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `GetToolBarCtrl` die Funktionalität des allgemeinen Symbolleisten-Steuerelements von Windows nutzen und die Unterstützung nutzen [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) symbolleistenanpassung bereit.  
  
 Weitere Informationen zum Verwenden von allgemeinen Steuerelementen finden Sie im Artikel [Steuerelemente](../../mfc/controls-mfc.md) und [Standardsteuerelementen](http://msdn.microsoft.com/library/windows/desktop/bb775493) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]  
  
##  <a name="loadbitmap"></a>  CToolBar::LoadBitmap  
 Rufen Sie diese Memberfunktion zum Laden von angegebenen Bitmap `lpszResourceName` oder `nIDResource`.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszResourceName*  
 Ein Zeiger auf den Ressourcennamen der Bitmap geladen werden soll.  
  
 *nIDResource*  
 Ressourcen-ID der Bitmap geladen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap muss für jede Symbolleisten-Schaltfläche ein Bild enthalten. Wenn die Bilder nicht Aufruf der die Standardgröße (16 Pixel breit und 15 Pixel hoch) sind [SetSizes](#setsizes) , legen Sie die Schaltfläche Größen und Bilder.  
  
> [!WARNING]
> `CToolBar` Bitmaps mit maximal 16 Farben wird unterstützt. Wenn Sie ein Bild in einem Symbolleisten-Editor laden, Visual Studio automatisch konvertiert ggf. das Bild in eine Bitmap mit 16 Farben und wird eine Warnmeldung angezeigt, wenn das Bild konvertiert wurde. Wenn Sie ein Image mit mehr als 16 Farben (verwenden einen externen Editor so bearbeiten Sie das Bild) verwenden, wird die Anwendung kann unerwartetes Verhalten aufweisen.  
  
##  <a name="loadtoolbar"></a>  CToolBar::LoadToolBar  
 Rufen Sie diese Memberfunktion zum Laden der Symbolleiste von angegebenen *LpszResourceName* oder *nIDResource*.  
  
```  
BOOL LoadToolBar(LPCTSTR lpszResourceName);  
BOOL LoadToolBar(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszResourceName*  
 Ein Zeiger auf den Ressourcennamen, der Symbolleiste geladen werden soll.  
  
 *nIDResource*  
 Ressourcen-ID der Symbolleiste geladen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Symbolleisten-Editor](../../windows/toolbar-editor.md) in Weitere Informationen zum Erstellen einer Symbolleistenressource.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CToolBar::CreateEx](#createex).  
  
##  <a name="setbitmap"></a>  CToolBar::SetBitmap  
 Rufen Sie diese Memberfunktion, um das Bitmap-Bild für die Symbolleiste festzulegen.  
  
```  
BOOL SetBitmap(HBITMAP hbmImageWell);
```  
  
### <a name="parameters"></a>Parameter  
 *hbmImageWell*  
 Das Handle des eine Bitmap, die eine Symbolleiste zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie z. B. `SetBitmap` als Bitmap verfügbares Bild zu ändern, nachdem der Benutzer eine Aktion für ein Dokument ausgeführt wird, die die Aktion einer Schaltfläche ändert.  
  
##  <a name="setbuttoninfo"></a>  CToolBar::SetButtonInfo  
 Rufen Sie diese Memberfunktion zum Festlegen der Befehls-ID, Stil und Image-Anzahl der Schaltfläche.  
  
```  
void SetButtonInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Nullbasierte Index der Schaltfläche oder Trennzeichen für die Informationen sind, festgelegt werden.  
  
 *nID*  
 Der Wert, den die Befehlsschaltfläche-ID festgelegt ist.  
  
 *nStyle*  
 Die neue Schaltfläche-Formatvorlage. Die folgende Schaltflächenstile werden unterstützt:  
  
- TBBS_BUTTON standardmäßige Pushbutton (Standard)  
  
- TBBS_SEPARATOR Trennzeichen  
  
- Automatische TBBS_CHECKBOX Kontrollkästchen Schaltfläche  
  
- TBBS_GROUP kennzeichnet den Anfang einer Gruppe von Optionsfeldern  
  
- TBBS_CHECKGROUP kennzeichnet den Beginn einer Gruppe von Kontrollkästchen Schaltflächen  
  
- TBBS_DROPDOWN erstellt eine Schaltfläche Dropdown-Liste.  
  
- TBBS_AUTOSIZE, die die Breite der Schaltfläche berechnet werden sollen, basierend auf den Text der Schaltfläche nicht auf die Größe des Bilds.  
  
- TBBS_NOPREFIX müssen der Text der Schaltfläche keine Zugriffstaste Präfix zugeordnet.  
  
 *iImage*  
 Neue Index für das Bild der Schaltfläche in der Bitmap.  
  
### <a name="remarks"></a>Hinweise  
 Für Trennzeichen, die den Stil TBBS_SEPARATOR haben, setzt diese Funktion das Trennzeichen Breite in Pixel, um den Wert in gespeicherten *iImage*.  
  
> [!NOTE]
>  Sie können auch mit Schaltflächenzuständen Festlegen der *nStyle* Parameter jedoch da Schaltflächenzuständen von gesteuert werden die [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) Handler auf, alle Status Sie festlegen, über `SetButtonInfo` verloren während der Verarbeitung der nächsten im Leerlauf. Finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Schiebeleisten-Steuerelemente](../../mfc/tn031-control-bars.md) für Weitere Informationen.  
  
 Informationen zu Schaltflächen und Bitmapbildern, finden Sie unter der [CToolBar](../../mfc/reference/ctoolbar-class.md) Übersicht und [CToolBar::LoadBitmap](#loadbitmap).  
  
##  <a name="setbuttons"></a>  CToolBar::SetButtons  
 Diese Memberfunktion setzt die Befehls-ID für jede Symbolleisten-Schaltfläche auf den Wert, der durch das entsprechende Element im Array angegebenen *LpIDArray*.  
  
```  
BOOL SetButtons(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parameter  
 *lpIDArray*  
 Zeiger auf ein Array mit Befehls-Ids. NULL, um leere Schaltflächen zuzuordnen sind möglich.  
  
 *nIDCount*  
 Anzahl der Elemente im Array verweist *LpIDArray*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Element des Arrays den Wert ID_SEPARATOR hat, wird eine Trennzeichen in der entsprechenden Position der Symbolleiste erstellt. Diese Funktion wird auch jede Schaltfläche Format TBBS_BUTTON und jedes Trennzeichen Stil TBBS_SEPARATOR festgelegt und weist einen Abbildindex zu jeder Schaltfläche. Der Bildindex gibt die Position des Schaltflächenbild innerhalb der Bitmap an.  
  
 Sie müssen keine Trennzeichen in der Bitmap zu berücksichtigen, da diese Funktion nicht Image Indizes für Trennzeichen zuweist. Wenn die Symbolleiste Schaltflächen an der Position 0 aufweist, sind 1 und 3 und ein Trennzeichen an Position 2, die Bilder an den Positionen, die in der Bitmap 0, 1 und 2 auf die Schaltflächen an den Positionen, 0, 1 und 3, zugewiesen.  
  
 Wenn *LpIDArray* NULL ist, diese Funktion reserviert Speicherplatz für die Anzahl der Elemente, die vom angegebenen *nIDCount*. Verwendung [SetButtonInfo](#setbuttoninfo) Attribute für jedes Element festlegen.  
  
##  <a name="setbuttonstyle"></a>  CToolBar::SetButtonStyle  
 Rufen Sie diese Memberfunktion um den Stil des eine Schaltfläche oder ein Trennzeichen oder zum Gruppieren festzulegen.  
  
```  
void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index der Schaltfläche oder Separator, deren Informationen festgelegt werden.  
  
 *nStyle*  
 Das Schaltflächenformat. Die folgende Schaltflächenstile werden unterstützt:  
  
- TBBS_BUTTON standardmäßige Pushbutton (Standard)  
  
- TBBS_SEPARATOR Trennzeichen  
  
- Automatische TBBS_CHECKBOX Kontrollkästchen Schaltfläche  
  
- TBBS_GROUP kennzeichnet den Anfang einer Gruppe von Optionsfeldern  
  
- TBBS_CHECKGROUP kennzeichnet den Beginn einer Gruppe von Kontrollkästchen Schaltflächen  
  
- TBBS_DROPDOWN erstellt eine Dropdownliste-Schaltfläche  
  
- TBBS_AUTOSIZE, die die Breite der Schaltfläche berechnet wird basierend auf den Text der Schaltfläche nicht auf die Größe des Bilds  
  
- TBBS_NOPREFIX der Text der Schaltfläche eine Zugriffstaste Präfix zugeordnet keine  
  
### <a name="remarks"></a>Hinweise  
 Eine Schaltfläche Format bestimmt, wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert.  
  
 Vor dem Aufruf `SetButtonStyle`, rufen Sie die [GetButtonStyle](#getbuttonstyle) Memberfunktion versucht, den Stil Schaltfläche oder ein Trennzeichen abzurufen.  
  
> [!NOTE]
>  Sie können auch mit Schaltflächenzuständen Festlegen der *nStyle* Parameter jedoch da Schaltflächenzuständen von gesteuert werden die [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) Handler auf, alle Status Sie festlegen, über `SetButtonStyle` verloren während der Verarbeitung der nächsten im Leerlauf. Finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md) und [TN031: Schiebeleisten-Steuerelemente](../../mfc/tn031-control-bars.md) für Weitere Informationen.  
  
##  <a name="setbuttontext"></a>  CToolBar::SetButtonText  
 Rufen Sie diese Funktion, um den Text in einer Schaltfläche festzulegen.  
  
```  
BOOL SetButtonText(
    int nIndex,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Index der Schaltfläche, dessen Text ist, festgelegt werden.  
  
 *lpszText*  
 Verweist auf den Text auf eine Schaltfläche festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetToolBarCtrl](#gettoolbarctrl).  
  
##  <a name="setheight"></a>  CToolBar::SetHeight  
 Diese Memberfunktion setzt die Höhe der Symbolleiste auf den Wert, in Pixel, die im angegebenen *CyHeight*.  
  
```  
void SetHeight(int cyHeight);
```  
  
### <a name="parameters"></a>Parameter  
 *cyHeight*  
 Die Höhe in Pixel der Symbolleiste.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf [SetSizes](#setsizes), verwenden Sie diese Memberfunktion auf, um die Höhe der Standardsymbolleiste zu überschreiben. Wenn die Höhe zu klein ist, werden die Schaltflächen im unteren Bereich abgeschnitten.  
  
 Wenn diese Funktion nicht aufgerufen wird, verwendet das Framework die Größe der Schaltfläche auf der Symbolleiste Höhe bestimmt.  
  
##  <a name="setsizes"></a>  CToolBar::SetSizes  
 Rufen Sie diese Memberfunktion zum Festlegen von Schaltflächen der Symbolleiste auf die Größe in Pixel, die im angegebenen *SizeButton*.  
  
```  
void SetSizes(
    SIZE sizeButton,  
    SIZE sizeImage);
```  
  
### <a name="parameters"></a>Parameter  
 *sizeButton*  
 Die Größe in Pixel der einzelnen Schaltflächen.  
  
 *sizeImage*  
 Die Größe des jedes Bilds in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Die *SizeImage* Parameter muss die Größe in Pixel der Bilder in der Symbolleiste auf die Bitmap enthalten. Die Dimensionen in *SizeButton* muss ausreichend, um das Bild plus 7 Pixel breit zusätzliche und zusätzliche in Höhe von 6 Pixel enthalten sein. Diese Funktion legt auch die Höhe der Symbolleiste die Schaltflächen an.  
  
 Rufen Sie diese Memberfunktion nur für Symbolleisten, die nicht befolgt werden *Richtlinien zur Windows-Benutzeroberfläche für den Softwareentwurf* Empfehlungen für Schaltfläche und Image-Größen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel jeder](../../visual-cpp-samples.md)   
 [MFC-Beispiel DLGCBR32](../../visual-cpp-samples.md)   
 [MFC-Beispiel DOCKTOOL](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl-Klasse](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)
