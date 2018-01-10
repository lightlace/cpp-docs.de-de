---
title: CProgressCtrl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7def2d1a6b421259a2b0d5e8229165ea0593874
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cprogressctrl-class"></a>CProgressCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Statusanzeige-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Erstellt ein `CProgressCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CProgressCtrl](#create)|Erstellt eine Statusanzeige-Steuerelement, und fügt es einer `CProgressCtrl` Objekt.|  
|[CProgressCtrl::CreateEx](#createex)|Erstellt ein Statussteuerelement mit der angegebenen erweiterten Fensterstile und fügt es einer `CProgressCtrl` Objekt.|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|Ruft die Farbe der Statusanzeige für den aktuellen Statusanzeige-Steuerelements ab.|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe des aktuellen Statusanzeige ab.|  
|[CProgressCtrl::GetPos](#getpos)|Ruft die aktuelle Position der Statusanzeige ab.|  
|[CProgressCtrl::GetRange](#getrange)|Ruft die oberen und unteren Grenzen des Bereichs der Statusanzeige-Steuerelements ab.|  
|[CProgressCtrl:: GetState](#getstate)|Ruft den Zustand des aktuellen Statusanzeige-Steuerelements ab.|  
|[CProgressCtrl::GetStep](#getstep)|Ruft die Schrittweite für die Statusanzeige des aktuellen Statusanzeige-Steuerelements ab.|  
|[CProgressCtrl::OffsetPos](#offsetpos)|Erhöht die aktuelle Position eines Statusanzeige-Steuerelements durch eine bestimmte Schrittweite aufweist, und zeichnet die Leiste, um die neue Position wiedergegeben.|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|Legt die Farbe der Statusanzeige in der aktuellen Statusanzeige-Steuerelements fest.|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe für die Statusanzeige fest.|  
|[CProgressCtrl::SetMarquee](#setmarquee)|Aktiviert die Laufschrift-Modus aktiviert oder deaktiviert für den aktuellen Statusanzeige-Steuerelements.|  
|[CProgressCtrl::SetPos](#setpos)|Legt die aktuelle Position für eine Statusanzeige-Steuerelement fest und zeichnet die Leiste, um die neue Position wiedergegeben.|  
|[CProgressCtrl::SetRange](#setrange)|Legt die minimalen und maximalen Bereiche für eine Statusanzeige-Steuerelement, und zeichnet die Leiste entsprechend der neuen Bereiche.|  
|[CProgressCtrl::SetState](#setstate)|Legt den Status des aktuellen Statusanzeige-Steuerelements fest.|  
|[CProgressCtrl::SetStep](#setstep)|Gibt die Schrittweite für eine Statusanzeige-Steuerelements an.|  
|[CProgressCtrl::StepIt](#stepit)|Erhöht die aktuelle Position für eine Statusanzeige-Steuerelements durch die Schrittweite (finden Sie unter [SetStep](#setstep)) und zeichnet die Leiste, um die neue Position wiedergegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Statusanzeige-Steuerelement ist ein Fenster, das eine Anwendung verwenden kann, um den Fortschritt einer längeren Operation anzugeben. Er besteht aus einem Rechteck, das allmählich von links nach rechts, mit dem Fortschreiten eines Vorgangs Hervorhebungsfarbe gefüllt wird.  
  
 Eine Statusanzeige-Steuerelement verfügt über einen Bereich und eine aktuelle Position. Den Bereich darstellt, die gesamte Dauer des Vorgangs, und die aktuelle Position darstellt, den Status die Anwendung bis zum Abschließen des Vorgangs vorgenommen wurde. Die Fensterprozedur verwendet den Bereich und die aktuelle Position, um den Prozentsatz der Statusanzeige mit der Hervorhebungsfarbe auszufüllende zu bestimmen. Da der Bereich und die aktuelle Positionswerte als Ganzzahlen mit Vorzeichen angegeben sind, werden der mögliche Wertebereich aktuelle Position von-2.147.483.648 bis 2.147.483.647 liegen.  
  
 Weitere Informationen zur Verwendung von `CProgressCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CProgressCtrl](../../mfc/using-cprogressctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Nach dem Erstellen der `CProgressCtrl` -Objekt, rufen Sie `CProgressCtrl::Create` das Statusanzeige-Steuerelement zu erstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="create"></a>CProgressCtrl  
 Erstellt eine Statusanzeige-Steuerelement, und fügt es einer `CProgressCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Statusanzeige-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Fenster Stylesdescribed in [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) im Windows SDK, zusätzlich zu den folgenden Statusanzeige Steuerelementtypen an das Steuerelement:  
  
- `PBS_VERTICAL`Zeigt Informationen vertikal Status, von oben nach unten. Wenn dieses Kennzeichen nicht zeigt das Statusanzeige-Steuerelement horizontal und/oder links nach rechts.  
  
- `PBS_SMOOTH`Zeigt die schrittweisen, smooth ausfüllen das Statusanzeige-Steuerelement. Wenn dieses Kennzeichen wird das Steuerelement mit Blöcken füllen.  
  
 `rect`  
 Gibt an, des Statusanzeige-Steuerelements die Größe und Position. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur. Da das Steuerelement ein untergeordnetes Fenster sein muss, werden die angegebenen Koordinaten relativ zum Clientbereich der `pParentWnd`.  
  
 `pParentWnd`  
 Gibt an, die Statusanzeige-Steuerelements übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL.**  
  
 `nID`  
 Gibt das Statusanzeige-Steuerelement ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn die `CProgressCtrl` Objekt wurde erfolgreich erstellt wird; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CProgressCtrl` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor erstellt die `CProgressCtrl` Objekt, und rufen Sie anschließend **erstellen**, wodurch das Statusanzeige-Steuerelement erstellt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CProgressCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CProgressCtrl` Objekt.  
  
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
 Gibt das Statusanzeige-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Fensterstilen, die in beschriebenen [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) im Windows SDK.  
  
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
  
##  <a name="getbarcolor"></a>CProgressCtrl::GetBarColor  
 Ruft die Farbe der Statusanzeige für den aktuellen Statusanzeige-Steuerelements ab.  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe des aktuellen Statusanzeige, dargestellt als eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert oder `CLR_DEFAULT` Indikator Leiste Statusfarbe ist die Standardfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getbkcolor"></a>CProgressCtrl::GetBkColor  
 Ruft die Hintergrundfarbe des aktuellen Statusanzeige ab.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Hintergrundfarbe des aktuellen Statusanzeige, dargestellt als eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getpos"></a>CProgressCtrl::GetPos  
 Ruft die aktuelle Position der Statusanzeige ab.  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position der Statusanzeige-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Position der Statusanzeige-Steuerelement ist nicht der physische Speicherort auf dem Bildschirm, aber stattdessen wird zwischen der oberen und unteren Bereich angegeben [SetRange](#setrange).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="getrange"></a>CProgressCtrl::GetRange  
 Ruft den aktuellen unteren und oberen Grenzen oder ein Bereich, der das Statusanzeige-Steuerelement.  
  
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
 Diese Funktion kopiert die Werte der oberen und unteren Grenzen in der ganzen Zahlen verweist `nLower` und `nUpper`zugeordnet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="getstate"></a>CProgressCtrl:: GetState  
 Ruft den Zustand des aktuellen Statusanzeige-Steuerelements ab.  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status von der aktuellen Statusanzeige-Steuerelements, das einen der folgenden Werte ist:  
  
|Wert|Zustand|  
|-----------|-----------|  
|`PBST_NORMAL`|In Bearbeitung|  
|`PBST_ERROR`|Fehler|  
|`PBST_PAUSED`|Paused|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft den Status des aktuellen Statusanzeige-Steuerelements ab.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="getstep"></a>CProgressCtrl::GetStep  
 Ruft die Schrittweite für die Statusanzeige des aktuellen Statusanzeige-Steuerelements ab.  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Schrittweite der Statusanzeige.  
  
### <a name="remarks"></a>Hinweise  
 Die Schrittweite ist der Wert, einen Aufruf von [CProgressCtrl::StepIt](#stepit) erhöht die aktuelle Position der Statusanzeige.  
  
 Diese Methode sendet die [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft die Schrittweite von der aktuellen Statusanzeige-Steuerelements ab.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="offsetpos"></a>CProgressCtrl::OffsetPos  
 Verschiebt die Statusanzeige der aktuellen Position des Steuerelements durch das Inkrement gemäß `nPos` und zeichnet die Leiste, um die neue Position wiedergegeben.  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Betrag, um die Position zu wechseln.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Position der Statusanzeige-Steuerelements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="setbarcolor"></a>CProgressCtrl::SetBarColor  
 Legt die Farbe der Statusanzeige in der aktuellen Statusanzeige-Steuerelements fest.  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `clrBar`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der angibt, die neue ausgewählte Farbe von der Statusanzeige. Geben Sie `CLR_DEFAULT` , dazu führen, dass die Statusanzeige auf ihre Standardfarbe verwenden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Farbe von der Statusanzeige, dargestellt als eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert oder `CLR_DEFAULT` ist die Farbe von der Statusanzeige die Standardfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Die `SetBarColor` Methode legt die Statusanzeige Farbe nur, wenn eine [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] [Design](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx) ist nicht aktiv.  
  
 Diese Methode sendet die [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ändert sich die Farbe der Statusanzeige auf Rot, Grün, Blau oder die Standardeinstellung.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="setbkcolor"></a>CProgressCtrl::SetBkColor  
 Legt die Hintergrundfarbe für die Statusanzeige fest.  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Parameter  
 `clrNew`  
 Ein **COLORREF** Wert, der die neue Hintergrundfarbe angibt. Geben Sie die `CLR_DEFAULT` die Standardhintergrundfarbe für die Statusanzeige zu verwendende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der angibt, der vorherige Hintergrundfarbe oder **CLR_DEFAULT** ist die Farbe des Hintergrunds die Standardfarbe.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="setmarquee"></a>CProgressCtrl::SetMarquee  
 Aktiviert die Laufschrift-Modus aktiviert oder deaktiviert für den aktuellen Statusanzeige-Steuerelements.  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `fMarqueeMode`|`true`Um Laufschrift Modus aktivieren, oder `false` Laufschrift Modus deaktivieren.|  
|[in] `nInterval`|Zeit in Millisekunden zwischen den Updates für die Animation.|  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt immer `true` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Laufschrift-Modus aktiviert ist, die Statusanzeige animiert wird und scrollt wie eine Anmeldung eines Auswahlbereichs Theater.  
  
 Diese Methode sendet die [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird gestartet und beendet die Laufschrift Animation.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="setpos"></a>CProgressCtrl::SetPos  
 Legt den Status Balken der aktuellen Position des Steuerelements entsprechend den Angaben von `nPos` und zeichnet die Leiste, um die neue Position wiedergegeben.  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Neue Position der Statusanzeige-Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Position der Statusanzeige-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Position der Statusanzeige-Steuerelement ist nicht der physische Speicherort auf dem Bildschirm, aber stattdessen wird zwischen der oberen und unteren Bereich angegeben [SetRange](#setrange).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CProgressCtrl::SetRange  
 Legt den oberen und unteren Grenzen der Statusanzeige Bereichs des Steuerelements und zeichnet die Leiste entsprechend der neuen Bereiche.  
  
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
 Gibt die Untergrenze des Bereichs (die Standardeinstellung ist 0 (null)).  
  
 `nUpper`  
 Gibt die obere Grenze des Bereichs (die Standardeinstellung ist 100).  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion `SetRange32` legt die 32-Bit-Bereich für das Statussteuerelement fest.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
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
 Diese Methode sendet die [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird der Status des aktuellen Statusanzeige-Steuerelements auf angehalten oder In Bearbeitung festgelegt.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="setstep"></a>CProgressCtrl::SetStep  
 Gibt die Schrittweite für eine Statusanzeige-Steuerelements an.  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>Parameter  
 *nStep*  
 Neue Schrittweite.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Schritt Inkrement.  
  
### <a name="remarks"></a>Hinweise  
 Die Schrittweite ist der Wert, einen Aufruf von `CProgressCtrl::StepIt` den Fortschritt erhöht die aktuelle Position.  
  
 Die Schrittweite der Standardwert ist 10.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="stepit"></a>CProgressCtrl::StepIt  
 Erhöht die aktuelle Position für eine Statusanzeige-Steuerelements durch die Schrittweite und zeichnet die Leiste, um die neue Position wiedergegeben.  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Position der Statusanzeige-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Schrittweite wird festgelegt, indem die `CProgressCtrl::SetStep` Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


