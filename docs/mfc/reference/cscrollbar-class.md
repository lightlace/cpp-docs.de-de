---
title: CScrollBar Klasse | Microsoft Docs
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
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d458fe5f7bcaf25fc5bb0685bb382a72d44d183
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cscrollbar-class"></a>CScrollBar-Klasse
Stellt die Funktionalität eines Windows-Bildlaufleisten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CScrollBar : public CWnd  
```  
  
## <a name="members"></a>Member  
  
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
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Ruft den Grenzwert der scrollleiste ab|  
|[CScrollBar::GetScrollPos](#getscrollpos)|Ruft die aktuelle Position eines Scrollfelds ab.|  
|[CScrollBar::GetScrollRange](#getscrollrange)|Ruft die aktuellen minimalen und maximalen Bildlaufleisten-Positionen für die angegebene Bildlaufleiste ab.|  
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Legt die Informationen über die Bildlaufleiste fest.|  
|[CScrollBar::SetScrollPos](#setscrollpos)|Legt die aktuelle Position eines scrollfelds fest.|  
|[CScrollBar::SetScrollRange](#setscrollrange)|Legt die minimalen und maximalen Positionswerte für die angegebene Scrollleiste fest.|  
|[CScrollBar::ShowScrollBar](#showscrollbar)|Anzeigen oder ausblenden eine Bildlaufleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Sie erstellen ein Bildlaufleisten-Steuerelement in zwei Schritten. Rufen Sie zunächst den Konstruktor `CScrollBar` zum Erstellen der `CScrollBar` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion versucht, erstellen das Windows-Bildlaufleisten-Steuerelement, und fügen Sie es auf die `CScrollBar` Objekt.  
  
 Bei Erstellung einer `CScrollBar` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CScrollBar` wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CScrollBar` Objekt innerhalb eines Fensters müssen Sie möglicherweise auch sie zerstört werden.  
  
 Bei Erstellung der `CScrollBar` Objekt im Stapel befindet, automatisch zerstört wird. Bei Erstellung der `CScrollBar` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das sie zerstört werden, wenn der Benutzer die Bildlaufleiste Windows beendet.  
  
 Wenn Sie alle in Speicher der `CScrollBar` Objekt außer Kraft, indem die `CScrollBar` Destruktor, der die Zuordnungen zu verwerfen.  
  
 Weitere Informationen zur Verwendung von `CScrollBar`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Gibt den Bildlauf Standardstil der Statusleiste des. Wenden Sie eine beliebige Kombination von [Stile des Schiebeleisten Steuerelements](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) auf der Bildlaufleiste angezeigt.  
  
 `rect`  
 Gibt die Bildlaufleiste Größe und Position. Kann es sich um eine `RECT` Struktur oder ein `CRect` Objekt.  
  
 `pParentWnd`  
 Gibt den Bildlauf des übergeordneten Fensters, in der Regel eine `CDialog` Objekt. Es muss nicht **NULL**.  
  
 `nID`  
 Das Scroll Bar-Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CScrollBar` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor erstellt die `CScrollBar` Objekt; rufen dann **erstellen**, das erstellt und initialisiert das zugeordnete Windows-Bildlaufleiste und fügt es der `CScrollBar` Objekt.  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf eine Bildlaufleiste angezeigt:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]  
  
##  <a name="cscrollbar"></a>CScrollBar::CScrollBar  
 Erstellt ein `CScrollBar`-Objekt.  
  
```  
CScrollBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nach dem Erstellen des Objekts, das **erstellen** Memberfunktion zu erstellen und initialisieren Sie die Windows-Bildlaufleiste.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]  
  
##  <a name="enablescrollbar"></a>CScrollBar::EnableScrollBar  
 Aktiviert oder deaktiviert einen oder beide Pfeile auf einer Scrollleiste.  
  
```  
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>Parameter  
 `nArrowFlags`  
 Gibt an, ob der Bildlaufpfeile auf aktiviert oder deaktiviert sind und welche Pfeile aktiviert oder deaktiviert sind. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **ESB_ENABLE_BOTH** können beide Bildlaufpfeile einer Bildlaufleiste.  
  
