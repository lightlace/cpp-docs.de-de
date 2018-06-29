---
title: CReBarCtrl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
dev_langs:
- C++
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85a3c51f5c59b510e1024cc5f363096952c0f35a
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079461"
---
# <a name="crebarctrl-class"></a>CReBarCtrl-Klasse
Kapselt die Funktionalität eines Grundleisten-Steuerelements. Dabei handelt es sich um einen Container für ein untergeordnetes Fenster.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Erstellt ein `CReBarCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Platziert die Grundleisten-Steuerelement in den Drag & Drop-Modus.|  
|[CReBarCtrl::Create](#create)|Erstellt das Grundleistensteuerelement, und fügt es der `CReBarCtrl` Objekt.|  
|[CReBarCtrl::CreateEx](#createex)|Erstellt ein Grundleistensteuerelement mit der angegebenen erweiterten Fensterstile und fügt es einer `CReBarCtrl` Objekt.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Löscht ein Band von einem Grundleisten-Steuerelement.|  
|[CReBarCtrl::DragMove](#dragmove)|Aktualisiert die Position ziehen Sie in der Grundleisten-Steuerelement nach einem Aufruf von `BeginDrag`.|  
|[CReBarCtrl::EndDrag](#enddrag)|Beendet die Grundleisten-Steuerelement Drag & Drop-Vorgang.|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|Ruft die Ränder eines Bandes ab.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Ruft die Anzahl der Bänder, die derzeit in der Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Ruft Informationen zu einer angegebenen Band in einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Ruft die Ränder eines Bandes ab.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Ruft die Höhe des Grundleisten-Steuerelements ab.|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Ruft Informationen zu den Grundleisten-Steuerelement und die Bildliste verwendeten ab.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Ruft die Standardhintergrundfarbe einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Ruft die [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Struktur Grundleisten-Steuerelement zugeordnet ist.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Ruft ein Grundleistensteuerelement `IDropTarget` Schnittstellenzeiger auf.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Ruft den erweiterten Stil des aktuellen Grundleisten-Steuerelements ab.|  
|[CReBarCtrl::GetImageList](#getimagelist)|Ruft die einem Grundleistensteuerelement zugeordnete Bildliste ab.|  
|[CReBarCtrl::GetPalette](#getpalette)|Ruft die aktuelle Palette Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck für eine angegebene Band in einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Ruft die Anzahl der Band Zeilen in einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Ruft die Höhe einer angegebenen Zeile in einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Ruft die Standardtextfarbe einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Ruft das Handle für alle Grundleisten-Steuerelement zugeordneten QuickInfo-Steuerelement ab.|  
|[CReBarCtrl::HitTest](#hittest)|Bestimmt die Teil einer Infoleistenband ist zu einem bestimmten Zeitpunkt auf dem Bildschirm angezeigt, wenn ein Band Grundleisten an diesem Punkt vorhanden ist.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Konvertiert einen Band Bezeichner (ID) zu einem Band Index in einem Grundleisten-Steuerelement.|  
|[CReBarCtrl:: InsertBand](#insertband)|Fügt ein neues Band in einem Grundleisten-Steuerelement.|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|Ändert ein Band in einem Grundleisten-Steuerelement auf die maximale Größe an.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|Ändert ein Band in einem Grundleisten-Steuerelement auf die kleinste Größe an.|  
|[CReBarCtrl::MoveBand](#moveband)|Verschiebt ein Band von einem Index.|  
|[CReBarCtrl::PushChevron](#pushchevron)|Es wird ein Chevron programmgesteuert.|  
|[CReBarCtrl::RestoreBand](#restoreband)|Ändert die Größe ein Band in einem Grundleisten-Steuerelement, um die ideale Größe.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Legt die Eigenschaften einer vorhandenen Band in einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Legt die Breite des angegebenen angedockten Band in der aktuellen Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Legt die Eigenschaften eines Grundleisten-Steuerelements fest.|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Legt die Standardhintergrundfarbe einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Legt das Farbschema für die Schaltflächen in einem Grundleistensteuerelement fest.|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile für das aktuelle Grundleistensteuerelement fest.|  
|[CReBarCtrl::SetImageList](#setimagelist)|Legt die Bildliste einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetOwner](#setowner)|Legt ein Grundleistensteuerelement Besitzerfenster fest.|  
|[CReBarCtrl::SetPalette](#setpalette)|Legt die aktuelle Palette Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Legt die Standardtextfarbe einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Ordnet die Grundleisten-Steuerelement ein QuickInfo-Steuerelement hinzu.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil der Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::ShowBand](#showband)|Zeigt an, oder blendet Sie aus einer angegebenen Band in einem Grundleisten-Steuerelement.|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Entspricht einem Grundleisten-Steuerelement zu einem bestimmten Rechteck.|  
  
## <a name="remarks"></a>Hinweise  
 Die Anwendung, in der die Grundleisten-Steuerelement sich befindet, weist das untergeordnete Fenster Grundleisten-Steuerelement auf dem Band Grundleisten enthalten sind. Das untergeordnete Fenster ist in der Regel eine andere Standardsteuerelements.  
  
 Rebar-Steuerelemente enthalten eine oder mehrere Bänder. Jedes Band kann eine Kombination des ziehelements-Leiste, eine Bitmap, einer textbezeichnung und ein untergeordnetes Fenster enthalten. Das Band kann nur eines dieser Elemente enthalten.  
  
 Grundleisten-Steuerelement kann das untergeordnete Fenster über einen angegebenen Hintergrundbitmap angezeigt. Alle rebarbereichen Steuerelement geändert werden können, mit Ausnahme derjenigen, mit denen die **RBBS_FIXEDSIZE** Stil. Wie Sie neu positionieren, oder ändern ein Band der Grundleisten-Steuerelement, verwaltet Grundleisten-Steuerelement an die Größe und Position des untergeordneten Fensters dieses Band zugewiesen. Klicken Sie zum Ändern der Größe oder die Reihenfolge der Bänder innerhalb des Steuerelements ändern, klicken Sie auf, und ziehen Sie ein Band ziehelements Leiste.  
  
 Die folgende Abbildung zeigt ein Grundleistensteuerelement, das drei Bändern:  
  
-   Band 0 enthält einen flachen, transparente Symbolleisten-Steuerelement.  
  
-   Band 1 enthält beide transparente standard und transparente Dropdown-Schaltflächen.  
  
-   Band 2 enthält ein Kombinationsfeld und vier Standardschaltflächen.  
  
     ![Beispiel eines grundleistenmenüs](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Grundleisten-Steuerelement  
 Grundleisten Sie-Steuerelemente unterstützen:  
  
-   Bilderliste für das.  
  
-   Meldungsbehandlung.  
  
-   Benutzerdefiniertes Zeichnen Funktionalität.  
  
-   Eine Vielzahl von Steuerelementtypen für die zusätzlich zu den standardmäßigen Fensterstile. Eine Liste dieser Stile, finden Sie unter [Grundleisten-Steuerelementtypen für die](http://msdn.microsoft.com/library/windows/desktop/bb774377) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag  
 Implementiert das Verhalten der Win32-Nachricht [RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429)gemäß der Beschreibung im Windows SDK.  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands, die der Drag-and-Drop-Vorgang auswirkt.  
  
 *dwPos*  
 Ein `DWORD` -Wert, beginnend Mauskoordinaten enthält. Die horizontale Koordinate in der LOWORD enthalten ist, und die vertikale Koordinate in die HIWORD enthalten ist. Wenn Sie übergeben `(DWORD)-1`, Grundleisten-Steuerelement verwendet die Position der Maus der letzten Ausführung des Steuerelements Thread aufgerufen `GetMessage` oder `PeekMessage`.  
  
##  <a name="create"></a>  CReBarCtrl::Create  
 Erstellt das Grundleistensteuerelement, und fügt es der `CReBarCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *dwStyle*  
 Gibt die Kombination von Grundleisten-Steuerelementtypen, die auf das Steuerelement angewendet. Finden Sie unter [Grundleisten-Steuerelementtypen für die](http://msdn.microsoft.com/library/windows/desktop/bb774377) in das Windows SDK für eine Liste der unterstützten Formate.  
  
 *Rect*  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Position und Größe des Grundleisten-Steuerelements ist.  
  
 *pParentWnd*  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt, das das übergeordnete Fenster eines Grundleisten-Steuerelement darstellt. Es muss nicht **NULL**.  
  
 *nID*  
 Gibt an, das Grundleisten-Steuerelement-Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen eines Grundleisten-Steuerelements in zwei Schritten:  
  
1.  Rufen Sie [CReBarCtrl](#crebarctrl) zum Erstellen einer `CReBarCtrl` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die Windows-Grundleisten-Steuerelement erstellt, und fügt es der `CReBarCtrl` Objekt.  
  
 Beim Aufruf **erstellen**, die allgemeine Steuerelemente werden initialisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CReBarCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CReBarCtrl` Objekt.  
  
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
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der *DwExStyle* -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 *dwStyle*  
 Gibt die Kombination von Grundleisten-Steuerelementtypen, die auf das Steuerelement angewendet. Eine Liste der unterstützten Formate finden Sie unter [Grundleisten-Steuerelementtypen für die](http://msdn.microsoft.com/library/windows/desktop/bb774377) im Windows SDK.  
  
 *Rect*  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der *pParentWnd*.  
  
 *pParentWnd*  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 *nID*  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl  
 Erstellt ein `CReBarCtrl`-Objekt.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CReBarCtrl::Create](#create).  
  
##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands gelöscht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Band wurde erfolgreich gelöscht; andernfalls 0 (null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="dragmove"></a>  CReBarCtrl::DragMove  
 Implementiert das Verhalten der Win32-Nachricht [RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx)gemäß der Beschreibung im Windows SDK.  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Parameter  
 *dwPos*  
 Ein `DWORD` Wert, der die neue Mauskoordinaten enthält. Die horizontale Koordinate in der LOWORD enthalten ist, und die vertikale Koordinate in die HIWORD enthalten ist. Wenn Sie übergeben `(DWORD)-1`, Grundleisten-Steuerelement verwendet die Position der Maus der letzten Ausführung des Steuerelements Thread aufgerufen `GetMessage` oder `PeekMessage`.  
  
##  <a name="enddrag"></a>  CReBarCtrl::EndDrag  
 Implementiert das Verhalten der Win32-Nachricht [RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435)gemäß der Beschreibung im Windows SDK.  
  
```  
void EndDrag();
```  
  
##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437)gemäß der Beschreibung im Windows SDK.  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands für die Rahmen abgerufen werden sollen.  
  
 *VR China*  
 Ein Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Rahmen Band erhält. Wenn das Grundleistensteuerelement verfügt die **RBS_BANDBORDERS** Stil jedes Mitglied dieser Struktur erhalten die Anzahl der Pixel auf der entsprechenden Seite des das Band, das den Rahmen darstellen. Wenn das Grundleistensteuerelement keinen der **RBS_BANDBORDERS** formatieren, nur das linke Element dieser Struktur gültige Informationen empfängt. Eine Beschreibung der Stile für Grundleisten-Steuerelemente, finden Sie unter [Steuerelementtypen für die Infoleiste](http://msdn.microsoft.com/library/windows/desktop/bb774377) im Windows SDK.  
  
##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439)gemäß der Beschreibung im Windows SDK.  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bänder, die dem Steuerelement zugewiesen werden soll.  
  
##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) wie beschrieben im Windows SDK.  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands für die die Informationen abgerufen werden sollen.  
  
 *prbbi*  
 Ein Zeiger auf eine [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur das Band Informationen zu erhalten. Müssen Sie festlegen der `cbSize` Mitglied dieser Struktur zu `sizeof(REBARBANDINFO)` und legen Sie die **fMask** Member zu den Elementen, die Sie vor dem Senden dieser Nachricht abrufen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins  
 Ruft die Ränder des Bands ab.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>Parameter  
 *pMargins*  
 Ein Zeiger auf eine [RÄNDER](http://msdn.microsoft.com/library/windows/desktop/bb773244)-Struktur, die die Informationen erhält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) Nachricht, wie im Windows SDK beschrieben.  
  
##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight  
 Ruft die Höhe des Balkens Grundleisten ab.  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert, der die Höhe des Steuerelements in Pixel darstellt.  
  
##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *prbi*  
 Ein Zeiger auf eine [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) -Struktur, die die Grundleisten-Steuerelement-Informationen erhält. Sie müssen festlegen, die *CbSize* Mitglied dieser Struktur zu `sizeof(REBARINFO)` vor dem Senden dieser Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459)gemäß der Beschreibung im Windows SDK.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die aktuelle Standardhintergrundfarbe darstellen.  
  
##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme  
 Ruft die [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Struktur für das Grundleistensteuerelement.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Parameter  
 *LPCs*  
 Ein Zeiger auf eine [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) strukturieren, wie im Windows SDK beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die **COLORSCHEME** Struktur enthält die Hervorhebungsfarbe für Schaltfläche und die Schattenfarbe Schaltfläche.  
  
##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463)gemäß der Beschreibung im Windows SDK.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle.  
  
##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle  
 Ruft die erweiterten Stile des aktuellen Grundleisten-Steuerelements ab.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination (OR) von Flags, die die erweiterten Stile angeben. Die möglichen Flags sind `RBS_EX_SPLITTER` und `RBS_EX_TRANSPARENT`. Weitere Informationen finden Sie unter der *DwMask* Parameter von der [CReBarCtrl::SetExtendedStyle](#setextendedstyle) Methode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList  
 Ruft die `CImageList` Objekt mit einem Grundleisten-Steuerelement zugewiesen ist.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt. Gibt **NULL** Wenn keine Bildliste für das Steuerelement festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verwendet im gespeicherten Informationen zu Größe und die Subnetzmaske der [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) strukturieren, wie im Windows SDK beschrieben.  
  
##  <a name="getpalette"></a>  CReBarCtrl::GetPalette  
 Ruft die aktuelle Palette Grundleisten-Steuerelement ab.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md) Objekt, das aktuelle Palette Grundleisten-Steuerelement angibt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die diese Memberfunktion verwendet ein `CPalette` Objekt als Rückgabewert, anstelle einer `HPALETTE`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="getrect"></a>  CReBarCtrl::GetRect  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index, der ein Band in der Grundleisten-Steuerelement.  
  
 *VR China*  
 Ein Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Grenzen des Bands Grundleisten erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471)gemäß der Beschreibung im Windows SDK.  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **"uint"** Wert, der die Anzahl der Band Zeilen im Steuerelement darstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473)gemäß der Beschreibung im Windows SDK.  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *uRow*  
 Nullbasierte Index des Bands, die die Höhe abgerufen hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **"uint"** Wert, der die Höhe der Zeilen, in Pixel darstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475)gemäß der Beschreibung im Windows SDK.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die aktuelle Standard-Textfarbe darstellen.  
  
##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477)gemäß der Beschreibung im Windows SDK.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die MFC-Implementierung von `GetToolTips` gibt einen Zeiger auf eine `CToolTipCtrl`, anstelle einer `HWND`.  
  
##  <a name="hittest"></a>  CReBarCtrl::HitTest  
 Implementiert das Verhalten der Win32-Nachricht [RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494)gemäß der Beschreibung im Windows SDK.  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>Parameter  
 *prbht*  
 Ein Zeiger auf eine [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391) Struktur. Vor dem Senden der Nachricht die **pt** Mitglied dieser Struktur muss initialisiert werden, zu dem Punkt, die getestet werden, in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Bands an den angegebenen Punkt, andernfalls-1 wurde kein Band Grundleisten an dem Punkt.  
  
##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex  
 Implementiert das Verhalten der Win32-Nachricht [RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496)gemäß der Beschreibung im Windows SDK.  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *uBandID*  
 Übergeben Sie der Anwendung definierte Bezeichner des angegebenen Bands der **wID** Mitglied der [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur, wenn das Band eingefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Band Index im Erfolgsfall oder andernfalls -1. Wenn doppelte Band Indizes vorhanden sind, wird die erste Vorlage zurückgegeben.  
  
##  <a name="insertband"></a>  CReBarCtrl:: InsertBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Parameter  
 *uIndex*  
 Nullbasierte Index des Speicherorts, in dem das Band eingefügt wird. Wenn Sie diesen Parameter auf-1 festlegen, wird das Steuerelement das neue Band an der letzten Position hinzufügen.  
  
 *prbbi*  
 Ein Zeiger auf eine [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) -Struktur, die definiert, das Band aus, die eingefügt werden soll. Sie müssen festlegen, die *CbSize* Mitglied dieser Struktur zu `sizeof(REBARBANDINFO)` vor dem Aufrufen dieser Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand  
 Ändert ein Band in einem Grundleisten-Steuerelement auf die maximale Größe an.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands, maximiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) mit `fIdeal` auf 0 festgelegt, wie im Windows SDK beschrieben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand  
 Ändert ein Band in einem Grundleisten-Steuerelement auf die kleinste Größe an.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands minimiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert das Verhalten der Win32-Nachricht [RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="moveband"></a>  CReBarCtrl::MoveBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>Parameter  
 *uFrom*  
 Nullbasierte Index des Bands verschoben werden soll.  
  
 *utomatisch*  
 Nullbasierte Index der Position des neuen Band. Dieser Parameterwert muss niemals größer als die Anzahl der Bänder, die minus eins. Um die Anzahl der Bänder zu erhalten, rufen Sie [GetBandCount](#getbandcount).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron  
 Implementiert das Verhalten der Win32-Nachricht [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506)gemäß der Beschreibung im Windows SDK.  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands, deren Chevron wird verschoben werden.  
  
 *lAppValue*  
 Eine Anwendung definiert die 32-Bit-Wert. Finden Sie unter *lAppValue* in [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506) im Windows SDK.  
  
##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand  
 Ändert die Größe ein Band in einem Grundleisten-Steuerelement, um die ideale Größe.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands, maximiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) mit `fIdeal` auf 1 festgelegt, wie im Windows SDK beschrieben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index des Bands an den neuen Einstellungen zu erhalten.  
  
 *prbbi*  
 Zeiger auf eine [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) -Struktur, die definiert, das Band aus, die eingefügt werden soll. Sie müssen festlegen, die `cbSize` Mitglied dieser Struktur zu `sizeof(REBARBANDINFO)` vor dem Senden dieser Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth  
 Legt die Breite des angegebenen angedockten Band in der aktuellen Grundleisten-Steuerelement fest.  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *uBand*|Nullbasierte Index von einem Grundleisten-Band.|  
|[in] *CxWidth*|Neue Breite des Bands Infoleiste in Pixel.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_rebar`, d. h. auf das aktuelle Grundleistensteuerelement verwendet. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt fest, jede Grundleisten-Bereichs an die gleiche Breite.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>Parameter  
 *prbi*  
 Ein Zeiger auf eine [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) -Struktur, die die Informationen enthält, festgelegt werden sollen. Sie müssen festlegen, die `cbSize` Mitglied dieser Struktur zu `sizeof(REBARINFO)` vor dem Senden dieser Nachricht  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515)gemäß der Beschreibung im Windows SDK.  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 *CLR*  
 Die **COLORREF** Wert, der die neue Standard-Hintergrundfarbe darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die vorherige Standardhintergrundfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Thema enthält weitere Informationen zum beim Festlegen der Hintergrundfarbe und zum Festlegen des standardmäßigen angezeigt wird  
  
##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme  
 Legt das Farbschema für die Schaltflächen in einem Grundleistensteuerelement fest.  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcs`  
 Ein Zeiger auf eine [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) strukturieren, wie im Windows SDK beschrieben.  
  
### <a name="remarks"></a>Hinweise  
 Die **COLORSCHEME** Struktur enthält die Hervorhebungsfarbe für Schaltfläche und die Schattenfarbe Schaltfläche.  
  
##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle  
 Legt die erweiterten Stile für das aktuelle Grundleistensteuerelement fest.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *DwMask*|Eine bitweise Kombination (OR) von Flags, die angeben, welche Flags in der *DwStyleEx* Parameter angewendet. Verwenden Sie eine oder mehrere der folgenden Werte:<br /><br /> RBS_EX_SPLITTER: Standardmäßig zeigen Sie Splitters im unteren Bereich im horizontalen Modus, und klicken Sie rechts im vertikalen Modus an.<br /><br /> RBS_EX_TRANSPARENT: Weiterleiten der [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) Nachricht an das übergeordnete Fenster.|  
|[in] *DwStyleEx*|Eine bitweise Kombination (OR) von Flags, die angeben, die Stile übernehmen. Eine Formatvorlage festlegen möchten, geben die gleichen Kennzeichen, das verwendet werden die *DwMask* Parameter. Geben Sie zum Zurücksetzen eines Stils binäre 0 (null).|  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige erweiterter Stil.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList  
 Weist eine Bildliste einem Grundleisten-Steuerelement.  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 *pImageList*  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt, enthält die Bildliste, Grundleisten-Steuerelements zugewiesen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
##  <a name="setowner"></a>  CReBarCtrl::SetOwner  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522)gemäß der Beschreibung im Windows SDK.  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pWnd*  
 Ein Zeiger auf ein `CWnd` Objekt, das als Besitzer des Grundleisten-Steuerelement festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das der aktuelle Besitzer des Grundleisten-Steuerelements ist.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Memberfunktion Zeiger auf verwendet `CWnd` Objekte für den aktuellen und dem ausgewählten Besitzer eines Grundleisten-Steuerelement, statt Windows behandelt.  
  
> [!NOTE]
>  Diese Memberfunktion ändert sich nicht auf das aktuelle übergeordnete Element aus, das festgelegt wurde, wenn das Steuerelement erstellt wurde; Stattdessen sendet er benachrichtigungsmeldungen an das Fenster, das Sie angeben.  
  
##  <a name="setpalette"></a>  CReBarCtrl::SetPalette  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520)gemäß der Beschreibung im Windows SDK.  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>Parameter  
 *hPal*  
 Ein `HPALETTE` , angibt, dass die neue Palette, die das Grundleistensteuerelement verwenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md) -Objekt, das Grundleisten-Steuerelement vorherigen Palette angibt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die diese Memberfunktion verwendet ein `CPalette` Objekt als Rückgabewert, anstelle einer `HPALETTE`.  
  
##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524)gemäß der Beschreibung im Windows SDK.  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 *CLR*  
 Ein **COLORREF** Wert, der den neuen Text darstellt Farbe in der `CReBarCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) zugeordneten Wert, der die vorherige Textfarbe darstellt der `CReBarCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Er wird bereitgestellt, um Text Farbe Flexibilität in einem Grundleisten-Steuerelement zu unterstützen.  
  
##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips  
 Ordnet ein QuickInfo-Steuerelement mit einem Grundleisten-Steuerelement.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>Parameter  
 *pToolTip*  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Zerstören der `CToolTipCtrl` Objekt, wenn Sie damit fertig sind.  
  
##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme  
 Legt den visuellen Stil der Grundleisten-Steuerelement fest.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 *pszSubAppName*  
 Ein Zeiger auf eine Unicode-Zeichenfolge, die den visuellen Stil der Infoleiste festzulegende enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) Nachricht, wie im Windows SDK beschrieben.  
  
##  <a name="showband"></a>  CReBarCtrl::ShowBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *uBand*  
 Nullbasierte Index, der ein Band in der Grundleisten-Steuerelement.  
  
 *fShow*  
 Gibt an, ob das Band ein- oder ausgeblendet werden soll. Wenn dieser Wert ist **"true"**, das Band wird angezeigt. Andernfalls wird das Band ausgeblendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect  
 Implementiert das Verhalten der Win32-Nachricht [RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534)gemäß der Beschreibung im Windows SDK.  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 *Rect*  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das das Rechteck angibt, deren Größe die Grundleisten-Steuerelements geändert werden sollte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die diese Memberfunktion verwendet ein `CRect` Objekt als Parameter anstelle eines `RECT` Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


