---
title: CReBarCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- rebar controls, control bar
- rebar controls, CReBarCtrl class
- CReBarCtrl class
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
caps.latest.revision: 23
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
ms.openlocfilehash: c1da4de2897c74e9cb25bc060033f4bd43159174
ms.lasthandoff: 02/24/2017

---
# <a name="crebarctrl-class"></a>CReBarCtrl-Klasse
Kapselt die Funktionalität eines Grundleisten-Steuerelements. Dabei handelt es sich um einen Container für ein untergeordnetes Fenster.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|Erstellt ein `CReBarCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Drag & Drop-Modus Grundleisten-Steuerelement eingefügt.|  
|[CReBarCtrl::Create](#create)|Erstellt das Grundleistensteuerelement und fügt es der `CReBarCtrl` Objekt.|  
|[CReBarCtrl::CreateEx](#createex)|Erstellt ein Grundleistensteuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CReBarCtrl` Objekt.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Löscht ein Band von einem Grundleisten-Steuerelement.|  
|[CReBarCtrl::DragMove](#dragmove)|Aktualisiert die Position ziehen Sie in der Grundleisten-Steuerelement nach dem Aufruf von `BeginDrag`.|  
|[CReBarCtrl::EndDrag](#enddrag)|Beendet die Grundleisten-Steuerelement Drag & Drop-Vorgang.|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|Ruft die Ränder eines Bandes ab.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Ruft die Anzahl der Bänder, die derzeit in der Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Ruft Informationen über ein angegebenes Band in einem Grundleisten-Steuerelement.|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|Ruft die Ränder eines Bandes ab.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Ruft die Höhe des Infoleiste-Steuerelements ab.|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Ruft Informationen über die Grundleisten-Steuerelement und die Liste der Images verwendet.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Ruft die Standardhintergrundfarbe für ein Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|Ruft die [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Struktur Grundleisten-Steuerelement zugeordnet ist.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Ruft ein Grundleistensteuerelement `IDropTarget` -Schnittstellenzeiger.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile des aktuellen Grundleisten-Steuerelements ab.|  
|[CReBarCtrl::GetImageList](#getimagelist)|Ruft die einem Grundleistensteuerelement zugeordnete Bildliste ab.|  
|[CReBarCtrl::GetPalette](#getpalette)|Ruft die aktuelle Palette Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck für eine angegebene Band in einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Ruft die Anzahl der Zeilen von Band in einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Ruft die Höhe einer angegebenen Zeile in einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Ruft die Standardtextfarbe einem Grundleisten-Steuerelement ab.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Ruft das Handle für eine beliebige Grundleisten-Steuerelement zugeordneten QuickInfo-Steuerelements ab.|  
|[CReBarCtrl::HitTest](#hittest)|Bestimmt, welcher Teil eines Infoleistenbandes ist an einem bestimmten Punkt auf dem Bildschirm angezeigt, wenn ein Infoleistenband an diesem Punkt vorhanden ist.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Konvertiert einen Band Bezeichner (ID) auf einem Band Index in einem Grundleisten-Steuerelement.|  
|[CReBarCtrl:: InsertBand](#insertband)|Fügt ein neues Band in einem Grundleisten-Steuerelement.|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|Ändert die Größe eines Bandes in einem Grundleisten-Steuerelement auf die maximale Größe.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|Ändert ein Band in einem Grundleisten-Steuerelement auf die kleinste Größe an.|  
|[CReBarCtrl::MoveBand](#moveband)|Verschiebt ein Band aus einem Index.|  
|[CReBarCtrl::PushChevron](#pushchevron)|Programmgesteuertes legt ein Chevron.|  
|[CReBarCtrl::RestoreBand](#restoreband)|Ein Band in einem Grundleisten-Steuerelement die ideale Größe die Größe ändert.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Legt die Eigenschaften einer vorhandenen Bereichsrand in einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|Legt die Breite des angegebenen angedockten Band in der aktuellen Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Legt die Eigenschaften eines Grundleisten-Steuerelements fest.|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Legt die Standardhintergrundfarbe einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Legt das Farbschema für die Schaltflächen in einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile für das aktuelle Grundleistensteuerelement fest.|  
|[CReBarCtrl::SetImageList](#setimagelist)|Legt die Bildliste einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetOwner](#setowner)|Legt ein Grundleistensteuerelement Besitzerfenster.|  
|[CReBarCtrl::SetPalette](#setpalette)|Legt die aktuelle Palette Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Legt die Standardtextfarbe einem Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Ordnet die Grundleisten-Steuerelement ein QuickInfo-Steuerelement hinzu.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Legt den visuellen Stil der Grundleisten-Steuerelement fest.|  
|[CReBarCtrl::ShowBand](#showband)|Anzeigen oder Ausblenden einer bestimmten Band in einem Grundleisten-Steuerelement.|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Entspricht einem Grundleisten-Steuerelement zu einem bestimmten Rechteck.|  
  
## <a name="remarks"></a>Hinweise  
 Die Anwendung, in der die Grundleisten-Steuerelement befindet, weist das untergeordnete Fenster Grundleisten-Steuerelement die Infoleiste Band enthalten sind. Das untergeordnete Fenster ist normalerweise eine andere Standardsteuerelements.  
  
 Rebar-Steuerelemente enthalten eine oder mehrere Bänder. Jedes Band kann eine Kombination aus einem Ziehleiste, eine Bitmap, eine Bezeichnung und ein untergeordnetes Fenster enthalten. Das Band kann nur jeweils eine dieser Elemente enthalten.  
  
 Grundleisten-Steuerelement kann über eine angegebene Hintergrundbitmap das untergeordnete Fenster angezeigt. Alle rebarbereichen Steuerelement geändert werden können, mit Ausnahme derjenigen, mit denen die **RBBS_FIXEDSIZE** Stil. Wie Sie Position und Größe ein Grundleisten-Steuerelementband ändern, verwaltet das Grundleistensteuerelement die Größe und Position des untergeordneten Fensters, das Band zugewiesen. Zum Ändern der Größe oder die Reihenfolge der Bänder innerhalb des Steuerelements ändern, klicken Sie auf, und ziehen Sie ein Band Ziehleiste.  
  
 Die folgende Abbildung zeigt ein Grundleistensteuerelement, das drei Bändern:  
  
-   Band 0 enthält einen flachen, transparenten Toolbar-Steuerelement.  
  
-   Band 1 enthält beide transparente standard und transparente Dropdown-Schaltflächen.  
  
-   Band 2 enthält ein Kombinationsfeld und vier Standardschaltflächen.  
  
     ![Beispiel eines grundleistenmenüs](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Grundleisten-Steuerelement  
 Grundleisten Sie-Steuerelemente unterstützen:  
  
-   Bildlisten.  
  
-   Handhabung von Nachrichten.  
  
-   Benutzerdefiniertes Zeichnen Funktionalität.  
  
-   Eine Vielzahl von Steuerelementtypen für die zusätzlich zum standardmäßigen Fensterstile. Eine Liste dieser Stile finden Sie unter [Grundleisten-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb774377) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="begindrag"></a>CReBarCtrl::BeginDrag  
 Implementiert das Verhalten der Win32-Nachricht [RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands, die der Drag & Drop-Vorgang auswirkt.  
  
 `dwPos`  
 Ein `DWORD` Wert, der die ersten Koordinaten enthält. Die horizontale Koordinate in der LOWORD enthalten ist, und die vertikale Koordinate in die HIWORD enthalten ist. Wenn Sie übergeben `(DWORD)-1`, Grundleisten-Steuerelement verwendet die Position der Maus bei der letzten-Thread des Steuerelements aufgerufen **GetMessage** oder **PeekMessage**.  
  
##  <a name="create"></a>CReBarCtrl::Create  
 Erstellt das Grundleistensteuerelement und fügt es der `CReBarCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Kombination der Grundleisten-Steuerelementstile auf das Steuerelement angewendet. Finden Sie unter [Grundleisten-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb774377) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste der unterstützten Formate.  
  
 `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die Position und Größe des Infoleiste-Steuerelements ist.  
  
 `pParentWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Infoleiste-Steuerelements ist. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt die Grundleisten-Steuerelement-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen eines Grundleisten-Steuerelements in zwei Schritten:  
  
1.  Rufen Sie [CReBarCtrl](#crebarctrl) zum Erstellen einer `CReBarCtrl` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die Windows-Grundleisten-Steuerelement erstellt, und fügt es der `CReBarCtrl` Objekt.  
  
 Beim Aufruf von **erstellen**, werden die allgemeinen Steuerelemente initialisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&3;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>CReBarCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CReBarCtrl` Objekt.  
  
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
 Gibt die Kombination der Grundleisten-Steuerelementstile auf das Steuerelement angewendet. Eine Liste der unterstützten Formate finden Sie unter [Grundleisten-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb774377) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
##  <a name="crebarctrl"></a>CReBarCtrl::CReBarCtrl  
 Erstellt ein `CReBarCtrl`-Objekt.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CReBarCtrl::Create](#create).  
  
##  <a name="deleteband"></a>CReBarCtrl::DeleteBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands gelöscht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Band wurde erfolgreich gelöscht; andernfalls&0; (null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&4;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="dragmove"></a>CReBarCtrl::DragMove  
 Implementiert das Verhalten der Win32-Nachricht [RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>Parameter  
 `dwPos`  
 Ein `DWORD` Wert, der die neuen Koordinaten enthält. Die horizontale Koordinate in der LOWORD enthalten ist, und die vertikale Koordinate in die HIWORD enthalten ist. Wenn Sie übergeben `(DWORD)-1`, Grundleisten-Steuerelement verwendet die Position der Maus bei der letzten-Thread des Steuerelements aufgerufen **GetMessage** oder **PeekMessage**.  
  
##  <a name="enddrag"></a>CReBarCtrl::EndDrag  
 Implementiert das Verhalten der Win32-Nachricht [RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void EndDrag();
```  
  
##  <a name="getbandborders"></a>CReBarCtrl::GetBandBorders  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands für die Rahmen abgerufen werden sollen.  
  
 `prc`  
 Ein Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Rahmenlinien Band erhalten. Wenn das Grundleistensteuerelement verfügt die **RBS_BANDBORDERS** Stil, jedes Mitglied dieser Struktur erhalten die Anzahl der Pixel an, auf der entsprechenden Seite des Bands, die den Rahmen darstellen. Grundleisten-Steuerelement keinen der **RBS_BANDBORDERS** formatieren, nur das linke Element dieser Struktur gültige Informationen erhält. Eine Beschreibung der Steuerelementtypen Rebar, finden Sie unter [Steuerelementtypen für die Infoleiste](http://msdn.microsoft.com/library/windows/desktop/bb774377) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbandcount"></a>CReBarCtrl::GetBandCount  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bänder, die dem Steuerelement zugewiesen werden soll.  
  
##  <a name="getbandinfo"></a>CReBarCtrl::GetBandInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands für die die Informationen abgerufen werden sollen.  
  
 `prbbi`  
 Ein Zeiger auf eine [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur-Band-Informationen. Müssen Sie festlegen, die `cbSize` Member dieser Struktur zu `sizeof(REBARBANDINFO)` und legen Sie die **fMask** Member auf die Elemente, die Sie vor dem Senden dieser Nachricht abrufen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="getbandmargins"></a>CReBarCtrl::GetBandMargins  
 Ruft die Ränder des Bands.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>Parameter  
 *pMargins*  
 Ein Zeiger auf eine [RÄNDER](http://msdn.microsoft.com/library/windows/desktop/bb773244)-Struktur, die die Informationen zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbarheight"></a>CReBarCtrl::GetBarHeight  
 Ruft die Höhe des Balkens Infoleiste ab.  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert, der die Höhe des Steuerelements in Pixel darstellt.  
  
##  <a name="getbarinfo"></a>CReBarCtrl::GetBarInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `prbi`  
 Ein Zeiger auf eine [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) -Struktur, die die Infoleiste Informationen erhält. Sie müssen festlegen, die `cbSize` Member dieser Struktur zu `sizeof(REBARINFO)` vor dem Senden dieser Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="getbkcolor"></a>CReBarCtrl::GetBkColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die aktuelle Standard-Hintergrundfarbe.  
  
##  <a name="getcolorscheme"></a>CReBarCtrl::GetColorScheme  
 Ruft die [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Struktur für das Grundleistensteuerelement.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcs`  
 Ein Zeiger auf eine [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Struktur, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Die **COLORSCHEME** Struktur enthält, die Farbe der Schaltfläche Hervorhebung und die Schaltflächenfarbe.  
  
##  <a name="getdroptarget"></a>CReBarCtrl::GetDropTarget  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Schnittstelle.  
  
##  <a name="getextendedstyle"></a>CReBarCtrl::GetExtendedStyle  
 Ruft die erweiterten Stile des aktuellen Grundleisten-Steuerelements ab.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination (OR) von Flags, die die erweiterten Stile angeben. Die möglichen Flags sind `RBS_EX_SPLITTER` und `RBS_EX_TRANSPARENT`. Weitere Informationen finden Sie unter der `dwMask` Parameter von der [CReBarCtrl::SetExtendedStyle](#setextendedstyle) Methode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getimagelist"></a>CReBarCtrl::GetImageList  
 Ruft die `CImageList` Objekt, das mit einem Grundleisten-Steuerelement zugeordnet.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt. Gibt **NULL** Wenn keine Bildliste für das Steuerelement festgelegt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verwendet, Größe und Maske Informationen in der [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) Struktur, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getpalette"></a>CReBarCtrl::GetPalette  
 Ruft die aktuelle Palette Grundleisten-Steuerelement ab.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md) -Objekt, das die Grundleisten-Steuerelement aktuelle Palette angibt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die diese Memberfunktion verwendet ein `CPalette` Objekt als Rückgabewert, anstelle einer `HPALETTE`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&5;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="getrect"></a>CReBarCtrl::GetRect  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des ein Band in der Grundleisten-Steuerelement.  
  
 `prc`  
 Ein Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Grenzen des Bands Infoleiste erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&6;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="getrowcount"></a>CReBarCtrl::GetRowCount  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **UINT** Wert, der die Anzahl der Zeilen von Band im Steuerelement darstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#7;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="getrowheight"></a>CReBarCtrl::GetRowHeight  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *uRow*  
 Nullbasierte Index des Bands, die die Höhe abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **UINT** Wert, der die Höhe der Zeilen in Pixel darstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#8;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="gettextcolor"></a>CReBarCtrl::GetTextColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** -Wert, der die aktuellen Standardtextfarbe darstellen.  
  
##  <a name="gettooltips"></a>CReBarCtrl::GetToolTips  
 Implementiert das Verhalten der Win32-Nachricht [RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die MFC-Implementierung von `GetToolTips` gibt einen Zeiger auf eine `CToolTipCtrl`, anstelle einer `HWND`.  
  
##  <a name="hittest"></a>CReBarCtrl::HitTest  
 Implementiert das Verhalten der Win32-Nachricht [RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>Parameter  
 *prbht*  
 Ein Zeiger auf eine [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391) Struktur. Vor dem Senden der Nachricht die **pt** Member dieser Struktur muss initialisiert werden, zu dem Punkt, die getestet werden, in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Bands am angegebenen Punkt oder -1, wenn kein Infoleistenband am Punkt wurde.  
  
##  <a name="idtoindex"></a>CReBarCtrl::IDToIndex  
 Implementiert das Verhalten der Win32-Nachricht [RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *uBandID*  
 Der anwendungsspezifische Bezeichner des angegebenen Bands, übergeben die **wID** Mitglied der [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur, wenn das Band eingelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Band Index im Erfolgsfall oder andernfalls -1. Wenn doppelte Band Indizes vorhanden sind, ist das erste Objekt zurückgegeben.  
  
##  <a name="insertband"></a>CReBarCtrl:: InsertBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Parameter  
 *uIndex*  
 Nullbasierte Index der Position, an der das Band eingefügt wird. Wenn Sie diesen Parameter auf-1 festlegen, wird das Steuerelement an der letzten Position das neue Band hinzufügen.  
  
 `prbbi`  
 Ein Zeiger auf eine [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur, definiert das Band aus, das eingefügt werden soll. Sie müssen festlegen, die `cbSize` Member dieser Struktur zu `sizeof(REBARBANDINFO)` vor dem Aufruf dieser Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#9;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="maximizeband"></a>CReBarCtrl::MaximizeBand  
 Ändert die Größe eines Bandes in einem Grundleisten-Steuerelement auf die maximale Größe.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands, maximiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) mit `fIdeal` auf 0 festgelegt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#10;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="minimizeband"></a>CReBarCtrl::MinimizeBand  
 Ändert ein Band in einem Grundleisten-Steuerelement auf die kleinste Größe an.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands auf ein Minimum reduziert werden.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert das Verhalten der Win32-Nachricht [RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#11;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="moveband"></a>CReBarCtrl::MoveBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>Parameter  
 *uFrom*  
 Nullbasierte Index des Bands verschoben werden soll.  
  
 *utomatisch*  
 Nullbasierte Index der Position des neuen Band. Dieser Parameterwert muss nie größer als die Anzahl der Bänder minus&1; sein. Rufen Sie zum Abrufen der Anzahl der Bänder [GetBandCount](#getbandcount).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="pushchevron"></a>CReBarCtrl::PushChevron  
 Implementiert das Verhalten der Win32-Nachricht [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands, deren Chevron wird verschoben werden.  
  
 `lAppValue`  
 Eine Anwendung definiert die 32-Bit-Wert. Finden Sie unter `lAppValue` in [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="restoreband"></a>CReBarCtrl::RestoreBand  
 Ein Band in einem Grundleisten-Steuerelement die ideale Größe die Größe ändert.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands, maximiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Implementiert das Verhalten der Win32-Nachricht [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) mit `fIdeal` auf 1 festgelegt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#12;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="setbandinfo"></a>CReBarCtrl::SetBandInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des Bands an den neuen Einstellungen zu erhalten.  
  
 `prbbi`  
 Zeiger auf eine [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Struktur, definiert das Band aus, das eingefügt werden soll. Sie müssen festlegen, die `cbSize` Member dieser Struktur zu `sizeof(REBARBANDINFO)` vor dem Senden dieser Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&#13;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="setbandwidth"></a>CReBarCtrl::SetBandWidth  
 Legt die Breite des angegebenen angedockten Band in der aktuellen Grundleisten-Steuerelement fest.  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `uBand`|Nullbasierten Index eines Infoleistenbandes.|  
|[in] `cxWidth`|Die neue Breite des Infoleistenbandes in Pixel.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_rebar`, d. h. auf das aktuelle Grundleistensteuerelement verwendet. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird jedes Infoleistenband die gleiche Breite.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="setbarinfo"></a>CReBarCtrl::SetBarInfo  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>Parameter  
 `prbi`  
 Ein Zeiger auf eine [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) Struktur mit den Informationen festgelegt werden. Sie müssen festlegen, die `cbSize` Member dieser Struktur zu `sizeof(REBARINFO)` vor dem Senden dieser Nachricht  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CReBarCtrl&14;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="setbkcolor"></a>CReBarCtrl::SetBkColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Die **COLORREF** Wert, der die neue Standard-Hintergrundfarbe darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Wert, der vorherigen Standard-Hintergrundfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie diese Weitere Informationen darüber, wann die Hintergrundfarbe festlegen und wie der Standardwert festgelegt.  
  
##  <a name="setcolorscheme"></a>CReBarCtrl::SetColorScheme  
 Legt das Farbschema für die Schaltflächen in einem Grundleisten-Steuerelement fest.  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcs`  
 Ein Zeiger auf eine [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Struktur, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Die **COLORSCHEME** Struktur enthält, die Farbe der Schaltfläche Hervorhebung und die Schaltflächenfarbe.  
  
##  <a name="setextendedstyle"></a>CReBarCtrl::SetExtendedStyle  
 Legt die erweiterten Stile für das aktuelle Grundleistensteuerelement fest.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwMask`|Eine bitweise Kombination (OR) von Flags, die angeben, welche Attribute in der `dwStyleEx` Parameter angewendet. Verwenden Sie eine oder mehrere der folgenden Werte:<br /><br /> RBS_EX_SPLITTER: Standardmäßig an den Splitter am unteren in horizontale Modus, und klicken Sie auf der rechten Seite in vertikaler Modus.<br /><br /> RBS_EX_TRANSPARENT: Weiterleiten der [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) Nachricht an das übergeordnete Fenster.|  
|[in] `dwStyleEx`|Eine bitweise Kombination (OR) von Flags, die die anzuwendenden Formate angeben. Um ein Format festzulegen, geben Sie das gleiche Flag, das verwendet wird der `dwMask` Parameter. Um einen Stil zurückzusetzen, geben Sie binäre&0; (null).|  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige erweiterten Stil.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setimagelist"></a>CReBarCtrl::SetImageList  
 Weist eine Bildliste einem Grundleisten-Steuerelement.  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, enthält die Bildliste Grundleisten-Steuerelement zugewiesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="setowner"></a>CReBarCtrl::SetOwner  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf ein `CWnd` Objekt, das als Besitzer des Grundleisten-Steuerelement festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das der aktuelle Besitzer des Infoleiste-Steuerelements ist.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Memberfunktion Zeiger auf `CWnd` Objekte für den aktuellen und dem ausgewählten Besitzer des Infoleiste-Steuerelements statt Windows behandelt.  
  
> [!NOTE]
>  Diese Memberfunktion ändert nicht das tatsächliche übergeordnete Element, das festgelegt wurde, wenn das Steuerelement erstellt wurde. Stattdessen sendet sie Benachrichtigungen zu dem Fenster, das Sie angeben.  
  
##  <a name="setpalette"></a>CReBarCtrl::SetPalette  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>Parameter  
 *hPal*  
 Ein `HPALETTE` , angibt, dass die neue Palette, die die Grundleisten-Steuerelement verwenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md) -Objekt, das vorherige Palette Grundleisten-Steuerelement angibt.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die diese Memberfunktion verwendet ein `CPalette` Objekt als Rückgabewert, anstelle einer `HPALETTE`.  
  
##  <a name="settextcolor"></a>CReBarCtrl::SetTextColor  
 Implementiert das Verhalten der Win32-Nachricht [RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Ein **COLORREF** -Wert, der den neuen Text Farbe in der `CReBarCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) zugeordnete Wert, der die vorherige Textfarbe darstellt der `CReBarCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Es wird zur Unterstützung von Text Farbe Flexibilität in einem Grundleisten-Steuerelement bereitgestellt.  
  
##  <a name="settooltips"></a>CReBarCtrl::SetToolTips  
 Ordnet ein QuickInfo-Steuerelement mit einem Grundleisten-Steuerelement.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>Parameter  
 *pToolTip*  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Zerstören der `CToolTipCtrl` Objekt, wenn Sie damit fertig sind.  
  
##  <a name="setwindowtheme"></a>CReBarCtrl::SetWindowTheme  
 Legt den visuellen Stil der Grundleisten-Steuerelement fest.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parameter  
 `pszSubAppName`  
 Ein Zeiger auf eine Unicode-Zeichenfolge mit den visuellen Stil der Infoleiste festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="showband"></a>CReBarCtrl::ShowBand  
 Implementiert das Verhalten der Win32-Nachricht [RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `uBand`  
 Nullbasierte Index des ein Band in der Grundleisten-Steuerelement.  
  
 *fShow*  
 Gibt an, ob das Band ein- oder ausgeblendet werden soll. Wenn dieser Wert **TRUE**, das Band wird angezeigt. Andernfalls wird das Band ausgeblendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
##  <a name="sizetorect"></a>CReBarCtrl::SizeToRect  
 Implementiert das Verhalten der Win32-Nachricht [RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das Rechteck angibt, die das Grundleistensteuerelement festgelegt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die diese Memberfunktion verwendet ein `CRect` Objekt als Parameter anstelle eines `RECT` Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



