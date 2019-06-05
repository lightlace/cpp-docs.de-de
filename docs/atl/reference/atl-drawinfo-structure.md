---
title: ATL_DRAWINFO-Struktur
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: 77ef56f73be1ed9ddfc63c459b6bab3ad4decb3f
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503415"
---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO-Struktur

Enthält Informationen, die für das Rendering an verschiedene Ziele, z. B. einen Drucker, Metadatei oder ActiveX-Steuerelement verwendet.

## <a name="syntax"></a>Syntax

```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```

## <a name="members"></a>Member

`cbSize`<br/>
Die Größe der Struktur, in Bytes.

`dwDrawAspect`<br/>
Gibt an, wie das Ziel dargestellt werden soll. Darstellungen können es sich um Inhalte, ein Symbol, eine Miniaturansicht oder einem gedruckten Dokument enthalten. Eine Liste der möglichen Werte, finden Sie unter [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) und [DVASPECT2](/windows/desktop/api/ocidl/ne-ocidl-tagdvaspect2).

`lindex`<br/>
Der Teil des Ziels, das für den Ziehvorgang relevant ist. Die Interpretation hängt von den Wert in der `dwDrawAspect` Member.

`ptd`<br/>
Zeiger auf eine [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) -Struktur, die Zeichnen-Optimierungen, abhängig vom angegebenen Aspekt ermöglicht. Beachten Sie, dass neueren Objekten und Containern, die optimierte zeichnen Schnittstellen unterstützen auch dieser Member unterstützt. Geben Sie NULL für diesen Member, älteren Objekten und Containern, die nicht optimierte zeichnen Schnittstellen immer unterstützt werden.

`hicTargetDev`<br/>
Informationen über den Kontext für das Zielgerät verweist `ptd` aus dem das Objekt Gerätemetrik abrufen und Funktionen des Geräts prüfen kann. Wenn `ptd` NULL ist, das Objekt den Wert in ignorieren soll die `hicTargetDev` Member.

`hdcDraw`<br/>
Der Gerätekontext, in dem gezeichnet werden soll. Für ein fensterloses Objekt das `hdcDraw` ist Mitglied der `MM_TEXT` Zuordnungsmodus mit der logischen Koordinaten Abgleich der Clientkoordinaten des übergeordneten Fensters. Darüber hinaus der Gerätekontext muss den gleichen Zustand wie der in der Regel durch Übergeben einer `WM_PAINT` Nachricht.

`prcBounds`<br/>
Zeiger auf eine [RECTL](/previous-versions//dd162907\(v=vs.85\)) -Struktur gibt das Rechteck auf `hdcDraw` und in dem das Objekt gezeichnet werden soll. Dieses Element steuert die Positionierung und Strecken des Objekts. Dieser Member sollte NULL, um ein fensterloses für ein direktes aktives Objekt gezeichnet werden soll. In jedem anderen Fall NULL ist kein gültiger Wert und sollten dazu führen, eine `E_INVALIDARG` Fehlercode. Wenn der Container einen Wert ungleich NULL für fensterloses Objekt übergibt, sollte das Objekt den angeforderten Aspekt in den angegebenen Gerätekontext und das Rechteck gerendert. Ein Container kann dies von fensterloses Objekt zum Rendern einer zweiten, nicht aktive Ansicht des Objekts oder zum Drucken des Objekts anfordern.

`prcWBounds`<br/>
Wenn `hdcDraw` ist eine Metadatei-Gerätekontexts (finden Sie unter [GetDeviceCaps](/windows/desktop/api/wingdi/nf-wingdi-getdevicecaps) im Windows SDK), dies ist ein Zeiger auf eine `RECTL` Struktur, die das umschließende Rechteck in der zugrunde liegenden Metadatei angibt. Die Rectangle-Struktur enthält, die Fenster Umfang und die Fensterursprung. Diese Werte sind hilfreich für das Zeichnen von Metadateien. Das Rechteck erkennbar `prcBounds` darin geschachtelt ist dies `prcWBounds` Rechteck; sie befinden sich in den gleichen koordinierten Bereich.

`bOptimize`<br/>
Ungleich NULL ist das Zeichnen des Steuerelements zum werden optimiert, andernfalls 0. Wenn das Zeichnen optimiert ist, wird der Status des Gerätekontexts automatisch wiederhergestellt, sobald Sie fertig sind rendern.

`bZoomed`<br/>
Ungleich NULL, wenn das Ziel einen Zoomfaktor, andernfalls 0 hat. Der Zoomfaktor befindet sich in `ZoomNum`.

`bRectInHimetric`<br/>
Einen Wert ungleich NULL die Abmessungen des `prcBounds` befinden sich im HIMETRIC, andernfalls 0.

`ZoomNum`<br/>
Die Breite und Höhe des Rechtecks in dem das Objekt gerendert wird. Der Zoomfaktor entlang der x-Achse (den Anteil der Größe des Objekts in der aktuellen Umfang) des Ziels ist der Wert des `ZoomNum.cx` geteilt durch den Wert der `ZoomDen.cx`. Der Zoomfaktor entlang der y-Achse wird auf ähnliche Weise erreicht.

`ZoomDen`<br/>
Die tatsächliche Breite und Höhe des Ziels.

## <a name="remarks"></a>Hinweise

Typische Verwendung dieser Struktur wäre das Abrufen von Informationen während der Wiedergabe des Zielobjekts. Angenommen, Sie konnten rufen Werte aus ATL_DRAWINFO innerhalb Ihrer Überladung der [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced).

Diese Struktur speichert, relevante Informationen, mit denen die Darstellung eines Objekts für das Zielgerät gerendert wird. Die bereitgestellten Informationen kann in Funktionen zum Zeichnen auf dem Bildschirm, einen Drucker oder sogar einer Metadatei verwendet werden.

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)<br/>
[IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)