- **ESB_DISABLE_LTUP** deaktiviert, die nach-links-Taste, der eine horizontale Bildlaufleiste angezeigt oder den Pfeil nach oben, der eine vertikale Bildlaufleiste angezeigt.  
  
- **ESB_DISABLE_RTDN** deaktiviert den Pfeil nach rechts von einer horizontalen Bildlaufleiste oder den Pfeil nach unten, der eine vertikale Bildlaufleiste angezeigt.  
  
- **ESB_DISABLE_BOTH** deaktiviert beide Bildlaufpfeile einer Bildlaufleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Pfeile aktiviert oder werden, wie angegeben deaktiviert werden; andernfalls-0 und bedeutet, dass die Pfeile bereits in der angeforderte Status oder ein Fehler aufgetreten ist.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="getscrollbarinfo"></a>CScrollBar::GetScrollBarInfo  
 Ruft die Informationen ab, die die **SCROLLBARINFO** Struktur über eine scrollleiste verwaltet.  
  
```  
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pScrollInfo*  
 Ein Zeiger auf die [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [SBM_SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787545) Nachricht, wie im Windows SDK beschrieben.  
  
##  <a name="getscrollinfo"></a>CScrollBar::GetScrollInfo  
 Ruft die Informationen ab, die von der `SCROLLINFO`-Struktur über eine Scrollleiste verwaltet werden.  
  
```  
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpScrollInfo`  
 Ein Zeiger auf eine [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur. Finden Sie in das Windows SDK für Weitere Informationen zu dieser Struktur.  
  
 `nMask`  
 Gibt die Scroll Bar-Parameter abgerufen. Typischer Verwendung, SIF_ALL, gibt eine Kombination von SIF_PAGE, SIF_POS SIF_TRACKPOS und SIF_RANGE an. Finden Sie unter `SCROLLINFO` für Weitere Informationen zu den nMask-Werten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Nachricht keine Werte abgerufen werden, ist die Rückgabe **"true"**. Andernfalls ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 `GetScrollInfo`ermöglicht es Anwendungen, 32-Bit-Bildlaufpositionen.  
  
 Die [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur enthält Informationen über eine Bildlaufleiste, einschließlich die Mindest- und Höchstwerte Durchführen eines Bildlaufs Positionen, die Seitengröße und die Position des Bildlauffelds (Ziehpunkt). Finden Sie unter der `SCROLLINFO` Struktur Thema in das Windows SDK für Weitere Informationen zum Ändern der Struktur Standardwerte.  
  
 Die MFC-Windows-Meldung Handler, die an der Position Bildlaufleiste, [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) und [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), nur 16 Bits der Positionsdaten bereitstellen. `GetScrollInfo`und `SetScrollInfo` 32 Bits der Bildlaufleiste an Positionsdaten bereitstellen. Daher kann eine Anwendung aufrufen `GetScrollInfo` bei der Verarbeitung entweder `CWnd::OnHScroll` oder `CWnd::OnVScroll` um 32-Bit-Scroll-Leiste Positionsdaten abzurufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrolllimit"></a>CScrollBar::GetScrollLimit  
 Ruft die maximale Bildlauf Position der Bildlaufleiste ab.  
  
```  
int GetScrollLimit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die maximale Position eine Bildlaufleiste angezeigt, wenn erfolgreich; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollpos"></a>CScrollBar::GetScrollPos  
 Ruft die aktuelle Position eines Scrollfelds ab.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Position des Bildlauffelds bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die aktuelle Position ist ein relativer Wert, der von der aktuellen fortlaufenden Bereich abhängig ist. Wenn das Durchführen eines Bildlaufs Bereich liegt zwischen 100 und 200, und das Bildlauffeld mitten in der Leiste ist, wird die aktuelle Position 150.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollrange"></a>CScrollBar::GetScrollRange  
 Kopiert die aktuellen minimalen und maximalen Bildlaufleisten-Positionen für die angegebene scrollleiste an den Speicherorten von angegebenen `lpMinPos` und `lpMaxPos`.  
  
```  
void GetScrollRange(
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpMinPos`  
 Verweist auf die ganzzahlige Variable, die die minimale Position zu empfangen.  
  
 `lpMaxPos`  
 Verweist auf die ganzzahlige Variable, die die maximale Position zu empfangen.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardbereich für ein Bildlaufleisten-Steuerelement ist leer (beide Werte sind 0).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="setscrollinfo"></a>CScrollBar::SetScrollInfo  
 Legt der Informationen, die die `SCROLLINFO` Struktur über eine scrollleiste verwaltet.  
  
