---
title: CStatusBarCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CStatusBarCtrl
- CStatusBarCtrl class
- status bar controls
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
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
ms.openlocfilehash: 619fb88b96f60ab2dc0911cb8ea0b66574ea4287
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Statusleisten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|Erstellt ein `CStatusBarCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](#create)|Erstellt ein Statusleisten-Steuerelement und fügt es ein `CStatusBarCtrl` Objekt.|  
|[CStatusBarCtrl::CreateEx](#createex)|Erstellt ein Statusleisten-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CStatusBarCtrl` Objekt.|  
|[CStatusBarCtrl::DrawItem](#drawitem)|Wird aufgerufen, wenn sich ein Darstellungsaspekt eines ownerdrawn Statusleisten-Steuerelement ändert.|  
|[CStatusBarCtrl::GetBorders](#getborders)|Ruft die aktuelle Breite der horizontalen und vertikalen Rahmen ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl::GetIcon](#geticon)|Ruft das Symbol für einen Teil (auch bekannt als Bereich) in der aktuellen Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl::GetParts](#getparts)|Ruft die Anzahl der Teile in ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl::GetRect](#getrect)|Ruft das umschließende Rechteck eines Teils in ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl::GetText](#gettext)|Ruft den Text aus dem angegebenen Teil ein Statusleisten-Steuerelement ab.|  
|[CStatusBarCtrl::GetTextLength](#gettextlength)|Rufen Sie die Länge in Zeichen des Texts aus dem angegebenen Teil ein Statusleisten-Steuerelement.|  
|[CStatusBarCtrl::GetTipText](#gettiptext)|Ruft den QuickInfo-Text für einen Bereich in einer Statusleiste angezeigt.|  
|[CStatusBarCtrl::IsSimple](#issimple)|Überprüft, ob es im einfachen Modus ist ein Fenster-Steuerelement.|  
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|Legt die Farbe des Hintergrunds in einer Statusleiste angezeigt.|  
|[CStatusBarCtrl::SetIcon](#seticon)|Legt das Symbol für einen Bereich in einer Statusleiste angezeigt.|  
|[CStatusBarCtrl::SetMinHeight](#setminheight)|Legt die minimale Höhe des Status Leiste Zeichnungsbereich des Steuerelements fest.|  
|[CStatusBarCtrl::SetParts](#setparts)|Legt die Anzahl der Teile im Statusleiste-Steuerelement und die Koordinaten des rechten Rands der einzelnen Teile.|  
|[CStatusBarCtrl::SetSimple](#setsimple)|Gibt an, ob ein Statusleisten-Steuerelement zeigt die einfachen Text an oder alle Steuerelementteile festlegen, indem Sie einen vorherigen Aufruf von zeigt `SetParts`.|  
|[CStatusBarCtrl::SetText](#settext)|Legt den Text im bestimmten Teil eines Statusleisten-Steuerelements fest.|  
|[CStatusBarCtrl:: setTipText](#settiptext)|Legt den QuickInfo-Text für einen Bereich in einer Statusleiste angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Statusleisten-Steuerelement" ist ein horizontales Fenster angezeigt, in der Regel am unteren Rand eines übergeordneten Fensters, in dem eine Anwendung verschiedene Arten von Statusinformationen anzeigen kann. Das StatusBar-Steuerelement kann auf mehrere Arten von Informationen anzuzeigen unterteilt werden.  
  
 Dieses Steuerelement (und somit die `CStatusBarCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen zur Verwendung von `CStatusBarCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-namecreatea--cstatusbarctrlcreate"></a><a name="create"></a>CStatusBarCtrl::Create  
 Erstellt ein Statusleisten-Steuerelement und fügt es ein `CStatusBarCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das StatusBar-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen aufgeführt, die der Statusleiste [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dieser Parameter muss enthalten der **WS_CHILD** Stil. Darüber hinaus sollte enthalten die **WS_VISIBLE** Stil.  
  
 `rect`  
 Gibt des StatusBar-Steuerelements die Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt die Statusleiste übergeordnete Fenster des Steuerelements, normalerweise eine `CDialog`. Er darf nicht sein **NULL.**  
  
 `nID`  
 Gibt das StatusBar-Steuerelement ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie eine `CStatusBarCtrl` in zwei Schritten. Zuerst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die das Statusleiste-Steuerelement erstellt, und fügt es der `CStatusBarCtrl` Objekt.  
  
 Die Standardposition eines Fensters Status am unteren Rand des übergeordneten Fensters ist, aber Sie können angeben, die `CCS_TOP` Stil so, dass sie am Anfang der Clientbereich des übergeordneten Fensters angezeigt werden. Sie können angeben, die **SBARS_SIZEGRIP** Formatvorlage einen Größenziehpunkt am rechten Ende Fenster enthalten. Kombinieren der `CCS_TOP` und **SBARS_SIZEGRIP** Formatvorlagen wird nicht empfohlen, da der resultierende Größenziehpunkt nicht funktionsfähig ist, obwohl das System im Statusfenster zeichnet.  
  
 Rufen Sie zum Erstellen einer Statusleiste mit erweiterten Fensterstile [CStatusBarCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#1;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]  
  
##  <a name="a-namecreateexa--cstatusbarctrlcreateex"></a><a name="createex"></a>CStatusBarCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CStatusBarCtrl` Objekt.  
  
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
 Gibt das StatusBar-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen aufgeführt, die der Statusleiste [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dieser Parameter muss enthalten der **WS_CHILD** Stil. Darüber hinaus sollte enthalten die **WS_VISIBLE** Stil.  
  
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
  
##  <a name="a-namecstatusbarctrla--cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a>CStatusBarCtrl::CStatusBarCtrl  
 Erstellt ein `CStatusBarCtrl`-Objekt.  
  
```  
CStatusBarCtrl();
```  
  
##  <a name="a-namedrawitema--cstatusbarctrldrawitem"></a><a name="drawitem"></a>CStatusBarCtrl::DrawItem  
 Aufgerufen, wenn sich ein Darstellungsaspekt eines ownerdrawn Statusleisten-Steuerelement ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein long-Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) -Struktur, die Informationen über den Typ der erforderlichen Zeichnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CStatusBarCtrl` Objekt.  
  
 Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
##  <a name="a-namegetbordersa--cstatusbarctrlgetborders"></a><a name="getborders"></a>CStatusBarCtrl::GetBorders  
 Ruft das Statusleiste-Steuerelement der aktuellen Breite der horizontalen und vertikalen Rahmen und den Abstand zwischen den Rechtecken ab.  
  
```  
BOOL GetBorders(int* pBorders) const;  
  
BOOL GetBorders(
    int& nHorz,  
    int& nVert,  
    int& nSpacing) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pBorders*  
 Die Adresse eines Arrays von Ganzzahlen mit drei Elementen. Das erste Element empfängt die Breite des horizontalen Rands, die zweite erhält die Breite des vertikalen Rands und die dritte erhält die Breite des Rahmens zwischen den Rechtecken.  
  
 *nHorz*  
 Verweis auf eine ganze Zahl, die die Breite des horizontalen Rands empfängt.  
  
 *Umwandeln*  
 Verweis auf eine ganze Zahl, die die Breite des vertikalen Rands empfängt.  
  
 *nSpacing*  
 Verweis auf eine ganze Zahl, die die Breite des Rahmens zwischen Rechtecken empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Ränder bestimmen den Abstand zwischen dem äußeren Rand des Steuerelements und den Rechtecken innerhalb des Steuerelements, die Text enthalten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#2;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]  
  
##  <a name="a-namegeticona--cstatusbarctrlgeticon"></a><a name="geticon"></a>CStatusBarCtrl::GetIcon  
 Ruft das Symbol für einen Teil (auch bekannt als Bereich) in der aktuellen Statusleisten-Steuerelement ab.  
  
```  
HICON GetIcon(int iPart) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iPart`|Der nullbasierte Index des Teils mit den abgerufen werden sollen. Wenn dieser Parameter den Wert-1 hat, wird angenommen, dass die Statusleiste eine Statusleiste im einfachen Modus werden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Symbol "Wenn die Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [SB_GETICON](http://msdn.microsoft.com/library/windows/desktop/bb760744) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Ein Statusleisten-Steuerelement besteht aus einer Zeile von Textausgabebereichen, auch bekannt als Teile sind. Weitere Informationen über die Statusleiste finden Sie unter [Status Leiste Implementierung in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [Festlegen des Modus eines CStatusBarCtrl-Objekts](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_statusBar`, d. h. verwendet, um die aktuellen Statusleisten-Steuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden ein Symbol in zwei Bereiche des aktuellen Statusleisten-Steuerelements kopiert. In einem früheren Abschnitt des Codebeispiels müssen wir ein Statusleisten-Steuerelement mit drei Bereiche erstellt und dann ein Symbol in den ersten Bereich hinzugefügt. In diesem Beispiel ruft das Symbol aus dem ersten Bereich und dann im zweiten und dritten hinzugefügt.  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]  
  
##  <a name="a-namegetpartsa--cstatusbarctrlgetparts"></a><a name="getparts"></a>CStatusBarCtrl::GetParts  
 Ruft die Anzahl der Teile in ein Statusleisten-Steuerelement ab.  
  
```  
int GetParts(
    int nParts,  
    int* pParts) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nParts`  
 Anzahl der Teile für die Koordinaten abgerufen. Wenn dieser Parameter größer als die Anzahl der Teile in das Steuerelement ist, ruft die Nachricht Koordinaten für nur vorhandene Teile ab.  
  
 *pParts*  
 Ein Array von Ganzzahlen müssen die gleiche Anzahl von Elementen wie die Anzahl der Teile, die durch angegebene Adresse `nParts`. Jedes Element im Array empfängt der Clientkoordinate des rechten Rands des entsprechenden Teils. Wenn ein Element – festgelegt ist erweitert 1, die Position des rechten Rands für diesen Teil an den rechten Rand der Statusleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Teile in das Steuerelement im Erfolgsfall oder andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ruft auch die Koordinate für den rechten Rand die angegebene Anzahl von Teilen ab.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&3;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]  
  
##  <a name="a-namegetrecta--cstatusbarctrlgetrect"></a><a name="getrect"></a>CStatusBarCtrl::GetRect  
 Ruft das umschließende Rechteck eines Teils in ein Statusleisten-Steuerelement ab.  
  
```  
BOOL GetRect(
    int nPane,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Nullbasierte Index des Teils, dessen umschließendes Rechteck wird abgerufen werden sollen.  
  
 `lpRect`  
 Adresse einer [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das umschließende Rechteck empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&4;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]  
  
##  <a name="a-namegettexta--cstatusbarctrlgettext"></a><a name="gettext"></a>CStatusBarCtrl::GetText  
 Ruft den Text aus dem angegebenen Teil ein Statusleisten-Steuerelement ab.  
  
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
 Die Adresse des Puffers, die den Text empfängt. Dieser Parameter ist eine auf Null endende Zeichenfolge.  
  
 `nPane`  
 Nullbasierte Index des Teils aus dem Text abgerufen.  
  
 `pType`  
 Zeiger auf eine ganze Zahl, die die Typinformationen empfängt. Der Typ kann einen der folgenden Werte sein:  
  
- **0** der Text gezeichnet wird, mit einem Rahmen niedriger als die Ebene der Statusleiste angezeigt werden.  
  
- `SBT_NOBORDERS`Der Text wird ohne Rahmen gezeichnet.  
  
- `SBT_POPOUT`Der Text wird mit einem Rahmen höher als die Ebene der Statusleiste erscheinen gezeichnet.  
  
- `SBT_OWNERDRAW`Wenn der Text der `SBT_OWNERDRAW` Zeichnungstyp, `pType` empfängt diese Nachricht und gibt den 32-Bit-Wert, der den Text anstelle der Länge und den Vorgang zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge in Zeichen, die Text oder ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die den aktuellen Text enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&5;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]  
  
##  <a name="a-namegettextlengtha--cstatusbarctrlgettextlength"></a><a name="gettextlength"></a>CStatusBarCtrl::GetTextLength  
 Ruft die Länge in Zeichen des Texts aus dem angegebenen Teil ein Statusleisten-Steuerelement ab.  
  
```  
int GetTextLength(
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Nullbasierte Index des Teils aus dem Text abgerufen.  
  
 `pType`  
 Zeiger auf eine ganze Zahl, die die Typinformationen empfängt. Der Typ kann einen der folgenden Werte sein:  
  
- **0** der Text gezeichnet wird, mit einem Rahmen niedriger als die Ebene der Statusleiste angezeigt werden.  
  
- `SBT_NOBORDERS`Der Text wird ohne Rahmen gezeichnet.  
  
- `SBT_OWNERDRAW`Der Text wird vom übergeordneten Fenster gezeichnet.  
  
- `SBT_POPOUT`Der Text wird mit einem Rahmen höher als die Ebene der Statusleiste erscheinen gezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge in Zeichen des Texts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&6;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]  
  
##  <a name="a-namegettiptexta--cstatusbarctrlgettiptext"></a><a name="gettiptext"></a>CStatusBarCtrl::GetTipText  
 Ruft den QuickInfo-Text für einen Bereich in einer Statusleiste angezeigt.  
  
```  
CString GetTipText(int nPane) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Der nullbasierte Index des Status-Leistenbereich den QuickInfo-Text zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit dem Text, der in der QuickInfo verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_GETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760751), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#7;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]  
  
##  <a name="a-nameissimplea--cstatusbarctrlissimple"></a><a name="issimple"></a>CStatusBarCtrl::IsSimple  
 Überprüft, ob es im einfachen Modus ist ein Fenster-Steuerelement.  
  
```  
BOOL IsSimple() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Fenstersteuerelement Status im einfachen Modus ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_ISSIMPLE](http://msdn.microsoft.com/library/windows/desktop/bb760753), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbkcolora--cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a>CStatusBarCtrl::SetBkColor  
 Legt die Farbe des Hintergrunds in einer Statusleiste angezeigt.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Parameter  
 `cr`  
 **COLORREF** Wert, der die neue Hintergrundfarbe angibt. Geben Sie den `CLR_DEFAULT` -Wert an, damit die Statusleiste, verwenden Sie die Standard-Hintergrundfarbe.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Wert, der vorherigen Standard-Hintergrundfarbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760754), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#8;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]  
  
##  <a name="a-nameseticona--cstatusbarctrlseticon"></a><a name="seticon"></a>CStatusBarCtrl::SetIcon  
 Legt das Symbol für einen Bereich in einer Statusleiste angezeigt.  
  
```  
BOOL SetIcon(
    int nPane,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `nPane`  
 Der nullbasierte Index des Bereichs, der das Symbol erhält. Wenn dieser Parameter den Wert-1 hat, wird angenommen, dass die Statusleiste eine einfache Statusleiste werden.  
  
 `hIcon`  
 Handle für das Symbol festgelegt werden. Wenn dieser Wert **NULL**, das Symbol wird vom Teil entfernt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETICON](http://msdn.microsoft.com/library/windows/desktop/bb760755), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CStatusBarCtrl::SetBkColor](#setbkcolor).  
  
##  <a name="a-namesetminheighta--cstatusbarctrlsetminheight"></a><a name="setminheight"></a>CStatusBarCtrl::SetMinHeight  
 Legt die minimale Höhe des Status Leiste Zeichnungsbereich des Steuerelements fest.  
  
```  
void SetMinHeight(int nMin);
```  
  
### <a name="parameters"></a>Parameter  
 `nMin`  
 Minimale Höhe des Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Die minimale Höhe ist die Summe der `nMin` und zweimal die Breite des vertikalen Rands des Statusleisten-Steuerelements in Pixel.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#9;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]  
  
##  <a name="a-namesetpartsa--cstatusbarctrlsetparts"></a><a name="setparts"></a>CStatusBarCtrl::SetParts  
 Legt die Anzahl der Teile im Statusleiste-Steuerelement und die Koordinaten des rechten Rands der einzelnen Teile.  
  
```  
BOOL SetParts(
    int nParts,  
    int* pWidths);
```  
  
### <a name="parameters"></a>Parameter  
 `nParts`  
 Anzahl der Teile festlegen. Die Anzahl der Teile darf nicht größer als 255 sein.  
  
 *pWidths*  
 Ein Array von Ganzzahlen müssen die gleiche Anzahl von Elementen als Teile, die durch angegebene Adresse `nParts`. Jedes Element im Array gibt die Position des rechten Rands des entsprechenden Teils in Clientkoordinaten. Wenn ein Element – 1, erweitert die Position des rechten Rands für diesen Teil an den rechten Rand des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#10;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]  
  
##  <a name="a-namesetsimplea--cstatusbarctrlsetsimple"></a><a name="setsimple"></a>CStatusBarCtrl::SetSimple  
 Gibt an, ob ein Statusleisten-Steuerelement zeigt die einfachen Text an oder alle Steuerelementteile festlegen, indem Sie einen vorherigen Aufruf von zeigt [Sie SetParts](#setparts).  
  
```  
BOOL SetSimple(BOOL bSimple = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSimple`  
 Anzeigetyp Flag. Wenn dieser Parameter `TRUE`, das Steuerelement zeigt einfachen Text, wenn sie `FALSE`, mehrere Teile angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung das Statusleiste-Steuerelement aus nicht einfacher in einfache (oder umgekehrt) ändert, zeichnet das System sofort das Steuerelement neu.  
  
##  <a name="a-namesettexta--cstatusbarctrlsettext"></a><a name="settext"></a>CStatusBarCtrl::SetText  
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
 Der Typ des Zeichenvorgangs. Finden Sie unter [SB_SETTEXT Nachricht](http://msdn.microsoft.com/library/bb760758\(vs.85\).aspx) eine Liste der möglichen Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Die Meldung erklärt den geänderten Teil des Steuerelements für ungültig und veranlasst so, das beim nächsten Auftreten der `WM_PAINT`Meldung im Steuerelement der neue Text angezeigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#11;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]  
  
##  <a name="a-namesettiptexta--cstatusbarctrlsettiptext"></a><a name="settiptext"></a>CStatusBarCtrl:: setTipText  
 Legt den QuickInfo-Text für einen Bereich in einer Statusleiste angezeigt.  
  
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
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [SB_SETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760759), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CStatusBarCtrl&#12;](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl-Klasse](../../mfc/reference/ctoolbarctrl-class.md)

