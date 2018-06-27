---
title: CControlBar-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d6eb567babdea0d747e6b684f6373403cb685c6
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956667"
---
# <a name="ccontrolbar-class"></a>CControlBar Class
Die Basisklasse für die steuerleisteklassen [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), und [ COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>Member  
  
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
|[CControlBar::IsFloating](#isfloating)|Gibt einen Wert ungleich 0 (null) zurück, wenn die fragliche Steuerleiste unverankert ist.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Ruft die Befehlshandler der Benutzeroberfläche ab.|  
|[CControlBar::SetBarStyle](#setbarstyle)|Ändert die Formatvorlagen der Steuerleiste.|  
|[CControlBar::SetBorders](#setborders)|Legt die Rahmenwerte der Steuerleiste fest.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Ändert den direkten Besitzer einer Steuerleiste.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Wenn der Wert ungleich 0 (null) ist, wird das `CControlBar`-Objekt gelöscht, sobald die Windows-Steuerleiste beschädigt wird.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Der direkte Besitzer der Steuerleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Steuerleiste ist ein Fenster, das normalerweise am linken oder rechten Rand eines Rahmenfensters ausgerichtet wird. Er enthält möglicherweise untergeordnete Elemente, die entweder `HWND`- basierte Steuerelemente, d. h. Windows, generieren und reagieren auf Windows-Meldungen oder nicht - `HWND`--basierte Elemente, die nicht Windows und vom Anwendungscode oder Frameworkcode verwaltet werden. Listenfelder und Bearbeitungssteuerelemente sind Beispiele für `HWND`--basierte; Statusleistenbereiche und Bitmapschaltflächen sind Beispiele für nicht - `HWND`-Steuerelemente.  
  
 Bei Steuerleistenfenstern handelt es sich normalerweise um untergeordnete Fenster eines übergeordneten Rahmenfensters, und es sind normalerweise nebengeordnete Elemente der Clientansicht oder des MDI-Clients des Rahmenfensters. Ein `CControlBar`-Objekt verwendet zum eigenen Positionieren Informationen über das Clientrechteck des übergeordneten Fensters. Dem übergeordneten Fenster wird dann die Menge des Speicherplatzes im Clientbereich des übergeordneten Fensters mitgeteilt, die unzugeordnet bleibt.  
  
 Weitere Informationen zu `CControlBar` finden Sie unter:  
  
- [Steuerleisten](../../mfc/control-bars.md)  
  
- [Technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
-   Knowledge Base-Artikel Q242577: PRB: Update-Befehlshandler für Benutzeroberflächen funktionieren für das an ein Dialogfeld angefügte Menü nicht mehr  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="calcdynamiclayout"></a>  CControlBar::CalcDynamicLayout  
 Das Framework ruft diese Memberfunktion, um die Dimensionen einer dynamischen Symbolleiste zu berechnen.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>Parameter  
 *nLength*  
 Die angeforderte Dimension der Steuerleiste, horizontal oder vertikal, je nach *DwMode*.  
  
 *nMode*  
 Die folgenden vordefinierten Flags werden verwendet, um die Höhe und Breite der dynamischen Steuerleiste zu bestimmen. Verwenden Sie den bitweisen OR (&#124;) Operator, um die Flags zu kombinieren.  
  
|Layout-Modus-flags|Bedeutung|  
|-----------------------|-------------------|  
|`LM_STRETCH`|Gibt an, ob die Steuerleiste soll, auf die Größe des Frames gestreckt werden. Legt fest, ob die Leiste keine andockleiste (nicht verfügbar für Andocken) ist. Nicht festgelegt, wenn die Leiste angedockt oder unverankert ist (zum Andocken verfügbar). Wenn festgelegt, `LM_STRETCH` ignoriert *nLength* und Dimensionen basierend darauf, gibt die `LM_HORZ` Zustand. `LM_STRETCH` funktioniert ähnlich wie die *bStretch* verwendeten im Parameters [CalcFixedLayout](#calcfixedlayout); finden Sie weitere Informationen über die Beziehung zwischen Strecken und die Ausrichtung dieser Memberfunktion.|  
|`LM_HORZ`|Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Festgelegt, wenn die Leiste horizontal ausgerichtet ist, und wenn es vertikal ausgerichtet ist, wird es nicht festgelegt. `LM_HORZ` funktioniert ähnlich wie die *bHorz* verwendeten im Parameters [CalcFixedLayout](#calcfixedlayout); finden Sie weitere Informationen über die Beziehung zwischen Strecken und die Ausrichtung dieser Memberfunktion.|  
|`LM_MRUWIDTH`|Dynamische Breite zuletzt verwendete. Ignoriert *nLength* Parameter und verwendet die gespeicherte zuletzt verwendete Breite.|  
|`LM_HORZDOCK`|Horizontal angedockt Dimensionen. Ignoriert *nLength* Parameter und gibt die dynamische Größe mit der größten Breite zurück.|  
|`LM_VERTDOCK`|Vertikale angedockt Dimensionen. Ignoriert *nLength* Parameter und gibt die dynamische Größe durch die Höhe des größten zurück.|  
|`LM_LENGTHY`|Legen Sie, wenn *nLength* gibt die Höhe (Y-Richtung) anstelle der Breite an.|  
|`LM_COMMIT`|Setzt `LM_MRUWIDTH` aktuelle Breite der unverankerte Steuerleiste.|  
  
### <a name="return-value"></a>Rückgabewert  
 Steuerleiste Größe, in Pixel, der eine [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eigene dynamische Layout in Klassen bieten Sie ableiten `CControlBar`. MFC-Klassen abgeleitet `CControlBar`, wie z. B. [CToolbar](../../mfc/reference/ctoolbar-class.md), überschreiben Sie diese Memberfunktion auf, und ihre eigene Implementierung bereitstellen.  
  
##  <a name="calcfixedlayout"></a>  CControlBar::CalcFixedLayout  
 Rufen Sie diese Memberfunktion, um die horizontale Größe des eine Steuerleiste zu berechnen.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 *bStretch*  
 Gibt an, ob die Leiste soll, auf die Größe des Frames gestreckt werden. Die *bStretch* Parameter ist ungleich NULL, wenn die Leiste keine andockleiste (nicht verfügbar für Andocken ist) und 0, ist wenn angedockt oder unverankert ist (zum Andocken verfügbar).  
  
 *bHorz*  
 Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die *bHorz* -Parameter ist ungleich NULL, wenn die Leiste horizontal ausgerichtet ist, und 0, ist wenn es vertikal ausgerichtet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Steuerleiste Größe, in Pixel, der eine `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Steuerleisten, z. B. Symbolleisten können horizontal oder vertikal um die Schaltflächen Rechnung zu tragen enthalten sind, in der Steuerleiste.  
  
 Wenn *bStretch* ist **"true"**, dehnen Sie die Dimension entlang der Ausrichtung von bereitgestellten *bHorz*. Das heißt, wenn *bHorz* ist **"false"**, Steuerleiste vertikal gestreckt wird. Wenn *bStretch* ist **"false"**, keine Stretch auftritt. Die folgende Tabelle zeigt die möglichen Permutationen und die resultierende Steuerleiste Stile der *bStretch* und *bHorz*.  
  
|bStretch|bHorz|Ein Strecken|Ausrichtung|Andocken/nicht Andocken|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**"TRUE"**|**"TRUE"**|Horizontale Strecken|Horizontal|Nicht Andocken|  
|**"TRUE"**|**"FALSE"**|Vertikale Strecken|Vertikal ausgerichtet.|Nicht Andocken|  
|**"FALSE"**|**"TRUE"**|Keine Strecken verfügbar|Horizontal|Andocken|  
|**"FALSE"**|**"FALSE"**|Keine Strecken verfügbar|Vertikal ausgerichtet.|Andocken|  
  
##  <a name="calcinsiderect"></a>  CControlBar::CalcInsideRect  
 Das Framework ruft diese Funktion zur Berechnung der Clientbereich der Steuerleiste.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *Rect*  
 Enthält die aktuelle Größe der Steuerleiste. einschließlich der Rahmen an.  
  
 *bHorz*  
 Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die *bHorz* -Parameter ist ungleich NULL, wenn die Leiste horizontal ausgerichtet ist, und 0, ist wenn es vertikal ausgerichtet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, bevor die Steuerleiste gezeichnet wird.  
  
 Überschreiben Sie diese Funktion zum Anpassen der Darstellung von Rahmen und Balken der ziehelement der Steuerleiste.  
  
##  <a name="ccontrolbar"></a>  CControlBar::CControlBar  
 Erstellt ein `CControlBar`-Objekt.  
  
```  
CControlBar();
```  
  
##  <a name="dopaint"></a>  CControlBar::DoPaint  
 Wird aufgerufen, durch das Framework zum Rendern der Rahmen und Balken der ziehelement der Steuerleiste.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Verweist auf den Gerätekontext für das Rendern der Rahmen und das ziehelement der Steuerleiste verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Anpassen des Verhaltens Zeichnen der Steuerleiste.  
  
 Eine weitere Anpassungsmethode ist, überschreiben die `DrawBorders` und `DrawGripper` Funktionen und Hinzufügen von benutzerdefiniertem zeichnen Code für den Rahmen und das ziehelement. Da diese Methoden, die standardmäßig aufgerufen werden `DoPaint` -Methode, eine Überschreibung der `DoPaint` ist nicht erforderlich.  
  
##  <a name="drawborders"></a>  CControlBar::DrawBorders  
 Wird aufgerufen, durch das Framework die Rahmen der Steuerleiste gerendert.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Verweist auf den Gerätekontext für das Rendern von Rahmen der Steuerleiste verwendet werden.  
  
 *Rect*  
 Ein `CRect` Objekt, das die Dimensionen der Steuerleiste enthält.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Darstellung von den Rändern des Steuerelements Leiste anzupassen.  
  
##  <a name="drawgripper"></a>  CControlBar::DrawGripper  
 Wird aufgerufen, durch das Framework das ziehelement der Steuerleiste gerendert.  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Verweist auf den Gerätekontext für das Rendern des Steuerelements Leiste ziehelements verwendet werden.  
  
 *Rect*  
 Ein `CRect` Objekt, das die Dimensionen des ziehelements Leiste Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Darstellung des Steuerelements Leiste ziehelements anpassen.  
  
##  <a name="enabledocking"></a>  CControlBar:: EnableDocking  
 Mit dieser Funktion wird zum Aktivieren einer Steuerleiste angedockt werden.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDockStyle*  
 Gibt an, ob die Steuerleiste unterstützt Andocken und den Seiten des übergeordneten Fensters auf die Steuerleiste angedockt werden kann, wenn unterstützt. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `CBRS_ALIGN_TOP` Ermöglicht das Andocken am oberen Rand des Clientbereichs.  
  
- `CBRS_ALIGN_BOTTOM` Ermöglicht das Andocken am unteren Rand des Clientbereichs.  
  
- `CBRS_ALIGN_LEFT` Ermöglicht das Andocken auf der linken Seite des Clientbereichs.  
  
- `CBRS_ALIGN_RIGHT` Ermöglicht das Andocken auf der rechten Seite des Clientbereichs.  
  
- `CBRS_ALIGN_ANY` Ermöglicht das Andocken auf jeder Seite des Clientbereichs.  
  
- `CBRS_FLOAT_MULTI` Ermöglicht es mehreren Steuerleisten, die in einer einzelnen Minirahmenfenster umfließt werden.  
  
 Wenn 0 (d. h., der angibt, keine Flags), die Steuerleiste wird nicht angedockt.  
  
### <a name="remarks"></a>Hinweise  
 Die angegebenen Seiten übereinstimmen eine der Seiten, die für die in der Ziel-Rahmenfenster Andocken aktiviert, oder die Steuerleiste kann nicht auf dieses Frame-Fensters angedockt werden.  
  
##  <a name="getbarstyle"></a>  CControlBar::GetBarStyle  
 Mit dieser Funktion können Sie ermitteln, welche **CBRS_** (Steuerelementtypen Leiste)-Einstellungen werden derzeit für die Steuerleiste festgelegt.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle **CBRS_** (Steuerelementtypen Leiste)-Einstellungen für die Steuerleiste. Finden Sie unter [CControlBar::SetBarStyle](#setbarstyle) für die vollständige Liste der verfügbaren Formate.  
  
### <a name="remarks"></a>Hinweise  
 Verarbeitet keine **WS_** Stile (Fensterstil).  
  
##  <a name="getborders"></a>  CControlBar::GetBorders  
 Gibt die aktuellen rahmenwerte für die Steuerleiste zurück.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` Objekt, das die aktuelle Breite (in Pixel) der einzelnen Seiten des Steuerelementobjekts Balken enthält. Beispielsweise den Wert der die *linken* Member, der [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Breite des linken Rahmens.  
  
##  <a name="getcount"></a>  CControlBar::GetCount  
 Gibt die Anzahl der nicht - `HWND` Elemente auf der `CControlBar` Objekt.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der nicht - `HWND` Elemente auf der `CControlBar` Objekt. Diese Funktion gibt 0 für eine [CDialogBar](../../mfc/reference/cdialogbar-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Typ des Elements hängt das abgeleitete Objekt: Bereiche für [CStatusBar](../../mfc/reference/cstatusbar-class.md) Objekte, Schaltflächen und Trennzeichen für [CToolBar](../../mfc/reference/ctoolbar-class.md) Objekte.  
  
##  <a name="getdockingframe"></a>  CControlBar::GetDockingFrame  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf den aktuellen Frame-Fensters zu erhalten, an dem die Steuerleiste angedockt ist.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Framefenster bei Erfolg; andernfalls **NULL**.  
  
 Wenn die Steuerleiste ist nicht an ein Framefenster angedockt, (d. h., wenn die Steuerleiste unverankert ist), wird diese Funktion einen Zeiger zurück, an die übergeordnete [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu andockbaren Balken, finden Sie unter [CControlBar:: EnableDocking](#enabledocking) und [CFrameWnd:: DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
##  <a name="isfloating"></a>  CControlBar::IsFloating  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die Steuerleiste Gleitkommatyp oder angedockt ist.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Steuerleiste unverankert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ändern Sie den Zustand aus einer Steuerleiste angedockt in Gleitkommazahlen, rufen Sie [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).  
  
##  <a name="m_bautodelete"></a>  CControlBar::m_bAutoDelete  
 Wenn der Wert ungleich 0 (null) ist, wird das `CControlBar`-Objekt gelöscht, sobald die Windows-Steuerleiste beschädigt wird.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Hinweise  
 *M_bAutoDelete* ist eine öffentliche Variable des Typs **BOOL**.  
  
 Eine Steuerleiste-Objekt eingebettet ist in der Regel in einem Rahmenfenster Objekt. In diesem Fall *M_bAutoDelete* ist 0, da das Objekt eingebettete Steuerleiste zerstört wird, wenn das Rahmenfenster zerstört wird.  
  
 Legen Sie diese Variable auf einen Wert ungleich NULL, wenn Sie Zuweisen einer `CControlBar` Objekt auf dem Heap, und Sie nicht beabsichtigen, rufen Sie **löschen**.  
  
##  <a name="m_pinplaceowner"></a>  CControlBar::m_pInPlaceOwner  
 Der direkte Besitzer der Steuerleiste.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="onupdatecmdui"></a>  CControlBar::OnUpdateCmdUI  
 Diese Memberfunktion wird vom Framework zum Aktualisieren des Status des Balkens Symbolleiste oder Status aufgerufen.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *pTarget*  
 Verweist auf das Hauptrahmenfenster der Anwendung. This-Zeiger wird für das Nachrichtenrouting Update verwendet.  
  
 *bDisableIfNoHndler*  
 Flag, die angibt, ob ein Steuerelement, das kein der updatehandler weist automatisch als deaktiviert angezeigt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Um eine einzelne Schaltfläche oder einen Bereich zu aktualisieren, verwenden die `ON_UPDATE_COMMAND_UI` Makro in Ihrer nachrichtenzuordnung einen updatehandler ordnungsgemäß festgelegt. Finden Sie unter [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) für Weitere Informationen zum Verwenden dieses Makro.  
  
 `OnUpdateCmdUI` wird vom Framework aufgerufen, wenn die Anwendung im Leerlauf befindet. Das Rahmenfenster aktualisiert werden, muss ein untergeordnetes Fenster mindestens indirekt Rand eines Rahmenfensters sichtbar sein. `OnUpdateCmdUI` ist eine erweiterte überschrieben.  
  
##  <a name="setbarstyle"></a>  CControlBar::SetBarStyle  
 Mit dieser Funktion wird zum Festlegen der gewünschten **CBRS_** Stile für die Steuerleiste.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *dwStyle*  
 Die gewünschte Stile für die Steuerleiste. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `CBRS_ALIGN_TOP` Ermöglicht die Steuerleiste am oberen Rand der Clientbereich eines Rahmenfensters angedockt werden.  
  
- `CBRS_ALIGN_BOTTOM` Ermöglicht die Steuerleiste am unteren Rand der Clientbereich eines Rahmenfensters angedockt werden.  
  
- `CBRS_ALIGN_LEFT` Ermöglicht die Steuerleiste an der linken Seite des Clientbereichs eines Frame-Fensters angedockt werden.  
  
- `CBRS_ALIGN_RIGHT` Ermöglicht die Steuerleiste an der rechten Seite des Clientbereichs eines Frame-Fensters angedockt werden.  
  
- `CBRS_ALIGN_ANY` Ermöglicht die Steuerleiste auf jeder Seite des Clientbereichs Rand eines Rahmenfensters angedockt werden.  
  
- `CBRS_BORDER_TOP` Bewirkt, dass einen Rahmen, auf den oberen Rand der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_BORDER_BOTTOM` Bewirkt, dass einen Rahmen, für den unteren Rand der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_BORDER_LEFT` Bewirkt, dass einen Rahmen, auf dem linken Rand der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_BORDER_RIGHT` Bewirkt, dass einen Rahmen, auf dem rechten Rand der Steuerleiste gezeichnet werden soll, wenn es sichtbar wäre.  
  
- `CBRS_FLOAT_MULTI` Ermöglicht es mehreren Steuerleisten, die in einer einzelnen Minirahmenfenster umfließt werden.  
  
- `CBRS_TOOLTIPS` Bewirkt, dass QuickInfos für die Steuerleiste angezeigt werden soll.  
  
- `CBRS_FLYBY` Bewirkt, dass Meldungstext zur gleichen Zeit wie QuickInfos aktualisiert werden.  
  
- `CBRS_GRIPPER` Bewirkt, dass ein ziehelements, ähnlich wie auf Bänder in einer `CReBar` -Objekt, für eine beliebige gezeichnet werden `CControlBar`-abgeleitete Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Hat keinen Einfluss auf die **WS_** (Fensterstil)-Einstellungen.  
  
##  <a name="setborders"></a>  CControlBar::SetBorders  
 Mit dieser Funktion wird zum Festlegen der Größe der Rahmen der Steuerleiste.  
  
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
 Die Höhe (in Pixel) des oberen Rahmens der Steuerleiste.  
  
 *cxRight*  
 Die Breite (in Pixel) des rechten Rands der Steuerleiste.  
  
 *cyBottom*  
 Die Höhe (in Pixel) für die untere Rahmenlinie der Steuerleiste.  
  
 *lpRect*  
 Ein Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die aktuelle Breite (in Pixel) der einzelnen Rahmen der Steuerleistenobjekt enthält.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt die oberen und unteren Rahmen der Steuerleiste 5 Pixel und die linken und rechten Rahmen auf 2 Pixel fest:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="setinplaceowner"></a>  CControlBar::SetInPlaceOwner  
 Ändert den direkten Besitzer einer Steuerleiste.  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pWnd*  
 Ein Zeiger auf eine `CWnd` Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel jeder](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar-Klasse](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar-Klasse](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar-Klasse](../../mfc/reference/cstatusbar-class.md)   
 [CReBar-Klasse](../../mfc/reference/crebar-class.md)
