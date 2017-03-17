---
title: CControlBar-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
dev_langs:
- C++
helpviewer_keywords:
- CControlBar class
- OLE resize bars
- OLE resize bars, base class
- dialog bars, base class
- toolbars [C++], base class
- control bars [C++], base class
- status bars, base class
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9720c4c11656834923c0e42a2017d51543c08f53
ms.lasthandoff: 02/24/2017

---
# <a name="ccontrolbar-class"></a>CControlBar Class
Die Basisklasse für die steuerleisteklassen [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), und [COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|Erstellt ein `CControlBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Gibt die Größe einer dynamischen Steuerleiste als ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Gibt die Größe der Steuerleiste als ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|Gibt die aktuellen Maße des Steuerleistenbereichs, einschließlich der Rahmen, zurück.|  
|[CControlBar::DoPaint](#dopaint)|Rendert die Rahmen und das Ziehelement der Steuerleiste.|  
|[CControlBar::DrawBorders](#drawborders)|Rendert die Rahmen der Steuerleiste.|  
|[CControlBar::DrawGripper](#drawgripper)|Rendert das Ziehelement der Steuerleiste.|  
|[CControlBar:: EnableDocking](#enabledocking)|Ermöglicht das Andocken bzw. eine unverankerte Steuerleiste.|  
|[CControlBar::GetBarStyle](#getbarstyle)|Ruft die Formatvorlagen der Steuerleiste ab.|  
|[CControlBar::GetBorders](#getborders)|Ruft die Rahmenwerte der Steuerleiste ab.|  
|[CControlBar::GetCount](#getcount)|Gibt die Anzahl der nicht - `HWND` Elemente in der Steuerleiste.|  
|[CControlBar::GetDockingFrame](#getdockingframe)|Gibt einen Zeiger auf den Frame zurück, an den eine Steuerleiste angedockt ist.|  
|[CControlBar::IsFloating](#isfloating)|Gibt einen Wert ungleich&0; (null) zurück, wenn die fragliche Steuerleiste unverankert ist.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Ruft die Befehlshandler der Benutzeroberfläche ab.|  
|[CControlBar::SetBarStyle](#setbarstyle)|Ändert die Formatvorlagen der Steuerleiste.|  
|[CControlBar::SetBorders](#setborders)|Legt die Rahmenwerte der Steuerleiste fest.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Ändert den direkten Besitzer einer Steuerleiste.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Wenn der Wert ungleich&0; (null) ist, wird das `CControlBar`-Objekt gelöscht, sobald die Windows-Steuerleiste beschädigt wird.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Der direkte Besitzer der Steuerleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Steuerleiste ist ein Fenster, das normalerweise am linken oder rechten Rand eines Rahmenfensters ausgerichtet wird. Er enthält möglicherweise untergeordnete Elemente, die entweder `HWND`- basierte Steuerelemente, d. h. Windows, generieren und reagieren auf Windows-Meldungen oder nicht - `HWND`-Basis-Elementen, die sind keine Fenster und Anwendungscode oder Frameworkcode werden verwaltet. Listenfelder und Bearbeitungssteuerelemente sind Beispiele für `HWND`--basierte; Statusleistenbereiche und Schaltflächen sind Beispiele für nicht - `HWND`-Steuerelemente.  
  
 Bei Steuerleistenfenstern handelt es sich normalerweise um untergeordnete Fenster eines übergeordneten Rahmenfensters, und es sind normalerweise nebengeordnete Elemente der Clientansicht oder des MDI-Clients des Rahmenfensters. Ein `CControlBar`-Objekt verwendet zum eigenen Positionieren Informationen über das Clientrechteck des übergeordneten Fensters. Dem übergeordneten Fenster wird dann die Menge des Speicherplatzes im Clientbereich des übergeordneten Fensters mitgeteilt, die unzugeordnet bleibt.  
  
 Weitere Informationen zu `CControlBar` finden Sie unter:  
  
- [Steuerleisten](../../mfc/control-bars.md)  
  
- [Technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
-   Knowledge Base-Artikel Q242577: PRB: Update-Befehlshandler für Benutzeroberflächen funktionieren für das an ein Dialogfeld angefügte Menü nicht mehr  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout  
 Das Framework ruft diese Member-Funktion, um die Dimensionen der eine dynamische Werkzeugleiste zu berechnen.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>Parameter  
 `nLength`  
 Der angeforderte Dimension der Steuerleiste, horizontal oder vertikal, je nach `dwMode`.  
  
 `nMode`  
 Die folgenden vordefinierten Flags werden verwendet, um die Höhe und Breite der dynamischen Steuerleiste zu bestimmen. Verwenden Sie den Operator bitweises OR (|), der Flags.  
  
|Layout-Modus-flags|Bedeutung|  
|-----------------------|-------------------|  
|`LM_STRETCH`|Gibt an, ob die Steuerleiste soll, um die Größe des Rahmens gestreckt werden. Legt fest, ob die Leiste keine andockleiste (nicht verfügbar für andockbare) wird. Nicht festgelegt, wenn die Leiste angedockt oder unverankert ist (für andockbare verfügbar). Wenn festgelegt, `LM_STRETCH` ignoriert `nLength` und gibt Sie Dimensionen auf Grundlage der `LM_HORZ` Zustand. `LM_STRETCH`funktioniert ähnlich wie die `bStretch` in verwendeten Parameter [CalcFixedLayout](#calcfixedlayout); finden Sie weitere Informationen über die Beziehung zwischen Strecken und Ausrichtung, Member-Funktion.|  
|`LM_HORZ`|Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Legen Sie die Leiste horizontal ausgerichtet ist, und wenn sie vertikal ausgerichtet ist, wird nicht festgelegt. `LM_HORZ`funktioniert ähnlich wie die `bHorz` in verwendeten Parameter [CalcFixedLayout](#calcfixedlayout); finden Sie weitere Informationen über die Beziehung zwischen Strecken und Ausrichtung, Member-Funktion.|  
|**LM_MRUWIDTH**|Dynamische Breite zuletzt verwendete. Ignoriert `nLength` Parameter und verwendet die gespeicherte zuletzt verwendete Breite.|  
|`LM_HORZDOCK`|Horizontal angedockt Dimensionen. Ignoriert `nLength` Parameter und gibt die dynamische Größe mit der größten Breite.|  
|`LM_VERTDOCK`|Vertikal angedockt Dimensionen. Ignoriert `nLength` Parameter und gibt die dynamische Größe durch die Höhe des größten.|  
|`LM_LENGTHY`|Wenn `nLength` gibt die Höhe (Y-Richtung) anstelle von Breite an.|  
|`LM_COMMIT`|Setzt **LM_MRUWIDTH** aktuelle Breite der Steuerleiste unverankert.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Steuerleiste Größe, in Pixel, der eine [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um Ihre eigenen dynamischen Layouts in Klassen bieten Sie eine von Ableitung `CControlBar`. MFC-Klassen abgeleitet `CControlBar`, wie z. B. [CToolbar](../../mfc/reference/ctoolbar-class.md), überschreiben Sie diese Memberfunktion auf, und ihre eigene Implementierung bereitstellen.  
  
##  <a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout  
 Rufen Sie diese Memberfunktion zum Berechnen der horizontalen einer Steuerleiste.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 `bStretch`  
 Gibt an, ob die Leiste auf die Größe des Rahmens gestreckt werden soll. Die `bStretch` Parameter ist ungleich NULL, wenn die Leiste keine andockleiste (nicht verfügbar für andockbare) und 0, ist wenn es angedockt oder unverankert ist (verfügbar für andockbare).  
  
 `bHorz`  
 Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die `bHorz` Parameter ist ungleich NULL, wenn die Leiste horizontal ausgerichtet ist, und 0 ist, wenn sie vertikal ausgerichtet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Steuerleiste Größe, in Pixel, der eine `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Steuerleisten, z. B. Symbolleisten können horizontal gestreckt oder vertikal um die Schaltflächen gerecht zu werden in der Steuerleiste.  
  
 Wenn `bStretch` ist **TRUE**, dehnen Sie die Dimension entlang der Ausrichtung von bereitgestellten `bHorz`. Das heißt, wenn `bHorz` ist **FALSE**, Steuerleiste vertikal gestreckt wird. Wenn `bStretch` ist **FALSE**, kein Strecken auftritt. Die folgende Tabelle zeigt die möglichen Permutationen und die resultierende Steuerleiste Stile von `bStretch` und `bHorz`.  
  
|bStretch|bHorz|Strecken|Ausrichtung|Andocken/nicht Andocken|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**"TRUE"**|**"TRUE"**|Horizontale-Dehnung|Horizontal|Nicht Andocken|  
|**"TRUE"**|**FALSE**|Dehnen von vertikalen|Vertikal ausgerichtet|Nicht Andocken|  
|**FALSE**|**"TRUE"**|Keine größenanpassung verfügbar|Horizontal|Andocken|  
|**FALSE**|**FALSE**|Keine größenanpassung verfügbar|Vertikal ausgerichtet|Andocken|  
  
##  <a name="calcinsiderect"></a>CControlBar::CalcInsideRect  
 Das Framework ruft diese Funktion, um den Clientbereich der Steuerleiste zu berechnen.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Enthält die aktuelle Größe der Steuerleiste. einschließlich der Rahmen.  
  
 `bHorz`  
 Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die `bHorz` Parameter ist ungleich NULL, wenn die Leiste horizontal ausgerichtet ist, und 0 ist, wenn sie vertikal ausgerichtet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, bevor die Steuerleiste gezeichnet wird.  
  
 Überschreiben Sie diese Funktion, um die Darstellung der Rahmen und das ziehelement der Steuerleiste anpassen.  
  
##  <a name="ccontrolbar"></a>CControlBar::CControlBar  
 Erstellt ein `CControlBar`-Objekt.  
  
```  
CControlBar();
```  
  
##  <a name="dopaint"></a>CControlBar::DoPaint  
 Aufgerufen, um die Rahmen und das ziehelement der Steuerleiste zu rendern.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Gerätekontext für das Rendern der Rahmen und das ziehelement der Steuerleiste verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um das Zeichnen der Steuerleiste Verhalten anzupassen.  
  
 Eine weitere Anpassungsmethode besteht im Überschreiben der `DrawBorders` und `DrawGripper` Funktionen und benutzerdefinierte Zeichnung Code für die Rahmen und Ziehpunkte hinzuzufügen. Da diese Methoden, die standardmäßig aufgerufen werden `DoPaint` , eine Überschreibung der `DoPaint` ist nicht erforderlich.  
  
##  <a name="drawborders"></a>CControlBar::DrawBorders  
 Aufgerufen, um die Rahmen der Steuerleiste zu rendern.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Gerätekontext für das Rendern der Rahmen der Steuerleiste verwendet werden.  
  
 `rect`  
 Ein `CRect` Objekt mit den Dimensionen der Steuerleiste.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Darstellung der Balken Steuerelementrahmen anzupassen.  
  
##  <a name="drawgripper"></a>CControlBar::DrawGripper  
 Aufgerufen, um das ziehelement der Steuerleiste zu rendern.  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Verweist auf den Gerätekontext für das Rendern der Steuerelement-Leiste Ziehpunkte verwendet werden.  
  
 `rect`  
 Ein `CRect` Objekt, das die Dimensionen des ziehelements Leiste Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Darstellung des Steuerelements Leiste ziehelements anpassen.  
  
##  <a name="enabledocking"></a>CControlBar:: EnableDocking  
 Rufen Sie diese Funktion, um eine Steuerleiste angedockt werden aktivieren.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDockStyle`  
 Gibt an, ob die Steuerleiste unterstützt Andocken und den Seiten des übergeordneten Fensters auf die Steuerleiste angedockt werden kann, wenn unterstützt. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `CBRS_ALIGN_TOP`Ermöglicht das Andocken am oberen Rand des Clientbereichs.  
  
- `CBRS_ALIGN_BOTTOM`Ermöglicht das Andocken am unteren Rand des Clientbereichs.  
  
- `CBRS_ALIGN_LEFT`Ermöglicht das Andocken auf der linken Seite des Clientbereichs.  
  
- `CBRS_ALIGN_RIGHT`Ermöglicht das Andocken auf der rechten Seite des Clientbereichs.  
  
- `CBRS_ALIGN_ANY`Ermöglicht das Andocken auf jeder Seite des Clientbereichs.  
  
- `CBRS_FLOAT_MULTI`Ermöglicht mehrere Steuerleisten, die in einer einzelnen Minirahmenfenster abgedockt werden.  
  
 Wenn 0 (d. h. keine Flags angibt), die Steuerleiste wird nicht angedockt.  
  
### <a name="remarks"></a>Hinweise  
 Die angegebenen Seiten müssen einer der Seiten zum Andocken von Rahmenfenster Ziel aktiviert entsprechen oder Steuerleiste kann nicht zu diesem Frame Fenster angedockt werden.  
  
##  <a name="getbarstyle"></a>CControlBar::GetBarStyle  
 Mit dieser Funktion können Sie ermitteln, welche **CBRS_** (Steuerelementtypen Leiste) die Einstellungen werden derzeit für die Steuerleiste festgelegt.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle **CBRS_** (Steuerelementtypen Leiste) Einstellungen für die Steuerleiste. Finden Sie unter [CControlBar::SetBarStyle](#setbarstyle) für die vollständige Liste der verfügbaren Formate.  
  
### <a name="remarks"></a>Hinweise  
 Verarbeitet keine **WS_** (Fenster Formate).  
  
##  <a name="getborders"></a>CControlBar::GetBorders  
 Gibt die aktuellen rahmenwerte der Steuerleiste zurück.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das die aktuelle Breite (in Pixel) der einzelnen Seiten des Steuerelementobjekts Balken enthält. Z. B. der Wert der `left` Member der [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Breite des linken Rahmens.  
  
##  <a name="getcount"></a>CControlBar::GetCount  
 Gibt die Anzahl der nicht - `HWND` Elemente auf der `CControlBar` Objekt.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der nicht - `HWND` Elemente auf der `CControlBar` Objekt. Diese Funktion gibt 0 für eine [CDialogBar](../../mfc/reference/cdialogbar-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Typ des Elements hängt vom abgeleiteten Objekt: Bereiche für [CStatusBar](../../mfc/reference/cstatusbar-class.md) Objekte, Schaltflächen und Trennzeichen für [CToolBar](../../mfc/reference/ctoolbar-class.md) Objekte.  
  
##  <a name="getdockingframe"></a>CControlBar::GetDockingFrame  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf das aktuelle Rahmenfenster zu erhalten, die Steuerleiste angedockt ist.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Rahmenfenster, wenn erfolgreich; andernfalls **NULL**.  
  
 Wenn die Steuerleiste angedockt einem Rahmenfenster (d. h., wenn die Steuerleiste unverankert ist), diese Funktion wird ein Zeiger auf das übergeordnete Element zurückgegeben [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu andockbaren Balken, finden Sie unter [CControlBar:: EnableDocking](#enabledocking) und [CFrameWnd:: DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
##  <a name="isfloating"></a>CControlBar::IsFloating  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Steuerleiste frei verschiebbar oder angedockt ist.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Steuerleiste unverankert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie den Status aus einer Steuerleiste angedockt, sondern frei beweglich, rufen Sie [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).  
  
##  <a name="m_bautodelete"></a>CControlBar::m_bAutoDelete  
 Wenn der Wert ungleich&0; (null) ist, wird das `CControlBar`-Objekt gelöscht, sobald die Windows-Steuerleiste beschädigt wird.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_bAutoDelete`ist eine öffentliche Variable des Typs **BOOL**.  
  
 Eine Steuerleiste Objekt ist in der Regel in einem Rahmenfenster Objekt eingebettet. In diesem Fall `m_bAutoDelete` ist 0, da das Objekt eingebettete Steuerleiste beschädigt wird, wenn das Rahmenfenster zerstört wird.  
  
 Legen Sie diese Variable auf einen Wert ungleich NULL, wenn Sie reservieren einer `CControlBar` Objekt auf dem Heap, und Sie nicht planen, rufen Sie **löschen**.  
  
##  <a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner  
 Der direkte Besitzer der Steuerleiste.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI  
 Diese Member-Funktion wird vom Framework zum Aktualisieren des Status der Symbolleiste oder Status Leiste aufgerufen.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pTarget`  
 Verweist auf das Hauptrahmenfenster der Anwendung. Dieser Zeiger wird für das Nachrichtenrouting Update verwendet.  
  
 `bDisableIfNoHndler`  
 Flag, die angibt, ob ein Steuerelement, das kein updatehandler verfügbar ist, automatisch als deaktiviert angezeigt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Um eine einzelne Schaltfläche oder einen Bereich zu aktualisieren, verwenden die `ON_UPDATE_COMMAND_UI` Makro in Ihrer Zuordnung Nachricht ein Aktualisierungshandler entsprechend festlegen. Finden Sie unter [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) für Weitere Informationen zum Verwenden dieses Makro.  
  
 `OnUpdateCmdUI`wird vom Framework aufgerufen, wenn die Anwendung im Leerlauf befindet. Das Rahmenfenster aktualisiert werden, muss ein untergeordnetes Fenster mindestens indirekt eines Rahmenfensters sichtbar sein. `OnUpdateCmdUI`ist eine erweiterte überschrieben.  
  
##  <a name="setbarstyle"></a>CControlBar::SetBarStyle  
 Mit dieser Funktion können Sie die gewünschte festgelegt **CBRS_** Stile für die Steuerleiste.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Die gewünschten Stile für die Steuerleiste. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `CBRS_ALIGN_TOP`Ermöglicht die Steuerleiste am Anfang der Clientbereich eines Rahmenfensters angedockt werden.  
  
- `CBRS_ALIGN_BOTTOM`Ermöglicht den Clientbereich eines Rahmenfensters unten angedockt werden.  
  
- `CBRS_ALIGN_LEFT`Ermöglicht die Steuerleiste an der linken Seite des Clientbereichs eines Rahmenfensters angedockt werden.  
  
- `CBRS_ALIGN_RIGHT`Ermöglicht die Steuerleiste an der rechten Seite des Clientbereichs eines Rahmenfensters angedockt werden.  
  
- `CBRS_ALIGN_ANY`Ermöglicht den Rand des Clientbereichs eines Rahmenfensters angedockt werden.  
  
- `CBRS_BORDER_TOP`Bewirkt, dass einen Rahmen am oberen Rand der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_BORDER_BOTTOM`Bewirkt, dass einen Rahmen, für den unteren Rand der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_BORDER_LEFT`Bewirkt, dass einen Rahmen auf der linken Seite der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_BORDER_RIGHT`Bewirkt, dass einen Rahmen, auf den rechten Rand der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_FLOAT_MULTI`Ermöglicht mehrere Steuerleisten, die in einer einzelnen Minirahmenfenster abgedockt werden.  
  
- `CBRS_TOOLTIPS`Bewirkt, dass QuickInfos für die Steuerleiste angezeigt werden soll.  
  
- `CBRS_FLYBY`Bewirkt, dass der Text als QuickInfo gleichzeitig aktualisiert werden.  
  
- **CBRS_GRIPPER** bewirkt, dass ein Ziehpunkt, ähnlich wie die Bänder in einer **CReBar** Objekt, das für alle gezeichnet werden `CControlBar`-abgeleiteten Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Hat keine Auswirkung auf die **WS_** (Fensterstil)-Einstellungen.  
  
##  <a name="setborders"></a>CControlBar::SetBorders  
 Rufen Sie diese Funktion, um die Größe der Steuerleiste Rand festgelegt.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 *cxLeft*  
 Die Breite (in Pixel) des linken Rands der Steuerleiste.  
  
 *cyTop*  
 Die Höhe (in Pixel) des oberen Rands der Steuerleiste.  
  
 *cxRight*  
 Die Breite (in Pixel) des rechten Rands der Steuerleiste.  
  
 *cyBottom*  
 Die Höhe (in Pixel) für die untere Rahmenlinie der Steuerleiste.  
  
 `lpRect`  
 Ein Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die aktuelle Breite (in Pixel) der Ränder des Steuerelements Balken enthält.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die oberen und unteren Rahmen der Steuerleiste auf 5 Pixel und die linken und rechten Rahmen in 2 Pixel:  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#61;](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="setinplaceowner"></a>CControlBar::SetInPlaceOwner  
 Ändert den direkten Besitzer einer Steuerleiste.  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf ein `CWnd` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Muster CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar-Klasse](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar-Klasse](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar-Klasse](../../mfc/reference/cstatusbar-class.md)   
 [CReBar-Klasse](../../mfc/reference/crebar-class.md)

