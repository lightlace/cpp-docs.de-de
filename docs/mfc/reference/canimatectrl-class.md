---
title: CAnimateCtrl-Klasse | Microsoft Docs
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
ms.openlocfilehash: c1032ffac46af6370c45f4bcb2c251ddae73ce69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356395"
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
|[CAnimateCtrl::Close](#close)|Schließt die AVI-Videoclips an.|  
|[CAnimateCtrl::Create](#create)|Erstellt eine Animationssteuerelement, und fügt es einer `CAnimateCtrl` Objekt.|  
|[CAnimateCtrl::CreateEx](#createex)|Erstellt eine Animationssteuerelement mit der angegebenen erweiterten Fensterstile und fügt es einer `CAnimateCtrl` Objekt.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Gibt an, ob ein Audio/Video-Interleaved (AVI) abgespielt wird.|  
|[CAnimateCtrl::Open](#open)|Öffnet ein AVI-Videoclips aus einer Datei oder Ressource und den ersten Frame angezeigt.|  
|[CAnimateCtrl::Play](#play)|Wird die AVI-Videoclips ohne Sound wiedergegeben.|  
|[CAnimateCtrl::Seek](#seek)|Zeigt die einzelnen ausgewählten Frames von AVI-Videoclips an.|  
|[CAnimateCtrl::Stop](#stop)|Beendet die Wiedergabe von AVI-Videoclips.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Steuerelement (und somit die `CAnimateCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95, Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Ein Animationssteuerelements ist ein rechteckiges Fenster, in dem einen Clip im AVI (Audio / Video Interleaved)-Format angezeigt – Windows Video-oder Audio-Standardformat. Ein AVI-Videoclips besteht aus einer Reihe von Bitmapframes, z. B. einen Film.  
  
 Animationssteuerungselemente können nur einfache AVI-Clips wiedergeben. Insbesondere müssen die Clips von eines Animationssteuerelements wiedergegeben werden die folgenden Anforderungen erfüllen:  
  
-   Es muss genau ein Videostream und muss mindestens einen Frame.  
  
-   Es kann höchstens zwei Datenströmen in der Datei (in der Regel anderen Datenstrom vorhanden ist, ist einen Audiostream, obwohl die Animationssteuerelements Informationen ignoriert).  
  
-   Clip muss nicht komprimiert oder mit RLE8-Komprimierung komprimiert werden.  
  
-   Keine Palette Änderungen sind in den Videostream zulässig.  
  
 Sie können AVI-Videoclips an Ihre Anwendung als AVI-Ressource hinzufügen oder können sie die Anwendung als separate AVI-Datei begleitet.  
  
 Da der Thread ausgeführt weiterhin, während die AVI-Videoclips angezeigt wird, wird eine gemeinsame Verwendung eines Animationssteuerelements Systemaktivität während eines längeren Vorgangs angegeben. Beispielsweise zeigt das Dialogfeld Suchen von Datei-Explorer gleitenden Vergrößerungsglas als durchsucht eine Datei.  
  
 Wenn Sie erstellen ein `CAnimateCtrl` -Objekt in einem Dialogfeld Feld oder aus einer Ressource mit dem Dialog-Editor, es werden automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CAnimateCtrl` Objekt innerhalb eines Fensters müssen sie zerstört werden. Bei Erstellung der `CAnimateCtrl` Objekt im Stapel befindet, automatisch zerstört wird. Bei Erstellung der `CAnimateCtrl` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das sie zerstört werden. Wenn Sie eine neue Klasse von ableiten `CAnimateCtrl` und Speicher in dieser Klasse, überschreiben die `CAnimateCtrl` Destruktor, der die Zuordnungen zu verwerfen.  
  
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
 Rufen Sie die [erstellen](#create) Memberfunktion, bevor Sie alle anderen Vorgänge für das Objekt ausführen können, die Sie erstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>  CAnimateCtrl::Close  
 Schließt die AVI-Videoclips an, die zuvor in der Animationssteuerelements (sofern vorhanden) geöffnet wurde, und es aus dem Arbeitsspeicher entfernt.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="create"></a>  CAnimateCtrl::Create  
 Erstellt eine Animationssteuerelement, und fügt es einer `CAnimateCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Format der Animationssteuerelements an. Wenden Sie eine beliebige Kombination der Formate beschrieben im Abschnitt "Hinweise" und der Steuerelementtypen für die Animation in beschriebenen Windows [Steuerelementtypen für die Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886) im Windows SDK.  
  
 `rect`  
 Gibt an, die Animationssteuerelements Position und Größe. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt an, die Animationssteuerelements übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL.**  
  
 `nID`  
 Gibt an, die Animationssteuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CAnimateCtrl` in zwei Schritten. Zunächst den Konstruktor, und rufen dann **erstellen**, die die Animation-Steuerelement erstellt, und fügt es der `CAnimateCtrl` Objekt.  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) , eines Animationssteuerelements.  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
 Wenn Sie die erweiterten Fensterstile mit Ihrem Animationssteuerelements verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
 Zusätzlich zu den oben aufgeführten Fensterstile können Sie eine oder mehrere der Steuerelementtypen für die Animation auf eines Animationssteuerelements anwenden möchten. Das Windows SDK für Weitere Informationen finden Sie [Steuerelementtypen für die Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="createex"></a>  CAnimateCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CAnimateCtrl` Objekt.  
  
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
 Gibt das Format der Animationssteuerelements an. Eine beliebige Kombination aus dem Fenster anwenden und Steuerelementtypen für die Animation beschrieben [Steuerelementtypen für die Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886) im Windows SDK.  
  
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
  
##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying  
 Gibt an, ob ein Audio/Video-Interleaved (AVI) abgespielt wird.  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Wiedergabe eines AVI-Videoclips; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="open"></a>  CAnimateCtrl::Open  
 Mit dieser Funktion wird zum Öffnen eines AVI-Videoclips und seine erste Frame angezeigt.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Ein `CString` Objekt oder ein Zeiger auf eine auf Null endende Zeichenfolge, die entweder den Namen der AVI-Datei oder der Name einer AVI-Ressource enthält. Wenn dieser Parameter ist **NULL**, das System schließt die AVI-Videoclips an, die zuvor für das Animationssteuerelement geöffnet wurde, falls vorhanden.  
  
 `nID`  
 Der Ressourcenbezeichner des AVI. Wenn dieser Parameter ist **NULL**, das System schließt die AVI-Videoclips an, die zuvor für das Animationssteuerelement geöffnet wurde, falls vorhanden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die AVI-Ressource wird aus dem Modul geladen, die die Animation-Steuerelement erstellt.  
  
 **Öffnen Sie** Sound in eines AVI-Videoclips; nicht unterstützt, können Sie nur automatische AVI-Clips öffnen.  
  
 Wenn das Animationssteuerelement besitzt die `ACS_AUTOPLAY` Stil, die Animationssteuerelements Wiedergabe wird automatisch gestartet Clip sofort, nachdem er geöffnet wird. Es werden weiterhin wiedergegeben Clip im Hintergrund, während Ihr Thread ausgeführt weiterhin. Abschluss der Clip wiedergeben, es wird automatisch wiederholt.  
  
 Wenn das Animationssteuerelement besitzt die `ACS_CENTER` Stil, AVI-Videoclips wird das Bild zentriert im Steuerelement, und die Größe des Steuerelements wird nicht geändert. Wenn das Animationssteuerelement keinen der `ACS_CENTER` Format, das Steuerelement wird geändert werden, wenn die AVI-Videoclips an die Größe der Bilder in AVI-Videoclips geöffnet wird. Die Position der oberen linken Ecke des Steuerelements wird nur die Größe des Steuerelements nicht geändert.  
  
 Wenn das Animationssteuerelement verfügt die `ACS_TRANSPARENT` Formatvorlage, der erste Frame wird mit einem transparenten Hintergrund gezeichnet werden und nicht als die Farbe des Hintergrunds angegeben wird, der Animation Clip.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="play"></a>  CAnimateCtrl::Play  
 Mit dieser Funktion wird zum Wiedergeben eines AVI-Videoclips in eines Animationssteuerelements.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Parameter  
 `nFrom`  
 Nullbasierte Index des Frames, an der Wiedergabe beginnt. Wert muss kleiner als 65.536 sein. Der Wert 0 bedeutet, dass mit der erste Frame in der AVI-Videoclips beginnen.  
  
 `nTo`  
 Nullbasierten Index des Frames, in denen Wiedergabe enden. Wert muss kleiner als 65.536 sein. Ein Wert von - bedeutet 1 mit dem letzten Frame im AVI-Videoclips enden.  
  
 *nRep*  
 Anzahl der Wiederholungen AVI-Videoclips wiedergegeben. Ein Wert von - bedeutet 1 der Datei unbegrenzt wiederzugeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Animationssteuerelements spielen Clip im Hintergrund, während Ihr Thread ausführen weiterhin. Wenn das Animationssteuerelement besitzt `ACS_TRANSPARENT` Stil AVI-Videoclips werden wiedergegeben werden mit einem transparenten Hintergrund statt in der Animation Clip angegebene Hintergrundfarbe.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="seek"></a>  CAnimateCtrl::Seek  
 Mit dieser Funktion wird einen einfacher Frame AVI-Videoclips statisch angezeigt.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Parameter  
 `nTo`  
 Nullbasierte Index des anzuzeigenden Rahmens. Wert muss kleiner als 65.536 sein. Der Wert 0 bedeutet, dass den ersten Frame in der AVI-Videoclips angezeigt. Der Wert-1 bedeutet, dass den letzten Frame in der AVI-Videoclips angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Animationssteuerelement verfügt `ACS_TRANSPARENT` Stil AVI-Videoclips wird mit einem transparenten Hintergrund gezeichnet werden und nicht als die Farbe des Hintergrunds angegeben wird, der Animation Clip.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="stop"></a>  CAnimateCtrl::Stop  
 Mit dieser Funktion wird zum Beenden der Wiedergabe eines AVI-Videoclips in eines Animationssteuerelements.  
  
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

