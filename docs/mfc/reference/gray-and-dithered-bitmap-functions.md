---
title: Bitmap-Funktionen zu Ausgrauen und Dithering
ms.date: 11/19/2018
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
ms.openlocfilehash: fb764dbd71d89ae3317816df3539c2881b9695b6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290780"
---
# <a name="gray-and-dithered-bitmap-functions"></a>Bitmap-Funktionen zu Ausgrauen und Dithering

**Ausgegraute Bitmap-Funktionen**

MFC enthält zwei Funktionen, die verwendet werden können, um einer Bitmap das Aussehen eines deaktivierten Steuerelements zu verleihen.

![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vergleich von grauen und ursprünglichen Symbolversionen")

|||
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Zeichnet eine graue Version einer Bitmap.|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Kopiert eine graue Version einer Bitmap.|

**Bitmap-Funktionen mit Dithering**

MFC enthält außerdem zwei Funktionen, mit denen der Hintergrund einer Bitmap durch ein gedithertes Muster ersetzt werden kann.

![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vergleich von geditherten und ursprünglichen Symbolversionen")

|||
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Zeichnet eine Bitmap mit gedithertem Hintergrund.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Kopiert eine Bitmap mit gedithertem Hintergrund.|

##  <a name="afxdrawgraybitmap"></a>  AfxDrawGrayBitmap

Zeichnet eine graue Version einer Bitmap.

```
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Zeigt auf den Ziel-DC.

*w*<br/>
Die X-Koordinate des Ziels.

*y*<br/>
Die Y-Koordinate des Ziels.

*rSrc*<br/>
Die Quellbitmap.

*crBackground*<br/>
Die neue Hintergrundfarbe (normalerweise grau, wie etwa COLOR_MENU).

### <a name="remarks"></a>Hinweise

Eine mit `AfxDrawGrayBitmap` gezeichnete Bitmap hat das Aussehen eines deaktivierten Steuerelements.

![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vergleich von grauen und ursprünglichen Symbolversionen")

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="afxgetgraybitmap"></a>  AfxGetGrayBitmap

Kopiert eine graue Version einer Bitmap.

```
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parameter

*rSrc*<br/>
Die Quellbitmap.

*pDest*<br/>
Die Zielbitmap.

*crBackground*<br/>
Die neue Hintergrundfarbe (normalerweise grau, wie etwa COLOR_MENU).

### <a name="remarks"></a>Hinweise

Eine mit `AfxGetGrayBitmap` kopierte Bitmap hat das Aussehen eines deaktivierten Steuerelements.

![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vergleich von grauen und ursprünglichen Symbolversionen")

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap

Zeichnet eine Bitmap, dessen Hintergrund mit einem Muster für Dithering (Prüfung) ersetzt.

```
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Zeigt auf den Ziel-DC.

*w*<br/>
Die X-Koordinate des Ziels.

*y*<br/>
Die Y-Koordinate des Ziels.

*rSrc*<br/>
Die Quellbitmap.

*cr1*<br/>
Einer der beiden Dithering mit Farben ab, in der Regel weiß.

*cr2*<br/>
Die anderen Dithering mit Farbe, in der Regel hellgrau (etwa COLOR_MENU).

### <a name="remarks"></a>Hinweise

Die Quell-Bitmap gezeichnet wird, auf dem Zieldomänencontroller mit einer zwei-Farbe (*cr1* und *cr2*) kariertes Muster, die die Bitmap-Hintergrund ersetzt. Der Hintergrund des Quellbitmaps ist als seine weißen Pixel und alle Pixel, die die Farbe des Pixels in der oberen linken Ecke der Bitmap für die Übereinstimmung definiert.

![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vergleich von geditherten und ursprünglichen Symbolversionen")

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap

Kopiert eine Bitmap, dessen Hintergrund mit einem Muster für Dithering (Prüfung) ersetzt.

```
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parameter

*rSrc*<br/>
Die Quellbitmap.

*pDest*<br/>
Die Zielbitmap.

*cr1*<br/>
Einer der beiden Dithering mit Farben ab, in der Regel weiß.

*cr2*<br/>
Die anderen Dithering mit Farbe, in der Regel hellgrau (etwa COLOR_MENU).

### <a name="remarks"></a>Hinweise

Die Quell-Bitmap wird kopiert, in die Zielbitmap mit einer zwei-Farbe (*cr1* und *cr2*) kariertes Muster, und Ersetzen Sie dabei die Quell-Bitmap-Hintergrund. Der Hintergrund des Quellbitmaps ist als seine weißen Pixel und alle Pixel, die die Farbe des Pixels in der oberen linken Ecke der Bitmap für die Übereinstimmung definiert.

![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
