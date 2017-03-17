---
title: CProgressCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class
- progress controls [C++], CProgressCtrl class
- Internet Explorer 4.0 common controls
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
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
ms.openlocfilehash: 6c0e9bc16f88018c9f258504924670cc2be31d28
ms.lasthandoff: 02/24/2017

---
# <a name="cprogressctrl-class"></a>CProgressCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Statusanzeige-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Erstellt ein `CProgressCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CProgressCtrl](#create)|Erstellt ein Statusanzeige-Steuerelement und fügt es ein `CProgressCtrl` Objekt.|  
|[CProgressCtrl::CreateEx](#createex)|Erstellt ein Statussteuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CProgressCtrl` Objekt.|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|Ruft die Farbe der Statusanzeige für den aktuellen Statusanzeige-Steuerelement ab.|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe des aktuellen Statusanzeige ab.|  
|[CProgressCtrl::GetPos](#getpos)|Ruft die aktuelle Position der Statusanzeige ab.|  
|[CProgressCtrl::GetRange](#getrange)|Ruft den oberen und unteren Grenzwerten des Bereichs der Statusanzeige-Steuerelements ab.|  
|[CProgressCtrl:: GetState](#getstate)|Ruft den Zustand des aktuellen Statusanzeige-Steuerelements ab.|  
|[CProgressCtrl::GetStep](#getstep)|Ruft die Schrittweite für die Statusanzeige des aktuellen Statusanzeige-Steuerelements ab.|  
|[CProgressCtrl::OffsetPos](#offsetpos)|Verschiebt die aktuelle Position der Statusanzeige-Steuerelement durch eine angegebene Schrittweite und zeichnet die Leiste, um die neue Position wiederzugeben.|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|Legt die Farbe der Statusanzeige in der aktuellen Statusanzeige-Steuerelements fest.|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe für die Statusanzeige zu bewegen.|  
|[CProgressCtrl::SetMarquee](#setmarquee)|Aktiviert den Marquee-Modus aktiviert oder deaktiviert für den aktuellen Statusanzeige-Steuerelement.|  
|[CProgressCtrl::SetPos](#setpos)|Legt die aktuelle Position für ein Statusanzeige-Steuerelement, und zeichnet die Leiste, um die neue Position wiederzugeben.|  
|[CProgressCtrl::SetRange](#setrange)|Legt die minimalen und maximalen Bereiche für ein Statusanzeige-Steuerelement, und zeichnet die Leiste, um die neuen Bereiche widerspiegeln.|  
|[CProgressCtrl::SetState](#setstate)|Legt den Status des aktuellen Statusanzeige-Steuerelements fest.|  
|[CProgressCtrl::SetStep](#setstep)|Gibt die Schrittweite für ein Statusanzeige-Steuerelement.|  
|[CProgressCtrl::StepIt](#stepit)|Erhöht die aktuelle Position für ein Statusanzeige-Steuerelement um die Schrittweite (finden Sie unter [SetStep](#setstep)) und zeichnet die Leiste, um die neue Position wiederzugeben.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Statusanzeige-Steuerelement ist ein Fenster, das eine Anwendung verwenden kann, um den Status eines längeren Vorgangs anzugeben. Es besteht aus einem Rechteck, das allmählich von links nach rechts, mit dem Fortschreiten eines Vorgangs Hervorhebungsfarbe gefüllt wird.  
  
 Ein Statusanzeige-Steuerelement weist einen Bereich und eine aktuelle Position. Bereich stellt die Gesamtdauer des Vorgangs und die aktuelle Position darstellt, den Fortschritt, den die Anwendung, bis zum Abschluss der Operation vorgenommen hat. Die Fensterprozedur verwendet den Bereich und die aktuelle Position, um den Prozentsatz der Statusanzeige mit der Hervorhebungsfarbe füllen zu bestimmen. Da der Bereich und die aktuelle Positionswerte als Ganzzahlen mit Vorzeichen ausgedrückt werden, wird der mögliche Wertebereich aktuelle Position von Â €"2.147.483.648 bis 2.147.483.647 (einschließlich).  
  
 Weitere Informationen zur Verwendung von `CProgressCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CProgressCtrl](../../mfc/using-cprogressctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="cprogressctrl"></a>CProgressCtrl::CProgressCtrl  
 Erstellt ein `CProgressCtrl`-Objekt.  
  
```  
CProgressCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen der `CProgressCtrl` -Objekt, rufen Sie `CProgressCtrl::Create` auf das Statusanzeige-Steuerelement zu erstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&#1;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="create"></a>CProgressCtrl  
 Erstellt ein Statusanzeige-Steuerelement und fügt es ein `CProgressCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Fortschrittsanzeige-Stil. Wenden Sie eine beliebige Kombination von Fenster Stylesdescribed in [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], zusätzlich zu den folgenden Steuerelementtypen, um das Steuerelement der Statusanzeige:  
  
- `PBS_VERTICAL`Zeigt Informationen vertikal, wenn Sie von oben nach unten. Ohne dieses Flag zeigt das Statusanzeige-Steuerelement horizontal, links nach rechts.  
  
- `PBS_SMOOTH`Zeigt die schrittweise und das Statusanzeige-Steuerelement ausfüllen. Ohne dieses Flag wird das Steuerelement mit Blöcken ausfüllen.  
  
 `rect`  
 Gibt des Statusanzeige-Steuerelements die Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur. Da das Steuerelement ein untergeordnetes Fenster sein muss, werden die angegebenen Koordinaten relativ zum Clientbereich des der `pParentWnd`.  
  
 `pParentWnd`  
 Gibt die Statusanzeige übergeordnete Fenster des Steuerelements, normalerweise eine `CDialog`. Er darf nicht sein **NULL.**  
  
 `nID`  
 Gibt das Statusanzeige-Steuerelement ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn das `CProgressCtrl` Objekt erfolgreich erstellt wird; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CProgressCtrl` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, der erstellt die `CProgressCtrl` -Objekt, und rufen dann **erstellen**, erstellt das Statusanzeige-Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&#2;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CProgressCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CProgressCtrl` Objekt.  
  
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
 Gibt die Fortschrittsanzeige-Stil. Wenden Sie eine beliebige Kombination von Window-Stile in beschriebenen [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="getbarcolor"></a>CProgressCtrl::GetBarColor  
 Ruft die Farbe der Statusanzeige für den aktuellen Statusanzeige-Steuerelement ab.  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe des aktuellen Statusanzeige dargestellt, wie eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert oder `CLR_DEFAULT` Indikator Leiste Statusfarbe ist die Standardfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbkcolor"></a>CProgressCtrl::GetBkColor  
 Ruft die Hintergrundfarbe des aktuellen Statusanzeige ab.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Hintergrundfarbe des aktuellen Statusanzeige dargestellt, wie eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getpos"></a>CProgressCtrl::GetPos  
 Ruft die aktuelle Position der Statusanzeige ab.  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position der Statusanzeige-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Position der Statusanzeige-Steuerelements ist nicht der physische Speicherort auf dem Bildschirm, aber stattdessen wird zwischen der oberen und unteren Bereich angegeben [SetRange](#setrange).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&3;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="getrange"></a>CProgressCtrl::GetRange  
 Ruft die aktuelle oberen und unteren Grenzwerten oder den Bereich der Statusanzeige-Steuerelements.  
  
```  
void GetRange(
    int& nLower,  
    int& nUpper);
```  
  
### <a name="parameters"></a>Parameter  
 `nLower`  
 Ein Verweis auf eine ganze Zahl, die die untere Grenze der Statusanzeige-Steuerelements empfängt.  
  
 `nUpper`  
 Ein Verweis auf eine ganze Zahl, die die obere Grenze der Statusanzeige-Steuerelements empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion kopiert die Werte der oberen und unteren Grenzen in der ganzen Zahlen, auf die verwiesen wird `nLower` und `nUpper`bzw..  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&4;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="getstate"></a>CProgressCtrl:: GetState  
 Ruft den Zustand des aktuellen Statusanzeige-Steuerelements ab.  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status der der aktuellen Statusanzeige-Steuerelement, das einen der folgenden Werte ist:  
  
|Wert|Zustand|  
|-----------|-----------|  
|`PBST_NORMAL`|In Bearbeitung|  
|`PBST_ERROR`|Fehler|  
|`PBST_PAUSED`|Angehalten|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft den Zustand des aktuellen Statusanzeige-Steuerelements ab.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1&5;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="getstep"></a>CProgressCtrl::GetStep  
 Ruft die Schrittweite für die Statusanzeige des aktuellen Statusanzeige-Steuerelements ab.  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Schrittweite der Statusanzeige.  
  
### <a name="remarks"></a>Hinweise  
 Die Schrittweite ist der Betrag, einen Aufruf von [CProgressCtrl::StepIt](#stepit) erhöht die aktuelle Position der Statusanzeige.  
  
 Diese Methode sendet die [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft die Schrittweite des aktuellen Statusanzeige-Steuerelements ab.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1&3;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="offsetpos"></a>CProgressCtrl::OffsetPos  
 Verschiebt die aktuelle Position des Steuerelements der Statusanzeige um das Inkrement angegebenen `nPos` und zeichnet die Leiste, um die neue Position wiederzugeben.  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Betrag, um die Position.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherigen Position der Statusanzeige-Steuerelements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&5;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="setbarcolor"></a>CProgressCtrl::SetBarColor  
 Legt die Farbe der Statusanzeige in der aktuellen Statusanzeige-Steuerelements fest.  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `clrBar`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die neue Farbe von der Statusanzeige angibt. Geben Sie `CLR_DEFAULT` um die Statusanzeige zu bewegen, verwenden Sie die Standardfarbe verursachen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Farbe die Statusanzeige, dargestellt als ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert oder `CLR_DEFAULT` ist die Farbe der Statusanzeige die Standardfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Die `SetBarColor` Methode legt die Statusanzeige Farbe nur, wenn ein [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] [Design](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx) ist nicht aktiv.  
  
 Diese Methode sendet die [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ändert die Farbe der Statusleiste in Rot, Grün, Blau oder die Standardeinstellung.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="setbkcolor"></a>CProgressCtrl::SetBkColor  
 Legt die Hintergrundfarbe für die Statusanzeige zu bewegen.  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Parameter  
 `clrNew`  
 Ein **COLORREF** Wert, der die neue Hintergrundfarbe angibt. Geben Sie den `CLR_DEFAULT` Wert, der die Standardhintergrundfarbe für die Statusanzeige verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die vorherige Hintergrundfarbe oder **CLR_DEFAULT** die Hintergrundfarbe ist die Standardfarbe.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&6;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="setmarquee"></a>CProgressCtrl::SetMarquee  
 Aktiviert den Marquee-Modus aktiviert oder deaktiviert für den aktuellen Statusanzeige-Steuerelement.  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `fMarqueeMode`|`true`Um Marquee-Modus zu aktivieren, oder `false` zu Marquee-Modus zu deaktivieren.|  
|[in] `nInterval`|Zeit in Millisekunden zwischen den Aktualisierungen der Marquee-Animation.|  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt immer `true` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Marquee-Modus aktiviert ist, die Statusanzeige animiert wird und führt z. B. ein Zeichen in einer Theater Laufschrift.  
  
 Diese Methode sendet die [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird gestartet und beendet die Laufschrift Animation.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="setpos"></a>CProgressCtrl::SetPos  
 Legt den Status Balken der aktuellen Position des Steuerelements entsprechend den Angaben von `nPos` und zeichnet die Leiste, um die neue Position wiederzugeben.  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Neue Position der Statusanzeige-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherigen Position der Statusanzeige-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Position der Statusanzeige-Steuerelements ist nicht der physische Speicherort auf dem Bildschirm, aber stattdessen wird zwischen der oberen und unteren Bereich angegeben [SetRange](#setrange).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&#7;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CProgressCtrl::SetRange  
 Legt den oberen und unteren Grenzen der Statusanzeige Bereichs des Steuerelements und zeichnet die Leiste, um die neuen Bereiche widerspiegeln.  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>Parameter  
 `nLower`  
 Gibt die Untergrenze des Bereichs (der Standardwert ist&0; (null)).  
  
 `nUpper`  
 Gibt die obere Grenze des Bereichs (die Standardeinstellung ist 100).  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion `SetRange32` der 32-Bit-Bereich für das Statussteuerelement festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&#8;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
##  <a name="setstate"></a>CProgressCtrl::SetState  
 Legt den Status des aktuellen Statusanzeige-Steuerelements fest.  
  
```  
int SetState(int iState);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iState`|Der Status zum Festlegen der Statusleiste. Verwenden Sie einen der folgenden Werte:<br /><br /> - `PBST_NORMAL`-In Bearbeitung<br />- `PBST_ERROR`-Fehler<br />- `PBST_PAUSED`-Angehalten|  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Status des aktuellen Statusanzeige-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird der Status des aktuellen Statusanzeige-Steuerelements auf angehalten oder In Bearbeitung festgelegt.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="setstep"></a>CProgressCtrl::SetStep  
 Gibt die Schrittweite für ein Statusanzeige-Steuerelement.  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>Parameter  
 *nStep*  
 Neue Schrittweite.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Schrittweite.  
  
### <a name="remarks"></a>Hinweise  
 Die Schrittweite ist der Betrag, einen Aufruf von `CProgressCtrl::StepIt` den Fortschritt erhöht die aktuelle Position.  
  
 Die Schrittweite der Standard ist 10.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&#9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="stepit"></a>CProgressCtrl::StepIt  
 Erhöht die aktuelle Position für ein Statusanzeige-Steuerelement um die Schrittweite und zeichnet die Leiste, um die neue Position wiederzugeben.  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherigen Position der Statusanzeige-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Schrittweite wird festgelegt, indem die `CProgressCtrl::SetStep` -Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl&#10;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



