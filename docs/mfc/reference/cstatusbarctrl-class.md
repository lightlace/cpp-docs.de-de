---
title: CStatusBarCtrl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
dev_langs:
- C++
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f34711389478997b3e2c43cb2d812b1b961df714
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375528"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Statusleisten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Erstellt ein `CStatusBarCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](#create)|Erstellt ein Statusleisten-Steuerelement, und fügt es einer `CStatusBarCtrl` Objekt.|  
|[CStatusBarCtrl::CreateEx](#createex)|Erstellt ein Statusleisten-Steuerelement mit der angegebenen erweiterten Fensterstile und fügt es einer `CStatusBarCtrl` Objekt.|  
|[CStatusBarCtrl::DrawItem](#drawitem)|Wird aufgerufen, wenn sich ein Darstellungsaspekt eines ein ownerdrawn-Statusleisten-Steuerelements ändert.|  
|[CStatusBarCtrl::GetBorders](#getborders)|Ruft die aktuelle Breite der horizontalen und vertikalen Rahmen ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl::GetIcon](#geticon)|Ruft das Symbol für einen Teil (auch bekannt als Bereich) in das aktuelle StatusBar-Steuerelement ab.|  
|[CStatusBarCtrl::GetParts](#getparts)|Ruft die Anzahl der Teile in ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck eines Teils in ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl:: GetText](#gettext)|Ruft den Text aus den angegebenen Teil ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl:: getTextLength](#gettextlength)|Rufen Sie die Länge in Zeichen, der den Text aus den angegebenen Teil ein Statusleisten-Steuerelement.|  
|[CStatusBarCtrl::GetTipText](#gettiptext)|Ruft den QuickInfo-Text für einen Bereich in einer Statusleiste ab.|  
|[CStatusBarCtrl::IsSimple](#issimple)|Überprüft einen Status Window-Steuerelement, um festzustellen, ob es sich im einfachen Modus befindet.|  
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Legt die Farbe des Hintergrunds in einer Statusleiste fest.|  
|[CStatusBarCtrl::SetIcon](#seticon)|Legt das Symbol für einen Bereich in einer Statusleiste fest.|  
|[CStatusBarCtrl::SetMinHeight](#setminheight)|Legt die minimale Höhe des Status Strich Zeichnungsbereich des Steuerelements fest.|  
|[CStatusBarCtrl::SetParts](#setparts)|Legt die Anzahl der Teile in einer Statusleisten-Steuerelement und dem rechten Rand der einzelnen Teile der Koordinate.|  
|[CStatusBarCtrl::SetSimple](#setsimple)|Gibt an, ob ein Statusleisten-Steuerelement zeigt die einfachen Text an oder alle Steuerelementteile, die durch einen vorherigen Aufruf festlegen zeigt `SetParts`.|  
|[CStatusBarCtrl::SetText](#settext)|Legt den Text im bestimmten Teil eines Statusleisten-Steuerelements fest.|  
|[CStatusBarCtrl:: setTipText](#settiptext)|Legt den QuickInfo-Text für einen Bereich in einer Statusleiste fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Statusleisten-Steuerelement" ist eine horizontale Fenster angezeigt, in der Regel am unteren Rand einer übergeordneten Fenster, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann. Das StatusBar-Steuerelement kann in Webparts zum Anzeigen von mehr als eine Art von Informationen unterteilt werden.  
  
 Dieses Steuerelement (und somit die `CStatusBarCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Weitere Informationen zur Verwendung von `CStatusBarCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="create"></a>  CStatusBarCtrl::Create  
 Erstellt ein Statusleisten-Steuerelement, und fügt es einer `CStatusBarCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das StatusBar-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen aufgeführt, die der Statusleiste [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) im Windows SDK. Dieser Parameter muss umfassen die **WS_CHILD** Stil. Darüber hinaus sollte enthalten die **WS_VISIBLE** Stil.  
  
 `rect`  
 Gibt an, Größe und Position des Statusleisten-Steuerelement. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt an, der Statusleiste des Steuerelements übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL.**  
  
 `nID`  
 Gibt das StatusBar-Steuerelement ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CStatusBarCtrl` in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie anschließend **erstellen**, die das StatusBar-Steuerelement erstellt, und fügt es der `CStatusBarCtrl` Objekt.  
  
 Die Standardposition eines Status-Fensters am unteren Rand des übergeordneten Fensters ist, aber Sie können angeben, die `CCS_TOP` Stil, damit diese am oberen Rand der Clientbereich des übergeordneten Fensters angezeigt. Sie können angeben, die **SBARS_SIZEGRIP** Formatvorlage einen Größenziehpunkt am rechten Ende Statusfenster enthalten. Kombiniert die `CCS_TOP` und **SBARS_SIZEGRIP** Formatvorlagen wird nicht empfohlen, da der resultierende Größenziehpunkt nicht funktionsfähig ist, obwohl das System im Statusfenster zeichnet.  
  
 Rufen Sie zum Erstellen einer Statusleiste mit erweiterten Fensterstile [CStatusBarCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CStatusBarCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CStatusBarCtrl` Objekt.  
  
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
 Gibt das StatusBar-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen aufgeführt, die der Statusleiste [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) im Windows SDK. Dieser Parameter muss umfassen die **WS_CHILD** Stil. Darüber hinaus sollte enthalten die **WS_VISIBLE** Stil.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="cstatusbarctrl"></a>  CStatusBarCtrl::CStatusBarCtrl  
 Erstellt ein `CStatusBarCtrl`-Objekt.  
  
```  
CStatusBarCtrl();
```  
  
##  <a name="drawitem"></a>  CStatusBarCtrl::DrawItem  
 Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines ein ownerdrawn-Statusleisten-Steuerelements ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Eine long-Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) -Struktur, die Informationen über den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein Ownerdrawn- `CStatusBarCtrl` Objekt.  
  
 Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
##  <a name="getborders"></a>  CStatusBarCtrl::GetBorders  
 Ruft das StatusBar-Steuerelement der aktuellen Breite der horizontalen und vertikalen Rahmen und der Abstand zwischen den Rechtecken ab.  
  
```  
BOOL GetBorders(int* pBorders) const;  
  
BOOL GetBorders(
    int& nHorz,  
    int& nVert,  
    int& nSpacing) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pBorders*  
 Die Adresse eines Arrays von Ganzzahlen mit drei Elementen. Das erste Element empfängt die Breite des horizontalen Rands, die zweite empfängt die Breite des vertikalen Rands und das dritte empfängt die Breite des Rahmens zwischen Rechtecken.  
  
 *nHorz*  
 Verweis auf eine ganze Zahl, die die Breite des horizontalen Rands empfängt.  
  
 *Umwandeln*  
 Verweis auf eine ganze Zahl, die die Breite des vertikalen Rands empfängt.  
  
 *nSpacing*  
 Verweis auf eine ganze Zahl, die die Breite des Rahmens zwischen Rechtecken empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Rahmen bestimmen den Abstand zwischen den äußeren Rand des Steuerelements und der Rechtecke innerhalb des Steuerelements, die Text enthalten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]  
  
##  <a name="geticon"></a>  CStatusBarCtrl::GetIcon  
 Ruft das Symbol für einen Teil (auch bekannt als Bereich) in das aktuelle StatusBar-Steuerelement ab.  
  
```  
HICON GetIcon(int iPart) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iPart`|Der nullbasierte Index des Teils, der das Symbol "abgerufen werden sollen. Ist dieser Parameter 1, wird davon ausgegangen, dass die Statusleiste einen einfachen Modus Statusleiste werden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Symbol "Wenn die Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SB_GETICON](http://msdn.microsoft.com/library/windows/desktop/bb760744) Nachricht, die im Windows SDK beschrieben wird.  
  
 Ein StatusBar-Steuerelement besteht aus einer Zeile von Textausgabebereichen, auch bekannt als Teile sind. Weitere Informationen zu der Statusleiste, finden Sie unter [Status Befehlsleisten-Standardimplementierung in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [Festlegen des CStatusBarCtrl-Objekts](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert eine Variable `m_statusBar`, d. h. verwendet, um das aktuelle StatusBar-Steuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden ein Symbol in zwei Bereiche des die aktuelle Statusleisten-Steuerelements kopiert. In einem früheren Abschnitt des Codebeispiels wir ein Statusleisten-Steuerelement mit drei Bereiche erstellt und dann ein Symbol in den ersten Bereich hinzugefügt. In diesem Beispiel ruft das Symbol ab, aus dem ersten Bereich und anschließend die zweite und dritte Bereich hinzugefügt.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]  
  
##  <a name="getparts"></a>  CStatusBarCtrl::GetParts  
 Ruft die Anzahl der Teile in ein Statusleisten-Steuerelement ab.  
  
```  
int GetParts(
    int nParts,  
    int* pParts) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nParts`  
 Die Anzahl der Teile, für die Koordinaten abzurufen. Wenn dieser Parameter größer als die Anzahl der Teile in das Steuerelement ist, ruft die Nachricht für vorhandene Teile nur Koordinaten ab.  
  
 *pParts*  
 Die Adresse eines Arrays von Ganzzahlen müssen die gleiche Anzahl von Elementen als die Anzahl der Teile, die vom angegebenen `nParts`. Jedes Element im Array empfängt der Clientkoordinate des rechten Rands des entsprechenden Teils. Wenn ein Element festgelegt ist – erweitert 1, die Position des rechten Rands für den jeweiligen Teil an den rechten Rand der Statusleiste an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Teile in das Steuerelement, wenn erfolgreich, oder andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ruft auch die Koordinate für den rechten Rand die angegebene Anzahl von Teilen ab.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]  
  
##  <a name="getrect"></a>  CStatusBarCtrl::GetRect  
 Ruft das umschließende Rechteck eines Teils in ein Statusleisten-Steuerelement ab.  
  
```  
BOOL GetRect(
    int nPane,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Nullbasierte Index des Teils, deren umschließendes Rechteck ist, abgerufen werden sollen.  
  
 `lpRect`  
 Adresse der einen [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das umschließende Rechteck empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]  
  
##  <a name="gettext"></a>  CStatusBarCtrl:: GetText  
 Ruft den Text aus den angegebenen Teil ein Statusleisten-Steuerelement ab.  
  
```  
CString GetText(
    int nPane,  
    int* pType = NULL) const;  
  
int GetText(
    LPCTSTR lpszText,  
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Die Adresse des Puffers, in den Text geschrieben. Dieser Parameter ist eine Null-terminierte Zeichenfolge.  
  
 `nPane`  
 Nullbasierte Index des Teils aus dem Text abzurufen.  
  
 `pType`  
 Ein Zeiger auf eine ganze Zahl, die die Typinformationen empfängt. Der Typ kann einen der folgenden Werte sein:  
  
- **0** der Text gezeichnet wird, mit einem Rahmen, die niedriger ist als die Ebene der Statusleiste angezeigt werden.  
  
- `SBT_NOBORDERS` Der Text wird ohne Rahmen gezeichnet.  
  
- `SBT_POPOUT` Der Text gezeichnet wird mit einem Rahmen höher als die Ebene der Statusleiste angezeigt werden.  
  
- `SBT_OWNERDRAW` Wenn der Text der `SBT_OWNERDRAW` Zeichnungstyp, `pType` empfängt diese Nachricht und gibt den 32-Bit-Wert, der den Text anstelle des Länge "und" Vorgang "zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge in Zeichen des Texts oder ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) mit dem aktuellen Text.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]  
  
##  <a name="gettextlength"></a>  CStatusBarCtrl:: getTextLength  
 Ruft die Länge in Zeichen, der den Text aus den angegebenen Teil ein Statusleisten-Steuerelement ab.  
  
```  
int GetTextLength(
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Nullbasierte Index des Teils aus dem Text abzurufen.  
  
 `pType`  
 Ein Zeiger auf eine ganze Zahl, die die Typinformationen empfängt. Der Typ kann einen der folgenden Werte sein:  
  
- **0** der Text gezeichnet wird, mit einem Rahmen, die niedriger ist als die Ebene der Statusleiste angezeigt werden.  
  
- `SBT_NOBORDERS` Der Text wird ohne Rahmen gezeichnet.  
  
- `SBT_OWNERDRAW` Der Text gezeichnet wird durch das übergeordnete Fenster.  
  
- `SBT_POPOUT` Der Text gezeichnet wird mit einem Rahmen höher als die Ebene der Statusleiste angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge in Zeichen des Texts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]  
  
##  <a name="gettiptext"></a>  CStatusBarCtrl::GetTipText  
 Ruft den QuickInfo-Text für einen Bereich in einer Statusleiste ab.  
  
```  
CString GetTipText(int nPane) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Der nullbasierte Index des Status-Leistenbereich den QuickInfo-Text zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit dem Text in der QuickInfo verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_GETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760751)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]  
  
##  <a name="issimple"></a>  CStatusBarCtrl::IsSimple  
 Überprüft einen Status Window-Steuerelement, um festzustellen, ob es sich im einfachen Modus befindet.  
  
```  
BOOL IsSimple() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Status Window-Steuerelement im einfachen Modus ist; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_ISSIMPLE](http://msdn.microsoft.com/library/windows/desktop/bb760753)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="setbkcolor"></a>  CStatusBarCtrl::SetBkColor  
 Legt die Farbe des Hintergrunds in einer Statusleiste fest.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Parameter  
 `cr`  
 **COLORREF** Wert, der die neue Hintergrundfarbe angibt. Geben Sie die `CLR_DEFAULT` Wert, der dazu führen, dass die Statusleiste die Standardhintergrundfarbe verwenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die vorherige Standardhintergrundfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760754)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]  
  
##  <a name="seticon"></a>  CStatusBarCtrl::SetIcon  
 Legt das Symbol für einen Bereich in einer Statusleiste fest.  
  
```  
BOOL SetIcon(
    int nPane,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Der nullbasierte Index des Bereichs, die das Symbol "erhalten. Wenn dieser Parameter-1 ist, wird davon ausgegangen, dass die Statusleiste eine einfache Statusleiste werden.  
  
 `hIcon`  
 Handle für das Symbol "festgelegt werden. Wenn dieser Wert ist **NULL**, das Symbol wird über das Webpart entfernt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETICON](http://msdn.microsoft.com/library/windows/desktop/bb760755)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CStatusBarCtrl::SetBkColor](#setbkcolor).  
  
##  <a name="setminheight"></a>  CStatusBarCtrl::SetMinHeight  
 Legt die minimale Höhe des Status Strich Zeichnungsbereich des Steuerelements fest.  
  
```  
void SetMinHeight(int nMin);
```  
  
### <a name="parameters"></a>Parameter  
 `nMin`  
 Mindesthöhe des Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Die minimale Höhe ist die Summe der `nMin` und zweimal die Breite des vertikalen Rands des Statusleisten-Steuerelement in Pixel.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]  
  
##  <a name="setparts"></a>  CStatusBarCtrl::SetParts  
 Legt die Anzahl der Teile in einer Statusleisten-Steuerelement und dem rechten Rand der einzelnen Teile der Koordinate.  
  
```  
BOOL SetParts(
    int nParts,  
    int* pWidths);
```  
  
### <a name="parameters"></a>Parameter  
 `nParts`  
 Die Anzahl von Teilen zu festgelegt. Die Anzahl der Teile darf nicht größer als 255 sein.  
  
 *pWidths*  
 Die Adresse eines Arrays von Ganzzahlen müssen die gleiche Anzahl von Elementen als Teile gemäß `nParts`. Jedes Element im Array gibt die Position des rechten Rands des entsprechenden Teils in Clientkoordinaten. Wenn ein Element - 1, erweitert die Position des rechten Rands für diesen Teil an den rechten Rand des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]  
  
##  <a name="setsimple"></a>  CStatusBarCtrl::SetSimple  
 Gibt an, ob ein Statusleisten-Steuerelement zeigt die einfachen Text an oder alle Steuerelementteile, die durch einen vorherigen Aufruf festlegen zeigt [Sie SetParts](#setparts).  
  
```  
BOOL SetSimple(BOOL bSimple = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSimple`  
 Anzeigetyp Flag. Wenn dieser Parameter ist `TRUE`, das Steuerelement zeigt einfachen Text an, wenn es ist `FALSE`, es werden mehrere Teile angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung das StatusBar-Steuerelement von nicht einfacher in einfache oder umgekehrt wechselt, zeichnet das System sofort das Steuerelement neu.  
  
##  <a name="settext"></a>  CStatusBarCtrl::SetText  
 Legt den Text im bestimmten Teil eines Statusleisten-Steuerelements fest.  
  
```  
BOOL SetText(
    LPCTSTR lpszText,  
    int nPane,  
    int nType);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Adresse einer mit NULL endenden Zeichenfolge, die den festzulegenden Text angibt. Wenn `nType` `SBT_OWNERDRAW` ist, stellt `lpszText` 32 Bit Daten dar.  
  
 `nPane`  
 Der nullbasierte Index des festzulegenden Teils. Wenn dieser Wert 255 ist, wird angenommen, dass das Statusleisten-Steuerelement ein einfaches Steuerelement mit nur einem Teil ist.  
  
 `nType`  
 Der Typ des Zeichenvorgangs. Finden Sie unter [SB_SETTEXT Meldung](http://msdn.microsoft.com/library/bb760758\(vs.85\).aspx) eine Liste der möglichen Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Meldung erklärt den geänderten Teil des Steuerelements für ungültig und veranlasst so, das beim nächsten Auftreten der `WM_PAINT`Meldung im Steuerelement der neue Text angezeigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]  
  
##  <a name="settiptext"></a>  CStatusBarCtrl:: setTipText  
 Legt den QuickInfo-Text für einen Bereich in einer Statusleiste fest.  
  
```  
void SetTipText(
    int nPane,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Der nullbasierte Index des Status-Leistenbereich den QuickInfo-Text zu erhalten.  
  
 *pszTipText*  
 Ein Zeiger auf eine Zeichenfolge, die den QuickInfo-Text enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760759)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl-Klasse](../../mfc/reference/ctoolbarctrl-class.md)
