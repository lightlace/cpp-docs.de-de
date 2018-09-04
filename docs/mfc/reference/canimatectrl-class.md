---
title: CAnimateCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
dev_langs:
- C++
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e921faf20fd7c2bbac967bf73b62dd33c8220a4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688227"
---
# <a name="canimatectrl-class"></a>CAnimateCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Animationssteuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Erstellt ein `CAnimateCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|Schließt die AVI-Clips.|  
|[CAnimateCtrl::Create](#create)|Erstellt ein Animationssteuerelement und fügt sie an einer `CAnimateCtrl` Objekt.|  
|[CAnimateCtrl::CreateEx](#createex)|Erstellt eine Animationssteuerelement mit dem angegebenen erweiterten Stile für Windows und fügt sie an einer `CAnimateCtrl` Objekt.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Gibt an, ob ein Audio-Video überlappen (AVI) Videoclip wiedergegeben wird.|  
|[CAnimateCtrl::Open](#open)|Ein AVI-Videoclips aus einer Datei oder Ressource geöffnet und zeigt den ersten Frame.|  
|[CAnimateCtrl::Play](#play)|Wird die AVI-Clips ohne Sound wiedergegeben.|  
|[CAnimateCtrl::Seek](#seek)|Zeigt einen einzelnen ausgewählten Frame des AVI-Clips.|  
|[CAnimateCtrl::Stop](#stop)|Beendet die Wiedergabe des AVI-Clips.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Steuerelement (und somit die `CAnimateCtrl` Klasse) ist nur für Programme, die unter Windows 95, Windows 98 und Windows NT, Version 3.51 und höher.  
  
 Ein Animationssteuerelement ist ein rechteckiges Fenster, das einen Clip in AVI (Audio Video überlappend)-Format angezeigt, das standardmäßige Windows-Video-oder Audio-Format. Ein AVI-Clips ist eine Reihe von Bitmapbildern wie einen Film.  
  
 Animationssteuerungselemente können nur einfache AVI-Clips wiedergeben. Insbesondere müssen die Clips, die von einem Animationssteuerelement wiedergegeben werden die folgenden Anforderungen erfüllen:  
  
-   Es muss genau einen Videostream vorhanden sein und muss mindestens einen Frame.  
  
-   Es darf nur maximal zwei Datenströmen in der Datei (in der Regel der anderen Stream, falls vorhanden, ist Audiostream, obwohl das Animationssteuerelement Audioinformationen ignoriert).  
  
-   Der Clip muss nicht komprimiert oder mit RLE8-Komprimierung komprimiert werden.  
  
-   Keine palettenänderungen sind in den video Stream zulässig.  
  
 Sie können Ihre Anwendung als AVI-Ressource des AVI-Clips hinzufügen, oder können sie Ihre Anwendung als separate Datei AVI-begleitet.  
  
 Da sich der Thread ausgeführt weiterhin, während des AVI-Clips angezeigt wird, werden ein gängiges Szenario für ein Animationssteuerelement Systemaktivität während eines längeren Vorgangs anzugeben. Beispielsweise zeigt das Dialogfeld "Suchen" von Datei-Explorer verschieben Vergrößerungsglas als das System sucht nach einer Datei.  
  
 Bei der Erstellung einer `CAnimateCtrl` -Objekt in einem Dialogfeld Feld oder aus einer Ressource mit dem Dialogfeld-Editor, es wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Bei der Erstellung einer `CAnimateCtrl` Objekt innerhalb eines Zeitfensters, müssen Sie möglicherweise zerstören. Bei der Erstellung der `CAnimateCtrl` Objekt im Stapel automatisch zerstört wird. Bei der Erstellung der `CAnimateCtrl` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** für das Objekt zu zerstören. Wenn Sie eine neue Klasse von ableiten `CAnimateCtrl` und Speicher in dieser Klasse außer Kraft, die `CAnimateCtrl` Destruktor, der Zuordnungen zu verwerfen.  
  
 Weitere Informationen zur Verwendung von `CAnimateCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CAnimateCtrl](../../mfc/using-canimatectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="canimatectrl"></a>  CAnimateCtrl::CAnimateCtrl  
 Erstellt ein `CAnimateCtrl`-Objekt.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [erstellen](#create) Member-Funktion, bevor Sie alle anderen Vorgänge für das Objekt ausführen können, die Sie erstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>  CAnimateCtrl::Close  
 Schließt die AVI-Clips, die zuvor in der Animation-Steuerelement (falls vorhanden) geöffnet wurde, und entfernt sie aus dem Arbeitsspeicher.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="create"></a>  CAnimateCtrl::Create  
 Erstellt ein Animationssteuerelement und fügt sie an einer `CAnimateCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *dwStyle*  
 Gibt das Animationssteuerelement-Stil. Wenden Sie eine beliebige Kombination der Formate, die im Abschnitt "Hinweise" und der Stile von Listensteuerelementen Animation beschrieben, die in beschriebenen Windows [Stile von Listensteuerelementen Animation](/windows/desktop/Controls/animation-control-styles) im Windows SDK.  
  
 *Rect*  
 Gibt an, Position und Größe des Animationssteuerelements. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 *pParentWnd*  
 Gibt an, das Animationssteuerelement übergeordnete Fenster, in der Regel eine `CDialog`. Es darf nicht NULL sein.  
  
 *nID*  
 Gibt an, die Animationssteuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CAnimateCtrl` in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann `Create`, die das Animationssteuerelement erstellt, und fügt es der `CAnimateCtrl` Objekt.  
  
 Übernehmen Sie das folgende [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) an ein Animationssteuerelement.  
  
- WS_CHILD immer  
  
- WS_VISIBLE in der Regel  
  
- WS_DISABLED selten  
  
 Wenn Sie erweiterte Fensterstile mit dem Animationssteuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von `Create`.  
  
 Zusätzlich zu den oben aufgeführten Window-Stile können Sie eine oder mehrere der Animation Steuerelementstilen an ein Animationssteuerelement anwenden möchten. Das Windows SDK Weitere Informationen finden Sie [Stile von Listensteuerelementen Animation](/windows/desktop/Controls/animation-control-styles).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="createex"></a>  CAnimateCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet ihn dem `CAnimateCtrl` Objekt.  
  
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
 Gibt das Animationssteuerelement-Stil. Wenden Sie eine beliebige Kombination aus dem Fenster und Steuerelement animationsstile beschrieben [Stile von Listensteuerelementen Animation](/windows/desktop/Controls/animation-control-styles) im Windows SDK.  
  
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
  
##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying  
 Gibt an, ob ein Audio-Video überlappen (AVI) Videoclip wiedergegeben wird.  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein AVI-Clips wiedergegeben wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [ACM_ISPLAYING](/windows/desktop/Controls/acm-isplaying) -Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="open"></a>  CAnimateCtrl::Open  
 Rufen Sie diese Funktion zum Öffnen des AVI-Clips und zum Anzeigen der erste Frame.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszFileName*  
 Ein `CString` Objekt oder ein Zeiger auf eine auf Null endende Zeichenfolge, die entweder den Namen der AVI-Datei oder der Name einer AVI-Ressource enthält. Wenn dieser Parameter NULL ist, schließt das System des AVI-Clips, die zuvor für das Animationssteuerelement geöffnet wurde, falls vorhanden.  
  
 *nID*  
 Der Ressourcenbezeichner des AVI. Wenn dieser Parameter NULL ist, schließt das System des AVI-Clips, die zuvor für das Animationssteuerelement geöffnet wurde, falls vorhanden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die AVI-Ressource wird aus dem Modul geladen, die das Animationssteuerelement erstellt.  
  
 `Open` Sound wird in einem AVI-Clips nicht unterstützt werden. Sie können nur die automatische AVI-Clips öffnen.  
  
 Wenn das Animationssteuerelement verfügt die `ACS_AUTOPLAY` Format, das Animationssteuerelement wird automatisch gestartet Wiedergabe des Clips, sofort, nachdem es geöffnet wird. Diese Funktion bleibt weiterhin zur Wiedergabe des Clips im Hintergrund, während der Thread ausgeführt weiterhin. Abschluss des Clips wiedergeben, es wird automatisch wiederholt.  
  
 Wenn das Animationssteuerelement verfügt die `ACS_CENTER` Stil des AVI-Clips wird im Steuerelement zentriert und die Größe des Steuerelements wird nicht geändert. Wenn das Animationssteuerelement keinen der `ACS_CENTER` Format, das Steuerelement wird beim Öffnen des AVI-Clips auf die Größe der Bilder in AVI-Clips geändert werden. Die Position der oberen linken Ecke des Steuerelements ändert sich nicht, nur die Größe des Steuerelements.  
  
 Wenn das Animationssteuerelement verfügt die `ACS_TRANSPARENT` Stil, der erste Frame wird mit einem transparenten Hintergrund gezeichnet werden und nicht als Farbe des Hintergrunds angegeben wird, der Animation-Clips.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="play"></a>  CAnimateCtrl::Play  
 Rufen Sie diese Funktion zum Wiedergeben eines AVI-Videoclips in einem Animationssteuerelement.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Parameter  
 *nWenn*  
 Nullbasierte Index des Frames, in dem Wiedergabe beginnt. Wert muss kleiner als 65.536 sein. Der Wert 0 bedeutet, dass mit den ersten Frame des AVI-Clips zu beginnen.  
  
 *NUM*  
 Nullbasierte Index des Frames, in denen Wiedergabe beendet. Wert muss kleiner als 65.536 sein. Der Wert von - bedeutet 1 mit dem letzten Frame des AVI-Clips enden.  
  
 *nRep*  
 Anzahl von Wiederholungen des AVI-Clips wiedergegeben. Der Wert von - bedeutet 1 der Datei unbegrenzt wiederzugeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Animationssteuerelement Wiedergeben des Clips im Hintergrund, während der Thread ausgeführt weiterhin. Wenn das Animationssteuerelement verfügt `ACS_TRANSPARENT` Stil des AVI-Clips wird wiedergegeben werden über einen transparenten Hintergrund statt über die Farbe des Hintergrunds der Animation-Clips angegeben.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="seek"></a>  CAnimateCtrl::Seek  
 Rufen Sie diese Funktion, um ein einzelnes Frame Ihres AVI-Clips statisch angezeigt werden sollen.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Parameter  
 *NUM*  
 Nullbasierte Index des anzuzeigenden Rahmens. Wert muss kleiner als 65.536 sein. Der Wert 0 bedeutet, dass den ersten Frame in der AVI-Clips angezeigt. Der Wert-1 bedeutet, dass den letzten Frame in der AVI-Clips angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Animationssteuerelement verfügt `ACS_TRANSPARENT` Stil des AVI-Clips wird mit einem transparenten Hintergrund gezeichnet werden und nicht als Farbe des Hintergrunds angegeben wird, der Animation-Clips.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="stop"></a>  CAnimateCtrl::Stop  
 Mit dieser Funktion können Sie beenden das Abspielen eines AVI-Videoclips in einem Animationssteuerelement.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](message-map-macros-mfc.md#on_control)

