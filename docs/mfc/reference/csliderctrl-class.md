---
title: CSliderCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6bd20852f1dfd278d4ae58cc6c67d6047579cd08
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693191"
---
# <a name="csliderctrl-class"></a>CSliderCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Schieberegler-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Erstellt ein `CSliderCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|Löscht die aktuelle Auswahl in einem Schieberegler-Steuerelement.|  
|[CSliderCtrl::ClearTics](#cleartics)|Entfernt die aktuelle Teilstriche aus einem Schieberegler-Steuerelement.|  
|[CSliderCtrl::Create](#create)|Erstellt ein Schieberegler-Steuerelement, und fügt sie an einer `CSliderCtrl` Objekt.|  
|[CSliderCtrl::CreateEx](#createex)|Erstellt ein Schieberegler-Steuerelement mit dem angegebenen erweiterten Stile für Windows und fügt sie an einer `CSliderCtrl` Objekt.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Ruft das Handle für ein Schieberegler-Steuerelement Buddy-Fenster an einer bestimmten Position ab.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Ruft die Größe des Schieberegler-Steuerelements Kanal ab.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Ruft die Zeilengröße eines Schieberegler-Steuerelements ab.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Ruft die Anzahl von Teilstrichen in einem Schieberegler-Steuerelement.|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Ruft die Seitengröße des Schieberegler-Steuerelement ab.|  
|[CSliderCtrl::GetPos](#getpos)|Ruft die aktuelle Position des Schiebereglers ab.|  
|[CSliderCtrl::GetRange](#getrange)|Ruft den minimalen und maximalen Positionen für einen Schieberegler ab.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Ruft die maximale Position für einen Schieberegler ab.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Ruft die minimale Position für einen Schieberegler ab.|  
|[CSliderCtrl::GetSelection](#getselection)|Ruft den Bereich der aktuellen Auswahl ab.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Ruft die Länge der Schieberegler in der aktuellen Trackbar-Steuerelement ab.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Ruft die Größe des Schieberegler-Steuerelements Thumb-Steuerelement ab.|  
|[CSliderCtrl::GetTic](#gettic)|Ruft die Position des angegebenen Teilstrichs ab.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Ruft das Array von Tick Mark Positionen für ein Schieberegler-Steuerelement ab.|  
|[CSliderCtrl::GetTicPos](#getticpos)|Ruft die Position des angegebenen Teilstrichs, in Clientkoordinaten ab.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Ruft das Handle für das QuickInfo-Steuerelement, das Schieberegler-Steuerelement zugewiesen, sofern vorhanden.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Wird in einem Fenster als das Buddyfenster für ein Schieberegler-Steuerelement.|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Legt die Zeilengröße eines Schieberegler-Steuerelements fest.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Legt die Seitengröße des Schieberegler-Steuerelement fest.|  
|[CSliderCtrl::SetPos](#setpos)|Legt die aktuelle Position des Schiebereglers fest.|  
|[CSliderCtrl::SetRange](#setrange)|Legt die minimalen und maximalen Positionen für einen Schieberegler fest.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Legt die maximale Position für einen Schieberegler fest.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Legt die minimale Position für einen Schieberegler fest.|  
|[CSliderCtrl::SetSelection](#setselection)|Legt den Bereich der aktuellen Auswahl fest.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Legt die Länge des Schiebereglers in das aktuelle Trackbar-Steuerelement fest.|  
|[CSliderCtrl::SetTic](#settic)|Legt die Position des angegebenen Teilstrichs fest.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Legt die Häufigkeit der Teilstriche markiert pro Erhöhung der Schieberegler-Steuerelement fest.|  
|[CSliderCtrl::SetTipSide](#settipside)|Positionen verwendet ein QuickInfo-Steuerelement von einem Trackbar-Steuerelement.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Ein Schieberegler-Steuerelement wird ein QuickInfo-Steuerelement zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Schieberegler-Steuerelement"(auch bekannt als Trackleiste) ist ein Fenster mit einem Schieberegler und optionale Teilstriche. Wenn der Benutzer den Schieberegler, mit der Maus oder die Schlüssel für die Richtung, sendet das Steuerelement Benachrichtigungen, um die Änderung anzuzeigen.  
  
 Schieberegler-Steuerelemente sind nützlich, wenn Sie möchten, dass den Benutzer einen diskreten Wert oder einen Satz von aufeinander folgenden Werten in einem Bereich auswählen. Beispielsweise können Sie ein Schieberegler-Steuerelement verwenden, damit der Benutzer die Wiederholrate der Tastatur mithilfe des Schiebereglers und eines bestimmten Teilstrichs festlegen kann.  
  
 Dieses Steuerelement (und somit die `CSliderCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Verschieben des Schiebereglers, in Schritten, die Sie angeben, bei der Erstellung. Z. B. Wenn Sie angeben, dass der Schieberegler auf einen Bereich von fünf haben soll, der Schieberegler kann nur sechs Positionen einnehmen: eine Position auf der linken Seite das Schieberegler-Steuerelement und eine Position für jeden Schritt im Bereich. In der Regel wird jeder dieser Positionen durch ein Teilstrich identifiziert.  
  
 Sie erstellen einen Schieberegler mit dem Konstruktor und die `Create` Memberfunktion `CSliderCtrl`. Nachdem Sie ein Schieberegler-Steuerelement erstellt haben, können Sie Memberfunktionen in `CSliderCtrl` um viele der Eigenschaften zu ändern. Änderungen, die Sie vornehmen können, enthalten die minimalen und maximalen Positionen für den Schieberegler festlegen, Teilstriche zu zeichnen, einen Auswahlbereich festlegen und Neupositionieren von den Schieberegler.  
  
 Weitere Informationen zur Verwendung von `CSliderCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="clearsel"></a>  CSliderCtrl::ClearSel  
 Löscht die aktuelle Auswahl in einem Schieberegler-Steuerelement.  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *bRedraw*  
 Flag neu gezeichnet werden. Wenn dieser Parameter TRUE ist, wird der Schieberegler neu gezeichnet werden, nach dem Löschen der Auswahl; Andernfalls wird der Schieberegler nicht neu gezeichnet.  
  
##  <a name="cleartics"></a>  CSliderCtrl::ClearTics  
 Entfernt die aktuelle Teilstriche aus einem Schieberegler-Steuerelement.  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *bRedraw*  
 Flag neu gezeichnet werden. Wenn dieser Parameter TRUE ist, der Schieberegler neu gezeichnet wird, nachdem die Teilstriche gelöscht werden; Andernfalls wird der Schieberegler nicht neu gezeichnet.  
  
##  <a name="create"></a>  CSliderCtrl::Create  
 Erstellt ein Schieberegler-Steuerelement, und fügt sie an einer `CSliderCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *dwStyle*  
 Gibt das Schieberegler-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Stile der Schieberegler-Steuerelemente](/windows/desktop/Controls/trackbar-control-styles), in der Windows-SDK verwenden, um das Steuerelement beschrieben.  
  
 *Rect*  
 Gibt an, Größe und Position des Schieberegler-Steuerelements. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 *pParentWnd*  
 Gibt an, das Schieberegler-Steuerelement übergeordnete Fenster, in der Regel eine `CDialog`. Es darf nicht NULL sein.  
  
 *nID*  
 Gibt das Schieberegler-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CSliderCtrl` in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann `Create`, die das Schieberegler-Steuerelement erstellt, und fügt es der `CSliderCtrl` Objekt.  
  
 Abhängig von den Werten, legen Sie für *DwStyle*, das Schieberegler-Steuerelement haben entweder vertikal oder horizontal ausgerichtet. Er kann die Teilstriche auf einer Seite, besitzen sowohl Seiten oder keines von beiden. Sie können auch verwendet werden, um einen Bereich aufeinander folgender Werte anzugeben.  
  
 Rufen Sie zum Anwenden von erweiterten Fensterstile auf das Schieberegler-Steuerelement [CreateEx](#createex) anstelle von `Create`.  
  
##  <a name="createex"></a>  CSliderCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet ihn dem `CSliderCtrl` Objekt.  
  
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
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Windows-Stile, finden Sie unter den *DwExStyle* -Parameter für [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) im Windows SDK.  
  
 *dwStyle*  
 Gibt das Schieberegler-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Stile der Schieberegler-Steuerelemente](/windows/desktop/Controls/trackbar-control-styles), in der Windows-SDK verwenden, um das Steuerelement beschrieben.  
  
 *Rect*  
 Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.  
  
 *pParentWnd*  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 *nID*  
 Der ID des Steuerelements untergeordneten Fensters mit.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.  
  
##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl  
 Erstellt ein `CSliderCtrl`-Objekt.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy  
 Ruft das Handle für ein Schieberegler-Steuerelement Buddy-Fenster an einer bestimmten Position ab.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *fLocation*  
 Ein boolescher Wert, welcher der beiden Buddy-Fensterhandles abrufen soll. Kann einer der folgenden Werte sein:  
  
- "True" Ruft das Handle für den Kontakt auf der linken Seite des Schiebereglers ab. Wenn das Schieberegler-Steuerelement den TBS_VERT-Stil verwendet, wird die Nachricht die Buddy oberhalb des Schiebereglers abzurufen.  
  
- "False" Ruft das Handle für das Buddy rechts neben dem Schieberegler ab. Wenn das Schieberegler-Steuerelement den TBS_VERT-Stil verwendet, wird die Nachricht die Buddy unten den Schieberegler abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das Buddyfenster an die vom angegebenen Speicherort ist *fLocation*, oder NULL, wenn kein Buddyfenster an diesem Speicherort vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_GETBUDDY](/windows/desktop/Controls/tbm-getbuddy), wie im Windows SDK beschrieben. Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Stile von Listensteuerelementen Trackbar](/windows/desktop/Controls/trackbar-control-styles) im Windows SDK.  
  
##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect  
 Ruft ab, die Größe und Position des umschließenden Rechtecks für ein Schieberegler-Steuerelement-Kanal.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lprc*  
 Ein Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Größe und Position des Kanals enthält umschließenden Rechtecks bei Rückgabe der Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Der Kanal ist der Bereich über das Verschieben des Schiebereglers, und die Hervorhebung enthält, wenn ein Bereich markiert ist.  
  
##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize  
 Ruft die Größe der Zeile für ein Schieberegler-Steuerelement ab.  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe einer Zeile für das Schieberegler-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeilengröße beeinflusst, wie viel der Schieberegler für die Benachrichtigungen TB_LINEUP und TB_LINEDOWN verschoben wird. Die Standardeinstellung für die Zeilengröße ist 1.  
  
##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics  
 Ruft die Anzahl von Teilstrichen in einem Schieberegler-Steuerelement.  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Teilstriche im Schiebereglersteuerelement.  
  
##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize  
 Ruft die Größe der Seite für ein Schieberegler-Steuerelement ab.  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe einer Seite für das Schieberegler-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe einer Seite auswirkt, wie viel der Schieberegler für die Benachrichtigungen TB_PAGEUP und TB_PAGEDOWN verschoben wird.  
  
##  <a name="getpos"></a>  CSliderCtrl::GetPos  
 Ruft die aktuelle Position des Schiebereglers in einem Schieberegler-Steuerelement ab.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Position.  
  
##  <a name="getrange"></a>  CSliderCtrl::GetRange  
 Ruft die maximalen und minimalen Positionen für den Schieberegler in einem Schieberegler-Steuerelement ab.  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nmin.*  
 Verweis auf eine ganze Zahl, die die minimale Position empfängt.  
  
 *nmax.*  
 Verweis auf eine ganze Zahl, die die maximale Position empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion kopiert die Werte in ganzen Zahlen verweist *nmin* und *nmax*.  
  
##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax  
 Ruft die maximale Position für den Schieberegler in einem Schiebereglersteuerelement ab.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des Steuerelements maximale.  
  
##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin  
 Ruft die minimale Position für den Schieberegler in einem Schiebereglersteuerelement ab.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des Steuerelements minimale.  
  
##  <a name="getselection"></a>  CSliderCtrl::GetSelection  
 Ruft die Anfangs- und Endposition Positionen der aktuellen Auswahl in einem Schiebereglersteuerelement ab.  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nmin.*  
 Verweis auf eine ganze Zahl, die die Anfangsposition des die aktuelle Auswahl empfängt.  
  
 *nmax.*  
 Verweis auf eine ganze Zahl, die die Endposition der aktuellen Auswahl empfängt.  
  
##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength  
 Ruft die Länge der Schieberegler in der aktuellen Trackbar-Steuerelement ab.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Schiebereglers in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TBM_GETTHUMBLENGTH](/windows/desktop/Controls/tbm-getthumblength) -Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect  
 Ruft ab, die Größe und Position des umschließenden Rechtecks für des Schiebereglers (Ziehpunkt) in einem Schiebereglersteuerelement.  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lprc*  
 Ein Zeiger auf eine `CRect` Objekt, das das umschließende Rechteck für den Schieberegler enthält, wenn die Funktion zurückgibt.  
  
##  <a name="gettic"></a>  CSliderCtrl::GetTic  
 Ruft die Position eines Teilstrichs in einem Schieberegler-Steuerelement ab.  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nTic*  
 Nullbasierter Index, identifizieren einen Teilstrich.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des angegebenen Teilstrichs oder -1, wenn *nTic* gibt kein gültigen Index.  
  
##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray  
 Ruft die Adresse des Arrays, die die Position von Teilstrichen für ein Schieberegler-Steuerelement enthält.  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse des Arrays, die Teilstriche Mark Positionen für das Schieberegler-Steuerelement enthält.  
  
##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos  
 Ruft die aktuelle physische Position eines Teilstrichs in einem Schieberegler-Steuerelement ab.  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nTic*  
 Nullbasierter Index, identifizieren einen Teilstrich.  
  
### <a name="return-value"></a>Rückgabewert  
 Die physische Position in Clientkoordinaten, von der angegebenen Teilstrich oder -1, wenn *nTic* gibt kein gültigen Index.  
  
##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips  
 Ruft das Handle für das QuickInfo-Steuerelement, das Schieberegler-Steuerelement zugewiesen, sofern vorhanden.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt oder NULL, wenn QuickInfos nicht verwendet werden. Wenn Sie das Schieberegler-Steuerelement nicht den TBS_TOOLTIPS-Stil verwendet, ist der Rückgabewert NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_GETTOOLTIPS](/windows/desktop/Controls/tbm-gettooltips), wie im Windows SDK beschrieben. Beachten Sie, die diese Memberfunktion gibt ein `CToolTipCtrl` Objekt anstelle eines Handles für ein Steuerelement.  
  
 Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Stile von Listensteuerelementen Trackbar](/windows/desktop/Controls/trackbar-control-styles) im Windows SDK.  
  
##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy  
 Wird in einem Fenster als das Buddyfenster für ein Schieberegler-Steuerelement.  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndBuddy*  
 Ein Zeiger auf eine `CWnd` -Objekt, das als das Schieberegler-Steuerelement Buddy festgelegt wird.  
  
 *fLocation*  
 Wert, der die Position, an dem das Buddyfenster angezeigt werden sollen angibt. Dieser Wert kann eine der folgenden sein:  
  
- "True" wird dem Buddy links neben die Positionierungsleiste angezeigt, wenn das Trackbar-Steuerelement der Formate TBS_HORZ-Stil verwendet. Wenn die Positionierungsleiste den TBS_VERT-Stil verwendet wird, wird das Buddy über das Trackbar-Steuerelement angezeigt.  
  
- "False" die Buddy erscheint rechts neben die Positionierungsleiste, wenn das Trackbar-Steuerelement der Formate TBS_HORZ-Stil verwendet. Wenn die Positionierungsleiste den TBS_VERT-Stil verwendet wird, wird das Buddy unten das Trackbar-Steuerelement angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das Schieberegler-Steuerelement an diesem Speicherort bereits zugewiesen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_SETBUDDY](/windows/desktop/Controls/tbm-setbuddy), wie im Windows SDK beschrieben. Beachten Sie, dass diese Memberfunktion auf Zeigern auf `CWnd` Objekte anstelle von Fensterhandles für den Rückgabewert und die Parameter.  
  
 Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Stile von Listensteuerelementen Trackbar](/windows/desktop/Controls/trackbar-control-styles) im Windows SDK.  
  
##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize  
 Legt die Größe der Zeile für ein Schieberegler-Steuerelement fest.  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 *nSize*  
 Die neue Zeilengröße des Schieberegler-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Zeilengröße.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeilengröße beeinflusst, wie viel der Schieberegler für die Benachrichtigungen TB_LINEUP und TB_LINEDOWN verschoben wird.  
  
##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize  
 Legt die Größe der Seite für ein Schieberegler-Steuerelement.  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 *nSize*  
 Die neue Seitengröße des Schieberegler-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Seitengröße.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe einer Seite auswirkt, wie viel der Schieberegler für die Benachrichtigungen TB_PAGEUP und TB_PAGEDOWN verschoben wird.  
  
##  <a name="setpos"></a>  CSliderCtrl::SetPos  
 Legt die aktuelle Position des Schiebereglers in einem Schieberegler-Steuerelement fest.  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 *nPos*  
 Gibt die neue Schiebereglerposition an.  
  
##  <a name="setrange"></a>  CSliderCtrl::SetRange  
 Legt den Bereich (minimalen und maximalen Positionen) für den Schieberegler in einem Schiebereglersteuerelement fest.  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *nmin.*  
 Minimale Position für den Schieberegler.  
  
 *nmax.*  
 Maximale Position für den Schieberegler.  
  
 *bRedraw*  
 Das Neuzeichnen-Flag. Wenn dieser Parameter TRUE ist, wird der Schieberegler neu gezeichnet werden, nach dem Festlegen des Bereichs; Andernfalls wird der Schieberegler nicht neu gezeichnet.  
  
##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax  
 Legt den maximalen Bereich für den Schieberegler in einem Schiebereglersteuerelement fest.  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *nmax.*  
 Maximale Position für den Schieberegler.  
  
 *bRedraw*  
 Das Neuzeichnen-Flag. Wenn dieser Parameter TRUE ist, wird der Schieberegler neu gezeichnet werden, nach dem Festlegen des Bereichs; Andernfalls wird der Schieberegler nicht neu gezeichnet.  
  
##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin  
 Legt die minimalen Bereich für den Schieberegler in einem Schiebereglersteuerelement fest.  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *nmin.*  
 Minimale Position für den Schieberegler.  
  
 *bRedraw*  
 Das Neuzeichnen-Flag. Wenn dieser Parameter TRUE ist, wird der Schieberegler neu gezeichnet werden, nach dem Festlegen des Bereichs; Andernfalls wird der Schieberegler nicht neu gezeichnet.  
  
##  <a name="setselection"></a>  CSliderCtrl::SetSelection  
 Legt die Start- und Enddatum für die aktuelle Auswahl in einem Schiebereglersteuerelement fest.  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameter  
 *nmin.*  
 Die Anfangsposition für den Schieberegler.  
  
 *nmax.*  
 Die Endposition für den Schieberegler.  
  
##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength  
 Legt die Länge des Schiebereglers in das aktuelle Trackbar-Steuerelement fest.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *nLength*|Die Länge des Schiebereglers in Pixel.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erfordert, dass das Trackbar-Steuerelement festgelegt werden, um [TBS_FIXEDLENGTH](/windows/desktop/Controls/trackbar-control-styles) Stil.  
  
 Diese Methode sendet die [TBM_SETTHUMBLENGTH](/windows/desktop/Controls/tbm-setthumblength) -Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_sliderCtrl`, d. h. für den Zugriff auf das aktuelle Trackbar-Steuerelement. Das Beispiel definiert auch eine Variable, `thumbLength`, d. h. verwendet, um die standardmäßige Länge der Thumb-Komponente das Trackbar-Steuerelement zu speichern. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt das Trackbar-Steuerelement-Thumb-Steuerelement-Komponente, zweimal die standardmäßige Länge der.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>  CSliderCtrl::SetTic  
 Legt die Position eines Teilstrichs in einem Schieberegler-Steuerelement fest.  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Parameter  
 *nTic*  
 Die Position des Teilstrichs. Dieser Parameter muss einen positiven Wert angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Legen Sie ungleich NULL, wenn es sich bei der Teilstrich festgelegt ist; andernfalls 0.  
  
##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq  
 Legt fest, die Häufigkeit, mit der, die Teilstriche Markierungen in einem Schieberegler angezeigt werden.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Parameter  
 *nFreq*  
 Die Häufigkeit der Teilstriche.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Häufigkeit auf 2 festgelegt ist, wird z. B. ein Teilstrichs für jede anderer Inkrement des Schiebereglers Bereichs angezeigt. Die Standardeinstellung für die Häufigkeit 1 ist (d. h. jedes Inkrement im Bereich ist ein Teilstrich zugeordnet).  
  
 Sie müssen das Steuerelement mit dem TBS_AUTOTICKS-Stil auf diese Funktion verwenden, erstellen. Weitere Informationen finden Sie unter [CSliderCtrl::Create](#create).  
  
##  <a name="settipside"></a>  CSliderCtrl::SetTipSide  
 Positionen verwendet ein QuickInfo-Steuerelement von einem Trackbar-Steuerelement.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Parameter  
 *%nspeicherort*  
 Wert, der die Position, an dem das QuickInfo-Steuerelement angezeigt werden sollen darstellt. Finden Sie eine Liste der möglichen Werte, die Win32-Meldung [TBM_SETTIPSIDE](/windows/desktop/Controls/tbm-settipside), wie im Windows SDK beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der vorherigen Speicherort des QuickInfo-Steuerelements darstellt. Der Rückgabewert einer der möglichen Werte für *%nspeicherort*.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht TBM_SETTIPSIDE, wie im Windows SDK beschrieben. Schieberegler-Steuerelemente, die den Stil TBS_TOOLTIPS verwenden die Anzeige von QuickInfos. Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Stile von Listensteuerelementen Trackbar](/windows/desktop/Controls/trackbar-control-styles) im Windows SDK.  
  
##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips  
 Ein Schieberegler-Steuerelement wird ein QuickInfo-Steuerelement zugewiesen.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndTip*  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) -Objekt, das die QuickInfo für die Verwendung mit dem Schiebereglersteuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_SETTOOLTIPS](/windows/desktop/Controls/tbm-settooltips), wie im Windows SDK beschrieben. Wenn ein Schieberegler-Steuerelement mit dem Stil TBS_TOOLTIPS erstellt wird, wird ein Standard-QuickInfo-Steuerelement, das neben dem Schieberegler, Anzeigen der aktuellen Position des Schiebereglers angezeigt wird. Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Stile von Listensteuerelementen Trackbar](/windows/desktop/Controls/trackbar-control-styles) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl-Klasse](../../mfc/reference/cprogressctrl-class.md)
