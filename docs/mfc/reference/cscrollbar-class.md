---
title: Klasse CScrollBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
dev_langs:
- C++
helpviewer_keywords:
- CScrollBar class
- SCROLLBAR window class
- scroll bars
- Windows common controls [C++], CScrollBar
- controls [MFC], scroll bar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
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
ms.openlocfilehash: 84b59f041f1a6cf73843c303e1a6b71adffc2101
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cscrollbar-class"></a>CScrollBar-Klasse
Stellt die Funktionalität eines Windows-Bildlaufleisten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CScrollBar : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CScrollBar::CScrollBar](#cscrollbar)|Erstellt ein `CScrollBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CScrollBar::Create](#create)|Erstellt die Windows-Bildlaufleiste und fügt es der `CScrollBar` Objekt.|  
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Aktiviert oder deaktiviert einen oder beide Pfeile auf einer Scrollleiste.|  
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Ruft Informationen über die Bildlaufleiste mit einer `SCROLLBARINFO` Struktur.|  
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Ruft Informationen über die Bildlaufleiste ab.|  
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Ruft den Grenzwert der Bildlaufleiste|  
|[CScrollBar::GetScrollPos](#getscrollpos)|Ruft die aktuelle Position eines Scrollfelds ab.|  
|[CScrollBar::GetScrollRange](#getscrollrange)|Ruft die aktuellen Positionen der minimalen und maximalen Bildlaufleiste für die angegebene Bildlaufleiste ab.|  
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Legt die Informationen über die Bildlaufleiste fest.|  
|[CScrollBar::SetScrollPos](#setscrollpos)|Legt die aktuelle Position des Bildlauffelds fest.|  
|[CScrollBar::SetScrollRange](#setscrollrange)|Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.|  
|[CScrollBar::ShowScrollBar](#showscrollbar)|Anzeigen oder ausblenden eine Bildlaufleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Sie erstellen eine Bildlaufleisten-Steuerelements in zwei Schritten. Rufen Sie zunächst den Konstruktor `CScrollBar` zum Erstellen der `CScrollBar` -Objekt, und rufen Sie dann die [erstellen](#create) Member-Funktion zum Erstellen der Windows-Bildlaufleisten-Steuerelements, und fügen Sie es auf die `CScrollBar` Objekt.  
  
 Bei der Erstellung einer `CScrollBar` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CScrollBar` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CScrollBar` -Objekt innerhalb eines Fensters müssen Sie möglicherweise auch zerstört.  
  
 Bei der Erstellung der `CScrollBar` Objekt auf dem Stapel automatisch zerstört wird. Bei der Erstellung der `CScrollBar` Objekt auf dem Heap mithilfe der **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn der Benutzer die Bildlaufleiste von Windows beendet wird.  
  
 Wenn Sie alle in Speicher der `CScrollBar` Objekt, das Überschreiben der `CScrollBar` Destruktor, um die Zuordnung zu entfernen.  
  
 Weitere Informationen zur Verwendung von `CScrollBar`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="create"></a>CScrollBar::Create  
 Erstellt die Windows-Bildlaufleiste und fügt es der `CScrollBar` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Rollen des Balkens-Stil. Wenden Sie eine beliebige Kombination von [Bildlaufleisten-Stile](../../mfc/reference/scroll-bar-styles.md) auf die Bildlaufleiste.  
  
 `rect`  
 Gibt die Bildlaufleiste Größe und Position. Kann entweder ein `RECT` Struktur oder ein `CRect` Objekt.  
  
 `pParentWnd`  
 Gibt die Rollen des Balkens übergeordneten Fensters, in der Regel ein `CDialog` Objekt. Er darf nicht sein **NULL**.  
  
 `nID`  
 Die Bildlaufleiste-Steuerelement-ID auf.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CScrollBar` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, die erstellt, die `CScrollBar` Objekt, rufen Sie dann **erstellen**, die erstellt und initialisiert die zugeordnete Windows-Bildlaufleiste und fügt es der `CScrollBar` Objekt.  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) um eine Bildlaufleiste angezeigt:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar&#1;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]  
  
##  <a name="cscrollbar"></a>CScrollBar::CScrollBar  
 Erstellt ein `CScrollBar`-Objekt.  
  
```  
CScrollBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nach dem Erstellen des Objekts, das **erstellen** Member-Funktion erstellen und initialisieren die Bildlaufleiste von Windows.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar&#2;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]  
  
##  <a name="enablescrollbar"></a>CScrollBar::EnableScrollBar  
 Aktiviert oder deaktiviert einen oder beide Pfeile auf einer Scrollleiste.  
  
```  
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>Parameter  
 `nArrowFlags`  
 Gibt an, ob die Pfeile aktiviert oder deaktiviert sind, und die Pfeile aktiviert oder deaktiviert werden. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **ESB_ENABLE_BOTH** können beide Bildlaufpfeile einer Bildlaufleiste.  
  
- **ESB_DISABLE_LTUP** deaktiviert den Pfeil nach links von einer horizontalen Bildlaufleiste oder den Pfeil nach oben, der eine vertikale Bildlaufleiste angezeigt.  
  
- **ESB_DISABLE_RTDN** deaktiviert den Pfeil nach rechts von einer horizontalen Bildlaufleiste oder den Pfeil nach unten, der eine vertikale Bildlaufleiste angezeigt.  
  
- **ESB_DISABLE_BOTH** deaktiviert sowohl Bildlaufpfeile einer Bildlaufleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Pfeile aktiviert oder angegeben deaktiviert sind; andernfalls 0 gibt an, dass die Pfeile bereits in den angeforderten Zustand befinden oder ein Fehler aufgetreten ist.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="getscrollbarinfo"></a>CScrollBar::GetScrollBarInfo  
 Ruft die Informationen ab, die die **SCROLLBARINFO** Struktur verwaltet, über eine Bildlaufleiste angezeigt.  
  
```  
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pScrollInfo*  
 Ein Zeiger auf die [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [SBM_SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787545) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getscrollinfo"></a>CScrollBar::GetScrollInfo  
 Ruft die Informationen ab, die von der `SCROLLINFO`-Struktur über eine Scrollleiste verwaltet werden.  
  
```  
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpScrollInfo`  
 Ein Zeiger auf eine [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur. Finden Sie unter den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu dieser Struktur.  
  
 `nMask`  
 Gibt die Scroll-Leiste Parameter abgerufen. Normalerweise SIF_ALL, gibt eine Kombination von SIF_PAGE, SIF_POS, SIF_TRACKPOS und SIF_RANGE. Finden Sie unter `SCROLLINFO` für Weitere Informationen über die nMask-Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Nachricht keine Werte abgerufen werden, ist die Rückgabe **TRUE**. Andernfalls wird **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 `GetScrollInfo`ermöglicht Anwendungen die 32-Bit-Bildlaufpositionen verwenden.  
  
 Die [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur enthält Informationen über eine Bildlaufleiste, einschließlich die Mindest- und Höchstwerte Bildlauf Positionen, die Größe und die Position des Bildlauffeld (Ziehpunkt). Finden Sie unter der `SCROLLINFO` Struktur Thema in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zum Ändern der Struktur Standardwerte.  
  
 Die MFC-Windows-Meldung Handler, die an der Position Bildlaufleiste, [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), nur 16 Bits der Positionsdaten bereitzustellen. `GetScrollInfo`und `SetScrollInfo` 32 Bits der Bildlaufleiste Positionsdaten bereitzustellen. Daher kann eine Anwendung aufrufen `GetScrollInfo` beim Verarbeiten einer `CWnd::OnHScroll` oder `CWnd::OnVScroll` 32-Bit-Scroll-Leiste Positionsdaten abrufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrolllimit"></a>CScrollBar::GetScrollLimit  
 Ruft die maximale Bildlauf Position der Bildlaufleiste ab.  
  
```  
int GetScrollLimit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die maximale Position der Bildlaufleiste bei Erfolg an. andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollpos"></a>CScrollBar::GetScrollPos  
 Ruft die aktuelle Position eines Scrollfelds ab.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Position des Bildlauffelds bei Erfolg an. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die aktuelle Position ist ein relativer Wert, der von der aktuellen fortlaufenden Bereich abhängt. Wenn der fortlaufende Bereich liegt zwischen 100 und 200, und das Bildlauffeld in der Mitte der Leiste ist, wird die aktuelle Position 150.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollrange"></a>CScrollBar::GetScrollRange  
 Kopiert die aktuellen Positionen der minimalen und maximalen Bildlaufleiste für die angegebene Bildlaufleiste an den angegebenen Speicherorten `lpMinPos` und `lpMaxPos`.  
  
```  
void GetScrollRange(
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpMinPos`  
 Verweist auf die ganzzahlige Variable, die die minimale Position zu erhalten.  
  
 `lpMaxPos`  
 Verweist auf die ganzzahlige Variable, die die maximale Position zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardbereich für ein Bildlaufleisten-Steuerelements ist leer (beide Werte sind 0).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="setscrollinfo"></a>CScrollBar::SetScrollInfo  
 Legt der Informationen, die die `SCROLLINFO` Struktur verwaltet, über eine Bildlaufleiste angezeigt.  
  
```  
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpScrollInfo`  
 Ein Zeiger auf eine [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste auf der neuen Informationen neu gezeichnet werden sollte. Wenn `bRedraw` ist **TRUE**, die Bildlaufleiste neu gezeichnet wird. Ist dies **FALSE**, ihn nicht neu gezeichnet wird. Standardmäßig aktualisiert der Bildlaufleiste angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Rückgabe **TRUE**. Andernfalls wird **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie die erforderlichen Werte der `SCROLLINFO` Parameter, einschließlich der Flagwerte-Struktur.  
  
 Die `SCROLLINFO` Struktur enthält Informationen über eine Bildlaufleiste, einschließlich die Mindest- und Höchstwerte Bildlauf Positionen, die Größe und die Position des Bildlauffeld (Ziehpunkt). Finden Sie unter der [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur Thema in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zum Ändern der Struktur Standardwerte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar&3;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]  
  
##  <a name="setscrollpos"></a>CScrollBar::SetScrollPos  
 Legt die aktuelle Position des Bildlauffelds auf angegebenen `nPos` und, falls angegeben, zeichnet die Bildlaufleiste, um die neue Position wiederzugeben.  
  
```  
int SetScrollPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt die neue Position für das Bildlauffeld. Es muss innerhalb des Bereichs der Bildlaufleiste.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden sollte, an die neue Position wiederzugeben. Wenn `bRedraw` ist **TRUE**, die Bildlaufleiste neu gezeichnet wird. Ist dies **FALSE**, ihn nicht neu gezeichnet wird. Standardmäßig aktualisiert der Bildlaufleiste angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vorherige Position des Bildlauffelds bei Erfolg an. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie `bRedraw` auf **FALSE** jedes Mal, wenn die Bildlaufleiste wird neu gezeichnet werden durch einen nachfolgenden Aufruf an eine andere Funktion zu vermeiden, dass die Bildlaufleiste zweimal innerhalb kurzer Zeit neu gezeichnet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="setscrollrange"></a>CScrollBar::SetScrollRange  
 Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.  
  
```  
void SetScrollRange(
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nMinPos`  
 Gibt die minimale Bildlaufposition.  
  
 `nMaxPos`  
 Gibt die maximale Bildlaufposition.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden soll, entsprechend die Änderung. Wenn `bRedraw` ist **TRUE**, die Bildlaufleiste neu gezeichnet wird, wenn **FALSE**, ihn nicht neu gezeichnet wird. Es wird standardmäßig neu gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie `nMinPos` und `nMaxPos` auf 0, um die standard-Bildlaufleisten ausblenden.  
  
 Rufen Sie diese Funktion, um eine Bildlaufleiste auszublenden, während der Verarbeitung einer Bildlaufleiste Benachrichtigung.  
  
 Wenn ein Aufruf von `SetScrollRange` unmittelbar folgt einen Aufruf der `SetScrollPos` -Memberfunktion festgelegt `bRedraw` in `SetScrollPos` auf 0, um zu verhindern, dass die Bildlaufleiste zweimal neu gezeichnet wird.  
  
 Der Unterschied zwischen den Werten, die durch angegebene `nMinPos` und `nMaxPos` darf nicht größer sein als 32.767. Der Standardbereich für ein Bildlaufleisten-Steuerelements ist leer (beide `nMinPos` und `nMaxPos` sind 0).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar&4;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]  
  
##  <a name="showscrollbar"></a>CScrollBar::ShowScrollBar  
 Anzeigen oder ausblenden eine Bildlaufleiste.  
  
```  
void ShowScrollBar(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob die Bildlaufleiste angezeigt oder ausgeblendet wird. Wenn dieser Parameter **TRUE**, wird die Schiebeleiste angezeigt; andernfalls wird es ausgeblendet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung sollte diese Funktion, um eine Bildlaufleiste auszublenden, während der Verarbeitung einer Bildlaufleiste Benachrichtigung nicht aufrufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CScrollBar::Create](#create).  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [CStatic-Klasse](../../mfc/reference/cstatic-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)

