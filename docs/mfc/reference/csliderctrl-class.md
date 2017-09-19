---
title: CSliderCtrl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- Windows common controls [C++], CSliderCtrl
- slider controls, CSliderCtrl class
- CSliderCtrl class, common controls
- CSliderCtrl class
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
caps.latest.revision: 22
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 745dc253ac0837ffc62f47db2038e6302b83b558
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="csliderctrl-class"></a>CSliderCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Schieberegler-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|Erstellt ein `CSliderCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|Löscht die aktuelle Auswahl in einem Schiebereglersteuerelement.|  
|[CSliderCtrl::ClearTics](#cleartics)|Entfernt die aktuelle Teilstriche aus ein Schieberegler-Steuerelement.|  
|[CSliderCtrl::Create](#create)|Erstellt ein Schieberegler-Steuerelement, und fügt es einer `CSliderCtrl` Objekt.|  
|[CSliderCtrl::CreateEx](#createex)|Erstellt ein Schieberegler-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es einer `CSliderCtrl` Objekt.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|Ruft das Handle für ein Schieberegler-Steuerelement Buddy-Fenster an einer angegebenen Position ab.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|Ruft die Größe des Kanals das Schieberegler-Steuerelement ab.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|Ruft die Größe des Schieberegler-Steuerelements ab.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|Ruft die Anzahl von Teilstrichen in ein Schieberegler-Steuerelement ab.|  
|[CSliderCtrl::GetPageSize](#getpagesize)|Ruft die Seitengröße des Schieberegler-Steuerelement ab.|  
|[CSliderCtrl::GetPos](#getpos)|Ruft die aktuelle Position des Schiebereglers ab.|  
|[CSliderCtrl::GetRange](#getrange)|Ruft die minimalen und maximalen Positionen für einen Schieberegler ab.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|Ruft die maximale Position für ein Schieberegler ab.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|Ruft die minimale Position für ein Schieberegler ab.|  
|[CSliderCtrl::GetSelection](#getselection)|Ruft den Bereich der aktuellen Auswahl ab.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|Ruft die Länge des Schiebereglers in der aktuellen Trackbar-Steuerelement ab.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|Ruft die Größe des Ziehpunkts das Schieberegler-Steuerelement ab.|  
|[CSliderCtrl::GetTic](#gettic)|Ruft die Position des angegebenen Teilstrichs ab.|  
|[CSliderCtrl::GetTicArray](#getticarray)|Ruft das Array von Teilstrichen Markierung Positionen für ein Schieberegler-Steuerelement ab.|  
|[CSliderCtrl::GetTicPos](#getticpos)|Ruft die Position des angegebenen Teilstrichs in Clientkoordinaten ab.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|Ruft das Handle für das QuickInfo-Steuerelement, das Schieberegler-Steuerelement zugewiesen, sofern vorhanden.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Weist ein Fenster als Buddyfenster für ein Schieberegler-Steuerelement.|  
|[CSliderCtrl::SetLineSize](#setlinesize)|Legt die Größe des Schieberegler-Steuerelements fest.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|Legt die Seitengröße des Schieberegler-Steuerelement fest.|  
|[CSliderCtrl::SetPos](#setpos)|Legt die aktuelle Position des Schiebereglers fest.|  
|[CSliderCtrl::SetRange](#setrange)|Legt die minimalen und maximalen Positionen für einen Schieberegler fest.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|Legt die maximale Position für ein Schieberegler fest.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|Legt die minimale Position für ein Schieberegler fest.|  
|[CSliderCtrl::SetSelection](#setselection)|Legt den Bereich der aktuellen Auswahl fest.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|Legt die Länge des Schiebereglers in der aktuellen Trackbar-Steuerelement fest.|  
|[CSliderCtrl::SetTic](#settic)|Legt die Position des angegebenen Teilstrichs fest.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|Legt die Häufigkeit der Teilstriche Markierungen pro Inkrement der Schieberegler-Steuerelement fest.|  
|[CSliderCtrl::SetTipSide](#settipside)|Positionen verwendet ein QuickInfo-Steuerelement von einem Trackbar-Steuerelement.|  
|[CSliderCtrl::SetToolTips](#settooltips)|Ein Schieberegler-Steuerelement ein QuickInfo-Steuerelement zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Schieberegler-Steuerelement" (auch bekannt als Trackbar) ist ein Fenster, das ein Schieberegler und optionalen Teilstrichen enthält. Wenn der Benutzer mit der Maus oder die Schlüssel für die Richtung des Schiebereglers verschoben wird, sendet das Steuerelement benachrichtigungsmeldungen an, dass die Änderung.  
  
 Schieberegler-Steuerelemente sind nützlich, wenn Sie möchten, dass den Benutzer einen diskreten Wert oder einen Satz von aufeinander folgenden Werten in einem Bereich auswählen. Beispielsweise können Sie ein Schieberegler-Steuerelement verwenden, damit der Benutzer die Wiederholung Rate der Tastatur mithilfe des Schiebereglers auf einen bestimmten Teilstrich festlegen kann.  
  
 Dieses Steuerelement (und somit die `CSliderCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Der Schieberegler verschiebt, die Sie bei der Erstellung angeben. Beispielsweise, wenn Sie angeben, dass der Schieberegler auf einen Bereich von fünf haben soll, der Schieberegler kann nur sechs Positionen einnehmen: eine Position auf der linken Seite des Schieberegler-Steuerelement und eine Position für jedes Inkrement des Bereichs. In der Regel wird jeder dieser Positionen durch ein Teilstrich identifiziert.  
  
 Sie erstellen einen Schieberegler mit dem Konstruktor und die **erstellen** Memberfunktion von `CSliderCtrl`. Nachdem Sie ein Schieberegler-Steuerelement erstellt haben, können Sie Memberfunktionen in `CSliderCtrl` viele der Eigenschaften ändern. Änderungen, die Sie vornehmen können, gehören das Festlegen der minimalen und maximalen Positionen für den Schieberegler, Teilstriche gezeichnet, einen Auswahlbereich festlegen, und Neupositionieren des Schiebereglers.  
  
 Weitere Informationen zur Verwendung von `CSliderCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="clearsel"></a>CSliderCtrl::ClearSel  
 Löscht die aktuelle Auswahl in einem Schiebereglersteuerelement.  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bRedraw`  
 Flag neu gezeichnet werden. Wenn dieser Parameter ist **"true"**, der Schieberegler nach dem Löschen der Auswahl neu gezeichnet wird; andernfalls der Schieberegler nicht neu gezeichnet wird.  
  