```  
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpScrollInfo`  
 Ein Zeiger auf eine [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden soll, entsprechend den neuen Informationen. Wenn `bRedraw` ist **"true"**, die Bildlaufleiste neu gezeichnet wird. Ist er **"false"**, ihn nicht neu gezeichnet wird. Standardmäßig aktualisiert der Bildlaufleiste angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei einer erfolgreichen Rückgabe **"true"**. Andernfalls ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen die erforderlichen Werte angeben der `SCROLLINFO` Parameter, einschließlich der Flagwerte-Struktur.  
  
 Die `SCROLLINFO` Struktur enthält Informationen über eine Bildlaufleiste, einschließlich die Mindest- und Höchstwerte Durchführen eines Bildlaufs Positionen, die Seitengröße und die Position des Bildlauffelds (Ziehpunkt). Finden Sie unter der [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur Thema in das Windows SDK für Weitere Informationen zum Ändern der Struktur Standardwerte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]  
  
##  <a name="setscrollpos"></a>CScrollBar::SetScrollPos  
 Legt die aktuelle Position eines scrollfelds auf, die durch `nPos` und, falls angegeben, zeichnet die Bildlaufleiste, um die neue Position zu berücksichtigen.  
  
```  
int SetScrollPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt die neue Position für das Bildlauffeld. Es muss sich innerhalb des Bereichs Durchführen eines Bildlaufs.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden soll, entsprechend die neue Position. Wenn `bRedraw` ist **"true"**, die Bildlaufleiste neu gezeichnet wird. Ist er **"false"**, ihn nicht neu gezeichnet wird. Standardmäßig aktualisiert der Bildlaufleiste angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vorherige Position des Bildlauffelds bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie `bRedraw` auf **"false"** immer die Bildlaufleiste wird neu gezeichnet werden über einen nachfolgenden Aufruf an eine andere Funktion zu vermeiden, dass die Bildlaufleiste zweimal innerhalb eines kurzen Zeitraums neu gezeichnet.  
  
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
 Gibt die minimale Bildlauf Position an.  
  
 `nMaxPos`  
 Gibt die maximale Bildlauf Position.  
  
 `bRedraw`  
 Gibt an, ob die Bildlaufleiste neu gezeichnet werden sollte, um die Änderung zu übernehmen. Wenn `bRedraw` ist **"true"**, die Bildlaufleiste aktualisiert wird; Wenn **"false"**, ihn nicht neu gezeichnet wird. Es wird standardmäßig neu gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie `nMinPos` und `nMaxPos` auf 0, um die standard-Bildlaufleisten ausblenden.  
  
 Rufen Sie diese Funktion, um eine Bildlaufleiste bei der Verarbeitung einer Bildlaufleiste – Meldung ausblenden nicht.  
  
 Wenn ein Aufruf von `SetScrollRange` unmittelbar folgt einen Aufruf der `SetScrollPos` Memberfunktion festgelegt `bRedraw` in `SetScrollPos` auf 0, um zu verhindern, dass die Bildlaufleiste zweimal neu gezeichnet wird.  
  
 Der Unterschied zwischen die angegebenen Werte von `nMinPos` und `nMaxPos` darf nicht größer als 32.767 sein. Der Standardbereich für ein Bildlaufleisten-Steuerelement ist leer (beide `nMinPos` und `nMaxPos` sind 0).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]  
  
##  <a name="showscrollbar"></a>CScrollBar::ShowScrollBar  
 Anzeigen oder ausblenden eine Bildlaufleiste.  
  
```  
void ShowScrollBar(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob die Bildlaufleiste angezeigt oder ausgeblendet wird. Wenn dieser Parameter ist **"true"**, die Bildlaufleiste angezeigt wird; andernfalls wird es ausgeblendet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung sollte nicht mit dieser Funktion können Sie eine Bildlaufleiste ausblenden beim Verarbeiten einer Benachrichtigung Bildlaufleisten-aufrufen.  
  
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
