---
title: CAnimateCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimateCtrl
dev_langs:
- C++
helpviewer_keywords:
- animation controls [C++], CAnimateCtrl class
- Windows common controls [C++], CAnimateCtrl class
- CAnimateCtrl class
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
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
ms.openlocfilehash: cef1d6274d5334804ee028fa296c77faf124a496
ms.lasthandoff: 02/24/2017

---
# <a name="canimatectrl-class"></a>CAnimateCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Animationssteuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Erstellt ein `CAnimateCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|Schließt den AVI-Clip.|  
|[CAnimateCtrl::Create](#create)|Erstellt ein Animationssteuerelement und fügt es ein `CAnimateCtrl` Objekt.|  
|[CAnimateCtrl::CreateEx](#createex)|Erstellt ein Animationssteuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CAnimateCtrl` Objekt.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Gibt an, ob ein Audio-Video Interleaved (AVI) abgespielt wird.|  
|[CAnimateCtrl::Open](#open)|Öffnet einen AVI-Clip aus einer Datei oder Ressource, und zeigt den ersten Frame.|  
|[CAnimateCtrl::Play](#play)|Gibt den AVI-Clip ohne Ton wieder.|  
|[CAnimateCtrl::Seek](#seek)|Zeigt einen einzelnen ausgewählten Frame des Clips AVI.|  
|[CAnimateCtrl::Stop](#stop)|Beendet die Wiedergabe des AVI-Clips.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Steuerelement (und somit die `CAnimateCtrl` Klasse) ist nur für Programme, die unter Windows 95, Windows 98 und Windows NT, Version 3.51 und höher.  
  
 Ein Animationssteuerelement ist ein rechteckiges Fenster, einen Clip im AVI (Audio Video Interleaved)-Format angezeigt – Windows Video-oder Audio-Standardformat. Ein AVI-Clip besteht aus einer Reihe von Bitmapbildern wie ein Film.  
  
 Animations-Steuerelemente können nur einfache AVI-Clips wiedergeben. Insbesondere müssen die Clips, die von einem Animationssteuerelement wiedergegeben werden die folgenden Anforderungen erfüllen:  
  
-   Muss genau einen Videodatenstrom vorhanden sein, und es müssen mindestens einen Frame.  
  
-   Es darf höchstens zwei Datenströmen in der Datei (in der Regel die anderen Datenstrom ist ggf. einen Audiostream zwar das Animationssteuerelement Audiodaten ignoriert).  
  
-   Der Clip muss nicht komprimiert oder mit RLE8-Komprimierung komprimiert werden.  
  
-   Keine Palette Änderungen sind in den Videodatenstrom zulässig.  
  
 Sie können den AVI-Clip für Ihre Anwendung als AVI-Ressource hinzufügen, oder können sie Ihre Anwendung als eine separate AVI-Datei begleiten.  
  
 Da der Thread wird ausgeführt weiterhin, während der AVI-Clip angezeigt wird, ist ein häufiges Anwendungsbeispiel für Animationssteuerelements Systemaktivität während eines längeren Vorgangs angegeben. Beispielsweise zeigt das Dialogfeld Suchen, der Datei-Explorer gleitenden Vergrößerungsglas als durchsucht eine Datei.  
  
 Wenn Sie erstellen ein `CAnimateCtrl` -Objekt einem Dialog Feld oder aus einer Ressource mit dem Dialog-Editor, es werden automatisch gelöscht, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CAnimateCtrl` -Objekt innerhalb eines Fensters müssen Sie möglicherweise zerstört. Bei der Erstellung der `CAnimateCtrl` Objekt auf dem Stapel automatisch zerstört wird. Bei der Erstellung der `CAnimateCtrl` Objekt auf dem Heap mithilfe der **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört. Wenn Sie eine neue Klasse von ableiten `CAnimateCtrl` Arbeitsspeicher in der Klasse, und überschreiben die `CAnimateCtrl` Destruktor, um die Zuordnung zu entfernen.  
  
 Weitere Informationen zur Verwendung von `CAnimateCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CAnimateCtrl](../../mfc/using-canimatectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-namecanimatectrla--canimatectrlcanimatectrl"></a><a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl  
 Erstellt ein `CAnimateCtrl`-Objekt.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen aufrufen, der [erstellen](#create) Memberfunktion, bevor Sie alle anderen Operationen für das Objekt ausführen können, die Sie erstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#56;](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="a-nameclosea--canimatectrlclose"></a><a name="close"></a>CAnimateCtrl::Close  
 Schließt den AVI-Clip an, der zuvor in das Animationssteuerelement (sofern vorhanden) geöffnet wurde und aus dem Arbeitsspeicher entfernt.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-namecreatea--canimatectrlcreate"></a><a name="create"></a>CAnimateCtrl::Create  
 Erstellt ein Animationssteuerelement und fügt es ein `CAnimateCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Animationssteuerelement-Stil. Wenden Sie eine beliebige Kombination der Formate beschrieben, die im Abschnitt "Hinweise" und der Steuerelementtypen für die Animation in beschriebenen Windows [Steuerelementtypen für die Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Gibt des Animationssteuerelements Position und Größe. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Animationssteuerelement übergeordneten Fensters, in der Regel eine `CDialog`. Er darf nicht sein **NULL.**  
  
 `nID`  
 Gibt das Animationssteuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie eine `CAnimateCtrl` in zwei Schritten. Zuerst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, wodurch erstellt das Animationssteuerelement und fügt es der `CAnimateCtrl` Objekt.  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) eine Animation steuern.  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
 Wenn Sie erweiterte Fensterstile mit das Animationssteuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
 Zusätzlich zu den oben aufgeführten Fensterstile empfiehlt es sich möglicherweise eine oder mehrere der Steuerelementtypen für die Animation eines Animationssteuerelements zuweisen. Finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu [Steuerelementtypen für die Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-namecreateexa--canimatectrlcreateex"></a><a name="createex"></a>CAnimateCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CAnimateCtrl` Objekt.  
  
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
 Gibt das Animationssteuerelement-Stil. Wenden Sie eine beliebige Kombination aus dem Fenster und Steuerelementtypen für die Animation in beschriebenen [Steuerelementtypen für die Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="a-nameisplayinga--canimatectrlisplaying"></a><a name="isplaying"></a>CAnimateCtrl::IsPlaying  
 Gibt an, ob ein Audio-Video Interleaved (AVI) abgespielt wird.  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn ein AVI-Clip wiedergegeben wird; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameopena--canimatectrlopen"></a><a name="open"></a>CAnimateCtrl::Open  
 Rufen Sie diese Funktion, um ein AVI-Clip öffnen und der erste Frame angezeigt.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Ein `CString` Objekt oder einen Zeiger auf eine auf Null endende Zeichenfolge, die entweder den Namen der AVI-Datei oder der Name einer AVI-Ressource enthält. Wenn dieser Parameter **NULL**, das System schließt den AVI-Clip, die zuvor für das Animationssteuerelement geöffnet wurde, falls vorhanden.  
  
 `nID`  
 Der Ressourcenbezeichner AVI. Wenn dieser Parameter **NULL**, das System schließt den AVI-Clip, die zuvor für das Animationssteuerelement geöffnet wurde, falls vorhanden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Die AVI-Ressource wird aus dem Modul geladen, die das Animationssteuerelement erstellt.  
  
 **Öffnen Sie** Sound in einen AVI-Clip; nicht unterstützt, können Sie nur die automatische AVI-Clips öffnen.  
  
 Verfügt das Animationssteuerelement das `ACS_AUTOPLAY` Format, das Animationssteuerelement Wiedergabe wird automatisch gestartet Clips sofort, nachdem er geöffnet wird. Es wird weiterhin geben Sie den Clip im Hintergrund, während der Thread wird ausgeführt weiterhin. Abschluss des Clips wiedergegeben, es wird automatisch wiederholt.  
  
 Verfügt das Animationssteuerelement das `ACS_CENTER` -Stil der AVI-Clip wird im Steuerelement zentriert und die Größe des Steuerelements wird nicht geändert. Das Animationssteuerelement keinen der `ACS_CENTER` Format des Steuerelements geändert wird, wenn die AVI-Clip auf die Größe der Bilder in den AVI-Clip geöffnet wird. Die Position der oberen linken Ecke des Steuerelements ändert sich, nur die Größe des Steuerelements.  
  
 Verfügt das Animationssteuerelement das `ACS_TRANSPARENT` Format, das erste Bild mit transparentem Hintergrund gezeichnet werden und nicht die Hintergrundfarbe im angegebenen Animation-Clips.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-nameplaya--canimatectrlplay"></a><a name="play"></a>CAnimateCtrl::Play  
 Rufen Sie diese Funktion, um ein AVI-Clip in einem Animationssteuerelement wiederzugeben.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Parameter  
 `nFrom`  
 Nullbasierte Index des Frames, in dem Wiedergabe beginnt. Wert muss kleiner als 65.536 sein. Der Wert 0 bedeutet, dass mit den ersten Frame im AVI-Clip zu beginnen.  
  
 `nTo`  
 Nullbasierter Index des Bilds, in denen Wiedergabe enden. Wert muss kleiner als 65.536 sein. Ein Wert von – 1 bedeutet endet mit dem letzten Frame in den AVI-Clip.  
  
 *nRep*  
 Anzahl den AVI-Clip wiedergegeben. Ein Wert von – 1 bedeutet unbegrenzt die Datei wiederzugeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Das Animationssteuerelement spielen Clips im Hintergrund, während der Thread wird ausgeführt weiterhin. Verfügt das Animationssteuerelement `ACS_TRANSPARENT` Stil, der AVI-Clip werden wiedergegeben werden über einen transparenten Hintergrund statt über die Hintergrundfarbe des Animation-Clips angegeben.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-nameseeka--canimatectrlseek"></a><a name="seek"></a>CAnimateCtrl::Seek  
 Rufen Sie diese Funktion, um ein einzelnes Bild der AVI-Clip statisch angezeigt werden sollen.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Parameter  
 `nTo`  
 Nullbasierte Index des Bilds angezeigt. Wert muss kleiner als 65.536 sein. Der Wert 0 bedeutet, dass das erste Bild in den AVI-Clip angezeigt. Ein Wert von-1 bedeutet, dass der letzte angezeigte Frame im Clip AVI.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Verfügt das Animationssteuerelement `ACS_TRANSPARENT` Format, der AVI-Clip mit einem transparenten Hintergrund gezeichnet werden und nicht die Hintergrundfarbe angegeben, der Animation-Clips.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="a-namestopa--canimatectrlstop"></a><a name="stop"></a>CAnimateCtrl::Stop  
 Rufen Sie diese Funktion, um ein AVI-Clip in einer Animation-Steuerelement Wiedergabe beendet.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](http://msdn.microsoft.com/library/2cb7ebdf-296b-4606-b191-3449835003db)