##  <a name="cleartics"></a>CSliderCtrl::ClearTics  
 Entfernt die aktuelle Teilstriche aus ein Schieberegler-Steuerelement.  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bRedraw`  
 Flag neu gezeichnet werden. Wenn dieser Parameter ist **"true"**, der Schieberegler neu gezeichnet wird, nachdem die Teilstriche gelöscht werden; andernfalls der Schieberegler nicht neu gezeichnet wird.  
  
##  <a name="create"></a>CSliderCtrl::Create  
 Erstellt ein Schieberegler-Steuerelement, und fügt es einer `CSliderCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Schieberegler-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Stile der Schieberegler-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb760147), beschrieben, in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], an das Steuerelement.  
  
 `rect`  
 Gibt an, Größe und Position des Schieberegler-Steuerelements. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Schieberegler-Steuerelement übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt das Schieberegler-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CSliderCtrl` in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie anschließend **erstellen**, die das Schieberegler-Steuerelement erstellt, und fügt es der `CSliderCtrl` Objekt.  
  
 Abhängig von den Werten für festgelegt `dwStyle`, das Schieberegler-Steuerelement eine horizontaler oder vertikaler Ausrichtung haben kann. Es kann Teilstriche auf einer Seite, haben beide Seiten oder keines von beiden. Es kann auch verwendet werden, um einen Bereich aufeinander folgender Werte anzugeben.  
  
 Rufen Sie zum Anwenden von erweiterten Fensterstile auf das Schieberegler-Steuerelement [CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="createex"></a>CSliderCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CSliderCtrl` Objekt.  
  
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
 Gibt das Schieberegler-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Stile der Schieberegler-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb760147), beschrieben, in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], an das Steuerelement.  
  
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
  
##  <a name="csliderctrl"></a>CSliderCtrl::CSliderCtrl  
 Erstellt ein `CSliderCtrl`-Objekt.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>CSliderCtrl::GetBuddy  
 Ruft das Handle für ein Schieberegler-Steuerelement Buddy-Fenster an einer angegebenen Position ab.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `fLocation`  
 Ein boolescher Wert, der die zwei Buddy Fensterhandles abzurufenden angibt. Kann einer der folgenden Werte sein:  
  
- **"True"** Ruft das Handle für den Kontakt auf der linken Seite des Schiebereglers ab. Wenn das Schieberegler-Steuerelement verwendet die `TBS_VERT` Stil, Abrufen der Nachricht die Buddy oberhalb des Schiebereglers.  
  
- **"False"** Ruft das Handle an die Freund des Schiebereglers rechts ab. Wenn das Schieberegler-Steuerelement verwendet die `TBS_VERT` Stil, Abrufen der Nachricht die Buddy unterhalb des Schiebereglers.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das Buddyfenster an der vom angegebenen Position ist `fLocation`, oder **NULL** Wenn kein Buddyfenster an diesem Speicherort vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Trackbar-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760147) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getchannelrect"></a>CSliderCtrl::GetChannelRect  
 Ruft die Größe und Position des umschließenden Rechtecks für ein Schieberegler-Steuerelement-Kanal.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Ein Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Größe und Position des Kanals enthält des umschließenden Rechtecks, wenn die Funktion zurückgibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Kanal ist ein Bereich über die verschiebt des Schiebereglers, und der die Hervorhebung enthält, wenn ein Bereich ausgewählt ist.  
  
##  <a name="getlinesize"></a>CSliderCtrl::GetLineSize  
 Ruft die Größe der Zeile für ein Schieberegler-Steuerelement ab.  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe einer Zeile für das Schieberegler-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe der wirkt sich auf wie viel des Schiebereglers für verschiebt die **TB_LINEUP** und **TB_LINEDOWN** Benachrichtigungen. Die Standardeinstellung für die Zeilengröße ist 1.  
  
##  <a name="getnumtics"></a>CSliderCtrl::GetNumTics  
 Ruft die Anzahl von Teilstrichen in ein Schieberegler-Steuerelement ab.  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Teilstrichen in das Schieberegler-Steuerelement.  
  
##  <a name="getpagesize"></a>CSliderCtrl::GetPageSize  
 Ruft die Größe der Seite für ein Schieberegler-Steuerelement ab.  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe einer Seite für das Schieberegler-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die Seitengröße wirkt sich auf wie viel des Schiebereglers für verschiebt die **TB_PAGEUP** und **TB_PAGEDOWN** Benachrichtigungen.  
  
##  <a name="getpos"></a>CSliderCtrl::GetPos  
 Ruft die aktuelle Position des Schiebereglers in ein Schieberegler-Steuerelement ab.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Position.  
  
##  <a name="getrange"></a>CSliderCtrl::GetRange  
 Ruft die maximalen und minimalen Positionen für den Schieberegler ein Schieberegler-Steuerelement ab.  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nMin`  
 Verweis auf eine ganze Zahl, die die minimale Position empfängt.  
  
 `nMax`  
 Verweis auf eine ganze Zahl, die die maximale Position empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion kopiert die Werte in der ganzen Zahlen verweist `nMin` und `nMax`.  
  
##  <a name="getrangemax"></a>CSliderCtrl::GetRangeMax  
 Ruft die maximale Position für den Schieberegler im Schieberegler-Steuerelement ab.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Maximale Position des Steuerelements.  
  
##  <a name="getrangemin"></a>CSliderCtrl::GetRangeMin  
 Ruft die minimale Position für den Schieberegler in einem Schiebereglersteuerelement ab.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Minimale Position des Steuerelements.  
  
##  <a name="getselection"></a>CSliderCtrl::GetSelection  
 Ruft die Start- und Enddatum Positionen von der aktuellen Auswahl im Schieberegler-Steuerelement ab.  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nMin`  
 Verweis auf eine ganze Zahl, die die Anfangsposition der aktuellen Auswahl empfängt.  
  
 `nMax`  
 Verweis auf eine ganze Zahl, die die Endposition der aktuellen Auswahl empfängt.  
  
##  <a name="getthumblength"></a>CSliderCtrl::GetThumbLength  
 Ruft die Länge des Schiebereglers in der aktuellen Trackbar-Steuerelement ab.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Schiebereglers, in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) Nachricht, die in beschrieben ist die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getthumbrect"></a>CSliderCtrl::GetThumbRect  
 Ruft die Größe und Position des umschließenden Rechtecks für den Schieberegler (Ziehpunkt) in ein Schieberegler-Steuerelement.  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lprc`  
 Ein Zeiger auf ein `CRect` Objekt, das das umschließende Rechteck für den Schieberegler enthält, wenn die Funktion zurückgibt.  
  
##  <a name="gettic"></a>CSliderCtrl::GetTic  
 Ruft die Position eines Teilstrichs in ein Schieberegler-Steuerelement ab.  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nTic`  
 Nullbasierter Index ein Teilstrichs identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des angegebenen Teilstrichs oder -1, wenn `nTic` gibt keinen gültigen Index.  
  
##  <a name="getticarray"></a>CSliderCtrl::GetTicArray  
 Ruft die Adresse des Arrays, die die Position von Teilstrichen für ein Schieberegler-Steuerelement enthält.  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse des Arrays, Teilstriche Markierung Positionen für das Schieberegler-Steuerelement enthält.  
  
##  <a name="getticpos"></a>CSliderCtrl::GetTicPos  
 Ruft die aktuelle physische Position eines Teilstrichs in ein Schieberegler-Steuerelement ab.  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nTic`  
 Nullbasierter Index ein Teilstrichs identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Die physische Position in Clientkoordinaten, der den angegebenen Teilstrich oder -1, wenn `nTic` gibt keinen gültigen Index.  
  
##  <a name="gettooltips"></a>CSliderCtrl::GetToolTips  
 Ruft das Handle für das QuickInfo-Steuerelement, das Schieberegler-Steuerelement zugewiesen, sofern vorhanden.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) -Objekt, oder **NULL** wenn QuickInfos nicht verwendet werden. Wenn das Schieberegler-Steuerelement nicht verwendet die **TBS_TOOLTIPS** Formatvorlage, der Rückgabewert ist **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Beachten Sie, die diese Memberfunktion gibt ein `CToolTipCtrl` Objekt anstatt ein Handle für ein Steuerelement.  
  
 Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Trackbar-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760147) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbuddy"></a>CSliderCtrl::SetBuddy  
 Weist ein Fenster als Buddyfenster für ein Schieberegler-Steuerelement.  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndBuddy`  
 Ein Zeiger auf eine `CWnd` -Objekt, das als das Schieberegler-Steuerelement Buddy festgelegt wird.  
  
 `fLocation`  
 -Wert, der die Position, an dem das Buddyfenster angezeigt. Dieser Wert kann eine der folgenden sein:  
  
- **"True"** der Buddy wird links neben der Trackbar angezeigt, wenn das Trackbar-Steuerelement verwendet die `TBS_HORZ` Stil. Wenn die Trackbar verwendet die `TBS_VERT` formatieren, der Kontakt wird über das Trackbar-Steuerelement angezeigt.  
  
- **"False"** der Buddy wird rechts neben der Trackbar angezeigt, wenn das Trackbar-Steuerelement verwendet die `TBS_HORZ` Stil. Wenn die Trackbar verwendet die `TBS_VERT` Formatieren der Buddy wird unterhalb der Trackbar-Steuerelement angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das Schieberegler-Steuerelement an dieser Stelle bereits zugewiesen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Beachten Sie, dass diese Memberfunktion Zeiger auf verwendet `CWnd` Objekte anstelle von Fensterhandles hinsichtlich der Rückgabewert und die Parameter.  
  
 Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Trackbar-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760147) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlinesize"></a>CSliderCtrl::SetLineSize  
 Legt die Größe der Zeile für ein Schieberegler-Steuerelement.  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 `nSize`  
 Die neue Zeilengröße des Schieberegler-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Zeilengröße.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe der wirkt sich auf wie viel des Schiebereglers für verschiebt die **TB_LINEUP** und **TB_LINEDOWN** Benachrichtigungen.  
  
##  <a name="setpagesize"></a>CSliderCtrl::SetPageSize  
 Legt die Größe der Seite für ein Schieberegler-Steuerelement.  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 `nSize`  
 Die neue Seitengröße des Schieberegler-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Seitengröße.  
  
### <a name="remarks"></a>Hinweise  
 Die Seitengröße wirkt sich auf wie viel des Schiebereglers für verschiebt die **TB_PAGEUP** und **TB_PAGEDOWN** Benachrichtigungen.  
  
##  <a name="setpos"></a>CSliderCtrl::SetPos  
 Legt die aktuelle Position des Schiebereglers in ein Schieberegler-Steuerelement fest.  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt die neue Schiebereglerposition an.  
  
##  <a name="setrange"></a>CSliderCtrl::SetRange  
 Legt den Bereich (minimalen und maximalen Positionen) für den Schieberegler in einem Schiebereglersteuerelement fest.  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `nMin`  
 Minimale Position für den Schieberegler.  
  
 `nMax`  
 Maximale Position für den Schieberegler.  
  
 `bRedraw`  
 Das Neuzeichnen-Flag. Wenn dieser Parameter ist **"true"**, der Schieberegler nach dem Festlegen des Bereichs der neu gezeichnet wird; andernfalls der Schieberegler nicht neu gezeichnet wird.  
  
##  <a name="setrangemax"></a>CSliderCtrl::SetRangeMax  
 Legt den maximalen Bereich für den Schieberegler in einem Schiebereglersteuerelement fest.  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `nMax`  
 Maximale Position für den Schieberegler.  
  
 `bRedraw`  
 Das Neuzeichnen-Flag. Wenn dieser Parameter ist **"true"**, der Schieberegler nach dem Festlegen des Bereichs der neu gezeichnet wird; andernfalls der Schieberegler nicht neu gezeichnet wird.  
  
##  <a name="setrangemin"></a>CSliderCtrl::SetRangeMin  
 Legt die minimale Bereich für den Schieberegler in einem Schiebereglersteuerelement fest.  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `nMin`  
 Minimale Position für den Schieberegler.  
  
 `bRedraw`  
 Das Neuzeichnen-Flag. Wenn dieser Parameter ist **"true"**, der Schieberegler nach dem Festlegen des Bereichs der neu gezeichnet wird; andernfalls der Schieberegler nicht neu gezeichnet wird.  
  
##  <a name="setselection"></a>CSliderCtrl::SetSelection  
 Legt die Start- und Enddatum für die aktuelle Auswahl in einem Schiebereglersteuerelement fest.  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `nMin`  
 Die Anfangsposition für den Schieberegler.  
  
 `nMax`  
 Die Endposition für den Schieberegler.  
  
##  <a name="setthumblength"></a>CSliderCtrl::SetThumbLength  
 Legt die Länge des Schiebereglers in der aktuellen Trackbar-Steuerelement fest.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nLength`|Die Länge des Schiebereglers, in Pixel.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erfordert, dass das Trackbar-Steuerelement festgelegt werden, um [TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147) Stil.  
  
 Diese Methode sendet die [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) Nachricht, die in beschrieben ist die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_sliderCtrl`, d. h. auf das aktuelle Trackbar-Steuerelement verwendet. Im Beispiel definiert auch eine Variable `thumbLength`, d. h. verwendet, um die standardmäßige Länge der Trackbar-Steuerelement Thumb-Komponente zu speichern. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1 Nr. 1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt Trackbar-Steuerelement Thumb-Komponente zu zweimal die Standardlänge.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>CSliderCtrl::SetTic  
 Legt die Position eines Teilstrichs in ein Schieberegler-Steuerelement fest.  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>Parameter  
 `nTic`  
 Die Position des Teilstrichs. Dieser Parameter muss einen positiven Wert angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Teilstrich festgelegt ist; andernfalls 0.  
  
##  <a name="setticfreq"></a>CSliderCtrl::SetTicFreq  
 Legt die Häufigkeit, mit der, die Teilstriche Markierungen in ein Schieberegler angezeigt werden.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>Parameter  
 *nFreq*  
 Häufigkeit der Teilstriche.  
  
### <a name="remarks"></a>Hinweise  
 Die Häufigkeit auf 2 festgelegt ist, wird z. B. ein Teilstrichs für alle anderen Inkrement in den Schieberegler liegen im Bereich angezeigt. Die Standardeinstellung für die Frequenz 1 ist (d. h. jedes Inkrement des Bereichs ist ein Teilstrich zugeordnet).  
  
 Müssen Sie das Steuerelement mit dem Erstellen der `TBS_AUTOTICKS` Formatvorlage, die diese Funktion verwenden. Weitere Informationen finden Sie unter [CSliderCtrl::Create](#create).  
  
##  <a name="settipside"></a>CSliderCtrl::SetTipSide  
 Positionen verwendet ein QuickInfo-Steuerelement von einem Trackbar-Steuerelement.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>Parameter  
 `nLocation`  
 Wert, der die Position, an dem das QuickInfo-Steuerelement angezeigt darstellt. Eine Liste der möglichen Werte finden Sie unter der Win32-Meldung [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der vorherigen Position das QuickInfo-Steuerelement darstellt. Der zurückgegebene Wert entspricht einer der möglichen Werte für `nLocation`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht **TBM_SETTIPSIDE**gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Schieberegler-Steuerelemente, verwenden die **TBS_TOOLTIPS** formatieren Sie QuickInfos anzeigen. Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Trackbar-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760147) in der [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
##  <a name="settooltips"></a>CSliderCtrl::SetToolTips  
 Ein Schieberegler-Steuerelement ein QuickInfo-Steuerelement zugewiesen.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndTip`  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt, das die QuickInfo für die Verwendung mit dem Schieberegler-Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn ein Schieberegler-Steuerelement erstellt wird, mit der **TBS_TOOLTIPS** Stil erstellt ein Standard-QuickInfo-Steuerelement, das neben dem Schieberegler, Anzeigen der aktuellen Position des Schiebereglers angezeigt wird. Eine Beschreibung der Stile der Schieberegler-Steuerelemente, finden Sie unter [Trackbar-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760147) in der [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl-Klasse](../../mfc/reference/cprogressctrl-class.md)

