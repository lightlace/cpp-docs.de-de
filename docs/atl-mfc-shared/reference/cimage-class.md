---
title: CImage-Klasse
ms.date: 08/19/2019
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
ms.openlocfilehash: 3b278f37bbcbe2ee879d9c3d2837267fe31e57e2
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630718"
---
# <a name="cimage-class"></a>CImage-Klasse

`CImage`bietet erweiterte Unterstützung für Bitmap, einschließlich der Möglichkeit, Bilder in JPEG-, GIF-, BMP-und Portable Network Graphics-Formaten (PNG) zu laden und zu speichern.

> [!IMPORTANT]
> Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CImage
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CImage::CImage](#cimage)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|Zeigt Bitmaps mit transparenten oder semitransparenten Pixeln an.|
|[CImage:: Attach](#attach)|Fügt ein HBITMAP an ein `CImage` -Objekt an. Kann entweder mit nicht-DIB-Abschnitts Bitmaps oder DIB-Abschnitts Bitmaps verwendet werden.|
|[CImage::BitBlt](#bitblt)|Kopiert eine Bitmap aus dem Quell Gerätekontext in diesen aktuellen Gerätekontext.|
|[CImage::Create](#create)|Erstellt eine DIB-Abschnitts Bitmap und fügt Sie an das zuvor `CImage` erstellte-Objekt an.|
|[CImage::CreateEx](#createex)|Erstellt eine DIB-Abschnitts Bitmap (mit zusätzlichen Parametern) und fügt Sie an das `CImage` zuvor erstellte Objekt an.|
|[CImage::D estroy](#destroy)|Trennt die Bitmap vom `CImage` -Objekt und zerstört die Bitmap.|
|[CImage::D Etach](#detach)|Trennt die Bitmap von einem `CImage` -Objekt.|
|[CImage::Draw](#draw)|Kopiert eine Bitmap aus einem Quell Rechteck in ein Ziel Rechteck. `Draw`stremiert oder komprimiert die Bitmap, sodass Sie ggf. den Abmessungen des Ziel Rechtecks entspricht, und behandelt Alpha Mischungen und transparente Farben.|
|[CImage::GetBits](#getbits)|Ruft einen Zeiger auf die eigentlichen Pixelwerte der Bitmap ab.|
|[CImage::GetBPP](#getbpp)|Ruft die Bits pro Pixel ab.|
|[CImage::GetColorTable](#getcolortable)|Ruft rote, grüne, blaue (RGB) Farbwerte aus einem Bereich von Einträgen in der Farbtabelle ab.|
|[CImage::GetDC](#getdc)|Ruft den Gerätekontext ab, in dem die aktuelle Bitmap ausgewählt wird.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Sucht die verfügbaren Bildformate und deren Beschreibungen.|
|[CImage::GetHeight](#getheight)|Ruft die Höhe des aktuellen Bilds in Pixel ab.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Sucht die verfügbaren Bildformate und deren Beschreibungen.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Ruft die maximale Anzahl von Einträgen in der Farbtabelle ab.|
|[CImage::GetPitch](#getpitch)|Ruft die Tonhöhe des aktuellen Bilds in Bytes ab.|
|[CImage::GetPixel](#getpixel)|Ruft die Farbe des Pixels ab, das von *x* und *y*angegeben wird.|
|[CImage::GetPixelAddress](#getpixeladdress)|Ruft die Adresse eines gegebenen Pixels ab.|
|[CImage::GetTransparentColor](#gettransparentcolor)|Ruft die Position der transparenten Farbe in der Farbtabelle ab.|
|[CImage::GetWidth](#getwidth)|Ruft die Breite des aktuellen Bilds in Pixel ab.|
|[CImage::IsDIBSection](#isdibsection)|Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.|
|[CImage::IsIndexed](#isindexed)|Gibt an, dass die Farben einer Bitmap einer indizierten Palette zugeordnet werden.|
|[CImage::IsNull](#isnull)|Gibt an, ob eine Quell Bitmap momentan geladen ist.|
|[CImage::IsTransparencySupported](#istransparencysupported)|Gibt an, ob die Anwendung transparente Bitmaps unterstützt.|
|[CImage::Load](#load)|Lädt ein Bild aus der angegebenen Datei.|
|[CImage::LoadFromResource](#loadfromresource)|Lädt ein Bild aus der angegebenen Ressource.|
|[CImage::MaskBlt](#maskblt)|Kombiniert die Farbdaten für die Quell-und Ziel Bitmaps mithilfe der angegebenen Maske und des Raster Vorgangs.|
|[CImage::PlgBlt](#plgblt)|Führt eine Bitblock Übertragung von einem Rechteck in einem Quell Gerätekontext in ein Parallelogramm in einem Zielgeräte Kontext aus.|
|[CImage::ReleaseDC](#releasedc)|Gibt den Gerätekontext frei, der mit [CImage:: GetDC](#getdc)abgerufen wurde.|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Gibt die von GDI+ verwendeten Ressourcen frei. Muss aufgerufen werden, um Ressourcen freizugeben, die `CImage` von einem globalen Objekt erstellt wurden.|
|[CImage::Save](#save)|Speichert ein Bild als den angegebenen Typ. `Save`die Bild Optionen können nicht angegeben werden.|
|[CImage::SetColorTable](#setcolortable)|Legt farbige, grüne und blaue RGB-Farbwerte in einem Bereich von Einträgen in der Farbtabelle des DIB-Abschnitts fest.|
|[CImage::SetPixel](#setpixel)|Legt das Pixel an den angegebenen Koordinaten auf die angegebene Farbe fest.|
|[CImage::SetPixelIndexed](#setpixelindexed)|Legt das Pixel an den angegebenen Koordinaten auf die Farbe am angegebenen Index der Palette fest.|
|[CImage::SetPixelRGB](#setpixelrgb)|Legt das Pixel an den angegebenen Koordinaten auf den angegebenen roten, grünen, blauen (RGB) Wert fest.|
|[CImage::SetTransparentColor](#settransparentcolor)|Legt den Index der Farbe fest, die als transparent behandelt werden soll. Nur eine Farbe in einer Palette kann transparent sein.|
|[CImage::StretchBlt](#stretchblt)|Kopiert eine Bitmap aus einem Quell Rechteck in ein Ziel Rechteck, wobei die Bitmap bei Bedarf an die Abmessungen des Ziel Rechtecks angepasst oder komprimiert wird.|
|[CImage::TransparentBlt](#transparentblt)|Kopiert eine Bitmap mit transparenter Farbe aus dem Quell Gerätekontext in diesen aktuellen Gerätekontext.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CImage:: Operator HBITMAP](#operator_hbitmap)|Gibt das an das `CImage` -Objekt angefügte Windows-Handle zurück.|

## <a name="remarks"></a>Hinweise

`CImage`erfordert Bitmaps, bei denen es sich entweder um einen geräteunabhängigen Bitmap-Abschnitt (DIB) handelt oder nicht. Sie können jedoch [Create](#create) oder [CImage:: Load](#load) nur mit DIB-Abschnitten verwenden. Sie können eine nicht-DIB-Abschnitts Bitmap an ein `CImage` -Objekt anfügen, indem Sie [Anfügen](#attach)verwenden. `CImage` Sie können jedoch nicht die folgenden Methoden verwenden, die nur DIB-Abschnitts Bitmaps unterstützen:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [Getpixeladdress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

Um zu ermitteln, ob eine angefügte Bitmap ein DIB-Abschnitt ist, nennen Sie [isdibsection](#isdibsection).

> [!NOTE]
> In Visual Studio .NET 2003 behält diese Klasse die Anzahl `CImage` der erstellten Objekte bei. Wenn die Anzahl auf 0 (null) sinkt `GdiplusShutdown` , wird die Funktion automatisch aufgerufen, um von GDI+ verwendete Ressourcen freizugeben. Dadurch wird sichergestellt `CImage` , dass alle direkt oder indirekt durch DLLs erstellten Objekte ordnungsgemäß zerstört `GdiplusShutdown` werden und nicht von `DllMain`aufgerufen werden.

> [!NOTE]
> Es wird `CImage` nicht empfohlen, globale Objekte in einer DLL zu verwenden. Wenn Sie ein globales `CImage` Objekt in einer DLL verwenden müssen, nennen Sie [CImage:: releasegdiplus](#releasegdiplus) , um die von GDI+ verwendeten Ressourcen explizit freizugeben.

`CImage`kann nicht in einem neuen [CDC](../../mfc/reference/cdc-class.md)ausgewählt werden. `CImage`erstellt einen eigenen HDC für das Image. Da eine HBITMAP nur jeweils in einem hdc ausgewählt werden kann, kann die HBITMAP, die dem `CImage` zugeordnet ist, nicht in einem anderen HDC ausgewählt werden. Wenn Sie eine CDC benötigen, rufen Sie den hdc aus `CImage` dem ab, und übergeben Sie ihn an [CDC:: FromHandle](../../mfc/reference/cdc-class.md#fromhandle).

## <a name="example"></a>Beispiel

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

Beachten Sie bei `CImage` der Verwendung von in einem MFC-Projekt, welche Member-Funktionen in Ihrem Projekt einen Zeiger auf ein [CBitmap](../../mfc/reference/cbitmap-class.md) -Objekt erwarten. Wenn Sie mit einer solchen `CImage` Funktion verwenden möchten, z. b. [CMenu:: AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), verwenden Sie [CBitmap:: FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), `CImage` übergeben Sie Ihr HBITMAP, und `CBitmap*`verwenden Sie die zurückgegebene.

## <a name="example"></a>Beispiel

```cpp
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
    UNREFERENCED_PARAMETER(nFlags);

    CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
    m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
    ClientToScreen(&point);
    m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x,
    point.y, this);
}
```

`CImage`Mithilfe von haben Sie Zugriff auf die tatsächlichen Bits eines DIB-Abschnitts. Sie können ein `CImage` -Objekt überall dort verwenden, wo Sie zuvor einen Win32-HBITMAP-oder DIB-Abschnitt verwendet haben.

Sie können entweder `CImage` von MFC oder ATL verwenden.

> [!NOTE]
> Wenn Sie ein Projekt mit `CImage`erstellen, müssen Sie definieren `CString` , bevor Sie *atlimage. h*einschließen. Wenn Ihr Projekt ATL ohne MFC verwendet, fügen Sie " *atlstr. h* " ein, bevor Sie " *atlimage. h*" einschließen. Wenn für Ihr Projekt MFC verwendet wird (oder wenn es sich um ein ATL-Projekt mit MFC-Unterstützung handelt), schließen Sie *afxstr. h* ein, bevor Sie *atlimage. h*einschließen.<br/>
> <br/>
> Ebenso müssen Sie *atlimage. h* einschließen, bevor Sie *Atlimpl. cpp*einschließen. Um dies zu erreichen, fügen Sie " *atlimage. h* " in die Datei " *PCH. h* " ein (*stdafx. h* in Visual Studio 2017 und früher).

## <a name="requirements"></a>Anforderungen

**Header:** atlimage. h

##  <a name="alphablend"></a>CImage:: AlphaBlend

Zeigt Bitmaps mit transparenten oder semitransparenten Pixeln an.

```
BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    const POINT& pointDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);
```

### <a name="parameters"></a>Parameter

*hDestDC*<br/>
Handle für den Zielgeräte Kontext.

*xDest*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*yDest*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*bSrcAlpha*<br/>
Ein Alpha Transparenz Wert, der für die gesamte Quell Bitmap verwendet werden soll. Der Standardwert 0xFF (255) setzt voraus, dass das Bild nicht transparent ist, und dass Sie nur Pixel-Alpha Werte pro Pixel verwenden möchten.

*bBlendOp*<br/>
Die Alpha Mischungs Funktion für Quell-und Ziel Bitmaps, einen globalen Alpha-Wert, der auf die gesamte Quell Bitmap angewendet werden soll, und Formatierungsinformationen für die Quell Bitmap. Die Blend-Funktionen für Quelle und Ziel sind zurzeit auf AC_SRC_OVER beschränkt.

*pointDest*<br/>
Ein Verweis auf eine [Punkt](/previous-versions/dd162805\(v=vs.85\)) Struktur, die die linke obere Ecke des Ziel Rechtecks in logischen Einheiten bezeichnet.

*nDestWidth*<br/>
Die Breite des Ziel Rechtecks in logischen Einheiten.

*nDestHeight*<br/>
Die Höhe des Ziel Rechtecks in logischen Einheiten.

*xSrc*<br/>
Die logische x-Koordinate der oberen linken Ecke des Quell Rechtecks.

*ySrc*<br/>
Die logische y-Koordinate der oberen linken Ecke des Quell Rechtecks.

*nSrcWidth*<br/>
Die Breite des Quell Rechtecks in logischen Einheiten.

*nSrcHeight*<br/>
Die Höhe des Quell Rechtecks in logischen Einheiten.

*rectDest*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die das Ziel identifiziert.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` -Struktur, die die Quelle identifiziert.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Alpha-Blend-Bitmaps unterstützen Farb Mischungs Farben pro Pixel.

Wenn *bblendop* auf den Standardwert von AC_SRC_OVER festgelegt ist, wird die Quell Bitmap auf der Zielbitmap basierend auf den Alpha Werten der Quell Pixel platziert.

##  <a name="attach"></a>CImage:: Attach

Fügt *hBitmap* an ein `CImage` -Objekt an.

```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Parameter

*hBitmap*<br/>
Ein Handle für eine HBITMAP.

*eOrientation*<br/>
Gibt die Ausrichtung der Bitmap an. Kann einen der folgenden Werte annehmen:

- DIBOR_DEFAULT die Ausrichtung der Bitmap hängt vom Betriebssystem ab.

- DIBOR_BOTTOMUP die Zeilen der Bitmap befinden sich in umgekehrter Reihenfolge. Dies bewirkt, dass [CImage:: GetBits](#getbits) einen Zeiger in der Nähe des Endes des bitmappuffers und [CImage:: getPitch](#getpitch) zurückgibt, um eine negative Zahl zurückzugeben.

- DIBOR_TOPDOWN die Zeilen der Bitmap sind in der Reihenfolge von oben nach unten angeordnet. Dies bewirkt, dass [CImage:: GetBits](#getbits) einen Zeiger auf das erste Byte des bitmappuffers und [CImage:: getPitch](#getpitch) zurückgibt, um eine positive Zahl zurückzugeben.

### <a name="remarks"></a>Hinweise

Die Bitmap kann entweder eine nicht-DIB-Abschnitts Bitmap oder eine DIB-Abschnitts Bitmap sein. Eine Liste der Methoden, die Sie nur mit DIB-Abschnitts Bitmaps verwenden können, finden Sie unter [isdibsection](#isdibsection) .

##  <a name="bitblt"></a>CImage:: BitBLT

Kopiert eine Bitmap aus dem Quell Gerätekontext in diesen aktuellen Gerätekontext.

```
BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const POINT& pointDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Parameter

*hDestDC*<br/>
Der Ziel-hdc.

*xDest*<br/>
Die logische x-Koordinate der oberen linken Ecke des Ziel Rechtecks.

*yDest*<br/>
Die logische y-Koordinate der oberen linken Ecke des Ziel Rechtecks.

*dwROP*<br/>
Der auszuführende Raster Vorgang. Raster-Vorgangs Codes definieren genau, wie die Bits der Quelle, des Ziels und des Musters (wie durch den aktuell ausgewählten Pinsel definiert) zum bilden des Ziels kombiniert werden. Unter [BitBLT](/windows/win32/api/wingdi/nf-wingdi-bitblt) im Windows SDK finden Sie eine Liste mit anderen Code für den Raster Betrieb und deren Beschreibungen.

*pointDest*<br/>
Eine [Punkt](/previous-versions/dd162805\(v=vs.85\)) Struktur, die die linke obere Ecke des Ziel Rechtecks angibt.

*nDestWidth*<br/>
Die Breite des Ziel Rechtecks in logischen Einheiten.

*nDestHeight*<br/>
Die Höhe des Ziel Rechtecks in logischen Einheiten.

*xSrc*<br/>
Die logische x-Koordinate der oberen linken Ecke des Quell Rechtecks.

*ySrc*<br/>
Die logische y-Koordinate der oberen linken Ecke des Quell Rechtecks.

*rectDest*<br/>
Eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die das Ziel Rechteck angibt.

*pointSrc*<br/>
Eine `POINT` -Struktur, die die linke obere Ecke des Quell Rechtecks angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [BitBLT](/windows/win32/api/wingdi/nf-wingdi-bitblt) in der Windows SDK.

##  <a name="cimage"></a>CImage:: CImage

Erstellt ein `CImage`-Objekt.

```
CImage() throw();
```

### <a name="remarks"></a>Hinweise

Nachdem Sie das Objekt erstellt haben, rufen Sie [Create](#create), [Load](#load), [loadfromresource](#loadfromresource)oder [Attach](#attach) auf, um eine Bitmap an das Objekt anzufügen.

**Hinweis** In Visual Studio behält diese Klasse die Anzahl `CImage` der erstellten Objekte bei. Wenn die Anzahl auf 0 (null) sinkt `GdiplusShutdown` , wird die Funktion automatisch aufgerufen, um von GDI+ verwendete Ressourcen freizugeben. Dadurch wird sichergestellt `CImage` , dass alle direkt oder indirekt durch DLLs erstellten Objekte ordnungsgemäß zerstört `GdiplusShutdown` werden und nicht von DllMain aufgerufen werden.

Es wird `CImage` nicht empfohlen, globale Objekte in einer DLL zu verwenden. Wenn Sie ein globales `CImage` Objekt in einer DLL verwenden müssen, nennen Sie [CImage:: releasegdiplus](#releasegdiplus) , um die von GDI+ verwendeten Ressourcen explizit freizugeben.

##  <a name="create"></a>CImage:: Create

Erstellt eine `CImage` Bitmap und fügt Sie an das zuvor erstellte `CImage` -Objekt an.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Die Breite der `CImage` Bitmap in Pixel.

*nheight*<br/>
Die Höhe `CImage` der Bitmap in Pixel. Wenn *nheight* positiv ist, ist die Bitmap ein Bottom-up-DIB, und der Ursprung ist die untere linke Ecke. Wenn *nheight* negativ ist, ist die Bitmap eine Top-Down-DIB, und Ihr Ursprung ist die linke obere Ecke.

*nBPP*<br/>
Die Anzahl der Bits pro Pixel in der Bitmap. Normalerweise 4, 8, 16, 24 oder 32. Kann für monochrome Bitmaps oder-Masken 1 sein.

*dwFlags*<br/>
Gibt an, ob das Bitmap-Objekt über einen Alpha-Kanal verfügt. Kann eine Kombination aus null oder mehr der folgenden Werte sein:

- " *kreatealphachannel* " Kann nur verwendet werden, wenn *nbpp* 32 und *ecompression* BI_RGB ist. Wenn angegeben, hat das erstellte Image einen Alpha-Wert (Transparenz) für jedes Pixel, das im 4. Byte der einzelnen Pixel gespeichert wird (nicht verwendet in einem nicht-alpha-32-Bit-Bild). Dieser Alphakanal wird automatisch verwendet, wenn [CImage:: AlphaBlend](#alphablend)aufgerufen wird.

> [!NOTE]
> In Aufrufen von [CImage::D RAW](#draw)werden Bilder mit einem Alphakanal automatisch mit dem Ziel gemischt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="createex"></a>CImage:: kreateex

Erstellt eine `CImage` Bitmap und fügt Sie an das zuvor erstellte `CImage` -Objekt an.

```
BOOL CreateEx(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD eCompression,
    const DWORD* pdwBitmasks = NULL,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Die Breite der `CImage` Bitmap in Pixel.

*nheight*<br/>
Die Höhe `CImage` der Bitmap in Pixel. Wenn *nheight* positiv ist, ist die Bitmap ein Bottom-up-DIB, und der Ursprung ist die untere linke Ecke. Wenn *nheight* negativ ist, ist die Bitmap eine Top-Down-DIB, und Ihr Ursprung ist die linke obere Ecke.

*nBPP*<br/>
Die Anzahl der Bits pro Pixel in der Bitmap. Normalerweise 4, 8, 16, 24 oder 32. Kann für monochrome Bitmaps oder-Masken 1 sein.

*eCompression*<br/>
Gibt den Komprimierungstyp für eine komprimierte Bottom-up-Bitmap an (Top-Down-Disb können nicht komprimiert werden). Kann einer der folgenden Werte sein:

- BI_RGB das Format ist nicht komprimiert. Die Angabe dieses Werts beim `CImage::CreateEx` Aufrufen von entspricht dem `CImage::Create`Aufrufen von.

- BI_BITFIELDS das Format ist unkomprimiert, und die Farbtabelle besteht aus drei DWORD-Farb Masken, die jeweils die roten, grünen und blauen Komponenten der einzelnen Pixel angeben. Dies ist gültig bei Verwendung mit 16-und 32-bpp-Bitmaps.

*pdwBitfields*<br/>
Wird nur verwendet, wenn *ecompression* auf BI_BITFIELDS festgelegt ist, andernfalls muss Sie NULL sein. Ein Zeiger auf ein Array von drei DWORD-Bitmasks, das angibt, welche Bits jedes Pixels für die rot-, grün-und Blau-Komponenten der Farbe verwendet werden. Informationen zu Einschränkungen für Bitfields finden Sie unter [BITMAPINFOHEADER](/previous-versions//dd183376\(v=vs.85\)) in der Windows SDK.

*dwFlags*<br/>
Gibt an, ob das Bitmap-Objekt über einen Alpha-Kanal verfügt. Kann eine Kombination aus null oder mehr der folgenden Werte sein:

- " *kreatealphachannel* " Kann nur verwendet werden, wenn *nbpp* 32 und *ecompression* BI_RGB ist. Wenn angegeben, hat das erstellte Image einen Alpha-Wert (Transparenz) für jedes Pixel, das im 4. Byte der einzelnen Pixel gespeichert wird (nicht verwendet in einem nicht-alpha-32-Bit-Bild). Dieser Alphakanal wird automatisch verwendet, wenn [CImage:: AlphaBlend](#alphablend)aufgerufen wird.

   > [!NOTE]
   > In Aufrufen von [CImage::D RAW](#draw)werden Bilder mit einem Alphakanal automatisch mit dem Ziel gemischt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich. Andernfalls false.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine 100 x 100 Pixel-Bitmap erstellt, wobei 16 Bits zum Codieren der einzelnen Pixel verwendet werden. In einem angegebenen 16-Bit-Pixel codieren Bits 0-3 die rote Komponente, Bits 4-7 codieren grün und Bits 8-11 codieren blau. Die verbleibenden 4 Bits werden nicht verwendet.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

##  <a name="destroy"></a>CImage::D estroy

Trennt die Bitmap vom `CImage` -Objekt und zerstört die Bitmap.

```
void Destroy() throw();
```

##  <a name="detach"></a>CImage::D Etach

Trennt eine Bitmap von einem `CImage` -Objekt.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für die getrennte Bitmap oder NULL, wenn keine Bitmap angefügt ist.

##  <a name="draw"></a>CImage::D RAW

Kopiert eine Bitmap aus dem Quell Gerätekontext in den aktuellen Gerätekontext.

```
BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest) const throw();

BOOL Draw(
    HDC hDestDC,
    const POINT& pointDest) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest) const throw();
```

### <a name="parameters"></a>Parameter

*hDestDC*<br/>
Ein Handle für den Zielgeräte Kontext.

*xDest*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*yDest*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*nDestWidth*<br/>
Die Breite des Ziel Rechtecks in logischen Einheiten.

*nDestHeight*<br/>
Die Höhe des Ziel Rechtecks in logischen Einheiten.

*xSrc*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*ySrc*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*nSrcWidth*<br/>
Die Breite des Quell Rechtecks in logischen Einheiten.

*nSrcHeight*<br/>
Die Höhe des Quell Rechtecks in logischen Einheiten.

*rectDest*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die das Ziel identifiziert.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` -Struktur, die die Quelle identifiziert.

*pointDest*<br/>
Ein Verweis auf eine [Punkt](/previous-versions/dd162805\(v=vs.85\)) Struktur, die die linke obere Ecke des Ziel Rechtecks in logischen Einheiten bezeichnet.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

`Draw`führt den gleichen Vorgang wie [StretchBlt](#stretchblt)aus, es sei denn, das Bild enthält eine transparente Farbe oder einen Alphakanal. In diesem Fall führt `Draw` den gleichen Vorgang wie erforderlich aus, um entweder [TransparentBlt](#transparentblt) oder [AlphaBlend](#alphablend) durchführen zu können.

Bei Versionen von `Draw` , die kein Quell Rechteck angeben, ist das gesamte Quell Image der Standard. Bei der-Version `Draw` , die keine Größe für das Ziel Rechteck angibt, ist die Größe des Quell Bilds der Standardwert, und es erfolgt keine Streckung oder Verkleinerung.

##  <a name="getbits"></a>CImage:: GetBits

Ruft einen Zeiger auf die tatsächlichen Bitwerte eines angegebenen Pixels in einer Bitmap ab.

```
void* GetBits() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den bitmappuffer. Wenn die Bitmap ein Bottom-up-DIB ist, zeigt der Zeiger auf das Ende des Puffers. Wenn die Bitmap ein Top-Down-DIB ist, zeigt der Zeiger auf das erste Byte des Puffers.

### <a name="remarks"></a>Hinweise

Mithilfe dieses Zeigers können Sie zusammen mit dem von [getPitch](#getpitch)zurückgegebenen Wert einzelne Pixel in einem Bild suchen und ändern.

> [!NOTE]
> Diese Methode unterstützt nur DIB-Abschnitts Bitmaps. Folglich greifen Sie auf die Pixel eines- `CImage` Objekts auf die gleiche Weise wie die Pixel eines DIB-Abschnitts zu. Der zurückgegebene Zeiger zeigt auf das Pixel an der Position (0,0).

##  <a name="getbpp"></a>CImage:: getbpp

Ruft den Wert für Bits pro Pixel ab.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bits pro Pixel.

### <a name="remarks"></a>Hinweise

Dieser Wert bestimmt die Anzahl der Bits, die jedes Pixel definieren, sowie die maximale Anzahl von Farben in der Bitmap.

Die Bits pro Pixel sind normalerweise 1, 4, 8, 16, 24 oder 32. Weitere Informationen `biBitCount` zu diesem Wert finden Sie unter dem-Member von [BITMAPINFOHEADER](/previous-versions//dd183376\(v=vs.85\)) im Windows SDK.

##  <a name="getcolortable"></a>CImage:: getcolortable

Ruft rote, grüne, blaue (RGB) Farbwerte aus einem Bereich von Einträgen in der Palette des DIB-Abschnitts ab.

```
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Parameter

*iFirstColor*<br/>
Der Farbtabellen Index des ersten Eintrags, der abgerufen werden soll.

*nColors*<br/>
Die Anzahl der abzurufenden farbtabelleneinträge.

*prgbColors*<br/>
Ein Zeiger auf das Array von [rgbquad](/windows/win32/api/wingdi/ns-wingdi-rgbquad) -Strukturen zum Abrufen der farbtabelleneinträge.

##  <a name="getdc"></a>CImage:: GetDC

Ruft den Gerätekontext ab, in dem das Bild derzeit ausgewählt ist.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für einen Gerätekontext.

### <a name="remarks"></a>Hinweise

Für jeden-aufrufbedarf `GetDC`benötigen Sie einen nachfolgenden-aufrufbefehl für [ReleaseDC](#releasedc).

##  <a name="getexporterfilterstring"></a>CImage:: getexporterfilterstring

Findet Bildformate, die zum Speichern von Bildern verfügbar sind.

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Parameter

*strExporters*<br/>
Ein Verweis auf ein `CSimpleString`-Objekt. Weitere Informationen finden Sie unter " **Hinweise** ".

*aguidFileTypes*<br/>
Ein Array von GUIDs, wobei jedes Element einem der Dateitypen in der Zeichenfolge entspricht. Im Beispiel in *pszallfilesdescription* unten ist *aguidfiletypes*[0] GUID_NULL, und die restlichen Array Werte sind die Bild Dateiformate, die vom aktuellen Betriebssystem unterstützt werden.

> [!NOTE]
> Eine umfassende Liste der Konstanten finden Sie unter **Bild Datei Format Konstanten** in der Windows SDK.

*pszAllFilesDescription*<br/>
Wenn dieser Parameter nicht NULL ist, weist die Filter Zeichenfolge am Anfang der Liste einen zusätzlichen Filter auf. Dieser Filter enthält den aktuellen Wert von " *pszallfilesdescription* " für seine Beschreibung und akzeptiert Dateien jeder beliebigen Erweiterung, die von einem anderen Exportprogramm in der Liste unterstützt wird.

Beispiel:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Ein Satz von Bitflags, die angeben, welche Dateitypen aus der Liste ausgeschlossen werden sollen. Zulässige Flags sind:

- `excludeGIF`= 0x01 schließt GIF-Dateien aus.

- `excludeBMP`= 0x02 schließt BMP-Dateien (Windows-Bitmap) aus.

- `excludeEMF`= 0x04 schließt EMF (Enhanced Metafile)-Dateien aus.

- `excludeWMF`= 0x08 schließt WMF-Dateien (Windows Metafile) aus.

- `excludeJPEG`= 0x10 schließt JPEG-Dateien aus.

- `excludePNG`= 0x20 schließt PNG-Dateien aus.

- `excludeTIFF`= 0x40 schließt TIFF-Dateien aus.

- `excludeIcon`= 0x80 schließt ICO-Dateien (Windows-Symbol Dateien) aus.

- `excludeOther`= 0x80000000 schließt alle anderen Dateitypen aus, die oben nicht aufgeführt sind.

- `excludeDefaultLoad`= 0 beim Laden werden alle Dateitypen standardmäßig eingeschlossen.

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`Zum Speichern werden diese Dateien standardmäßig ausgeschlossen, da Sie in der Regel über besondere Anforderungen verfügen.

*chSeparator*<br/>
Das Trennzeichen, das zwischen den Bildformaten verwendet wird. Weitere Informationen finden Sie unter " **Hinweise** ".

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standard.

### <a name="remarks"></a>Hinweise

Sie können die resultierende Format Zeichenfolge an Ihr MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) -Objekt übergeben, um die Dateierweiterungen der verfügbaren Bildformate im Dialogfeld Datei speichern unter verfügbar zu machen.

Der Parameter " *strexporter* " weist das folgende Format auf:

Datei description0&#124;\*. ext0&#124;&#124;filedescription1\*. EXT1&#124;... Dateibeschreibung *n*&#124;\*. ext *n*&#124;&#124;

Dabei ist&#124;"" das Trennzeichen, das `chSeparator`von angegeben wird. Beispiel:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Verwenden Sie das Standard Trennzeichen "&#124;", wenn Sie diese Zeichenfolge an `CFileDialog` ein MFC-Objekt übergeben. Verwenden Sie das NULL Trennzeichen "\ 0", wenn Sie diese Zeichenfolge an ein gemeinsames Dialogfeld zum Speichern von Dateien übergeben.

##  <a name="getheight"></a>CImage:: GetHeight

Ruft die Höhe eines Bilds in Pixel ab.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Höhe eines Bilds in Pixel.

##  <a name="getimporterfilterstring"></a>CImage:: getimporterfilterstring

Findet Bildformate, die zum Laden von Bildern verfügbar sind.

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Parameter

*strImporters*<br/>
Ein Verweis auf ein `CSimpleString`-Objekt. Weitere Informationen finden Sie unter " **Hinweise** ".

*aguidFileTypes*<br/>
Ein Array von GUIDs, wobei jedes Element einem der Dateitypen in der Zeichenfolge entspricht. Im Beispiel in *pszallfilesdescription* unten ist *aguidfiletypes*[0] GUID_NULL, wobei die verbleibenden Array Werte die Bild Dateiformate sind, die vom aktuellen Betriebssystem unterstützt werden.

> [!NOTE]
> Eine umfassende Liste der Konstanten finden Sie unter **Bild Datei Format Konstanten** in der Windows SDK.

*pszAllFilesDescription*<br/>
Wenn dieser Parameter nicht NULL ist, weist die Filter Zeichenfolge am Anfang der Liste einen zusätzlichen Filter auf. Dieser Filter enthält den aktuellen Wert von " *pszallfilesdescription* " für seine Beschreibung und akzeptiert Dateien jeder beliebigen Erweiterung, die von einem anderen Exportprogramm in der Liste unterstützt wird.

Beispiel:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Ein Satz von Bitflags, die angeben, welche Dateitypen aus der Liste ausgeschlossen werden sollen. Zulässige Flags sind:

- `excludeGIF`= 0x01 schließt GIF-Dateien aus.

- `excludeBMP`= 0x02 schließt BMP-Dateien (Windows-Bitmap) aus.

- `excludeEMF`= 0x04 schließt EMF (Enhanced Metafile)-Dateien aus.

- `excludeWMF`= 0x08 schließt WMF-Dateien (Windows Metafile) aus.

- `excludeJPEG`= 0x10 schließt JPEG-Dateien aus.

- `excludePNG`= 0x20 schließt PNG-Dateien aus.

- `excludeTIFF`= 0x40 schließt TIFF-Dateien aus.

- `excludeIcon`= 0x80 schließt ICO-Dateien (Windows-Symbol Dateien) aus.

- `excludeOther`= 0x80000000 schließt alle anderen Dateitypen aus, die oben nicht aufgeführt sind.

- `excludeDefaultLoad`= 0 beim Laden werden alle Dateitypen standardmäßig eingeschlossen.

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`Zum Speichern werden diese Dateien standardmäßig ausgeschlossen, da Sie in der Regel über besondere Anforderungen verfügen.

*chSeparator*<br/>
Das Trennzeichen, das zwischen den Bildformaten verwendet wird. Weitere Informationen finden Sie unter " **Hinweise** ".

### <a name="remarks"></a>Hinweise

Sie können die resultierende Format Zeichenfolge an Ihr MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) -Objekt übergeben, um die Dateierweiterungen der verfügbaren Bildformate im Dialogfeld **Datei öffnen** verfügbar zu machen.

Der *strimporter* -Parameter hat folgendes Format:

Datei description0&#124;\*. ext0&#124;&#124;filedescription1\*. EXT1&#124;... Dateibeschreibung *n*&#124;\*. ext *n*&#124;&#124;

Dabei ist&#124;"" das Trennzeichen, das von " *chseparator*" angegeben wird. Beispiel:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Verwenden Sie das Standard Trennzeichen "&#124;", wenn Sie diese Zeichenfolge an `CFileDialog` ein MFC-Objekt übergeben. Verwenden Sie das NULL Trennzeichen "\ 0", wenn Sie diese Zeichenfolge an ein gemeinsames Dialogfeld zum **Öffnen von Dateien** übergeben.

##  <a name="getmaxcolortableentries"></a>CImage:: getmaxcolortableentries

Ruft die maximale Anzahl von Einträgen in der Farbtabelle ab.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Einträge in der Farbtabelle.

### <a name="remarks"></a>Hinweise

Diese Methode unterstützt nur DIB-Abschnitts Bitmaps.

##  <a name="getpitch"></a>CImage:: getPitch

Ruft die Tonhöhe eines Bilds ab.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Darstellung des Bilds. Wenn der Rückgabewert negativ ist, ist die Bitmap ein Bottom-up-DIB, und der Ursprung ist die untere linke Ecke. Wenn der Rückgabewert positiv ist, ist die Bitmap ein Top-Down-DIB, und der Ursprung ist die linke obere Ecke.

### <a name="remarks"></a>Hinweise

Die Tonhöhe ist der Abstand zwischen zwei Speicheradressen (in Bytes), die den Anfang einer bitmaplinie darstellen, und dem Anfang der nächsten Bitmap-Linie. Da die Tonhöhe in Bytes gemessen wird, hilft Ihnen die Darstellung eines Bilds dabei, das Pixel Format zu bestimmen. Die Tonhöhe kann auch zusätzlichen Arbeitsspeicher enthalten, der für die Bitmap reserviert ist.

Verwenden `GetPitch` Sie mit [GetBits](#getbits) , um einzelne Pixel eines Bilds zu suchen.

> [!NOTE]
> Diese Methode unterstützt nur DIB-Abschnitts Bitmaps.

##  <a name="getpixel"></a>CImage:: GetPixel

Ruft die Farbe des Pixels an der von *x* und *y*angegebenen Position ab.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die x-Koordinate des Pixels.

*y*<br/>
Die y-Koordinate des Pixels.

### <a name="return-value"></a>Rückgabewert

Der rote, grüne und blaue (RGB) Wert des Pixels. Wenn das Pixel außerhalb des aktuellen Clippingbereichs liegt, ist der Rückgabewert CLR_INVALID.

##  <a name="getpixeladdress"></a>CImage:: getpixeladdress

Ruft die genaue Adresse eines Pixels ab.

```
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die x-Koordinate des Pixels.

*y*<br/>
Die y-Koordinate des Pixels.

### <a name="remarks"></a>Hinweise

Die Adresse wird gemäß den Koordinaten eines Pixels, der Tonhöhe der Bitmap und den Bits pro Pixel bestimmt.

Bei Formaten, die weniger als 8 Bits pro Pixel aufweisen, gibt diese Methode die Adresse des Bytes zurück, das das Pixel enthält. Wenn Ihr Bildformat z. b. 4 Bits pro Pixel hat `GetPixelAddress` , gibt die Adresse des ersten Pixels im Byte zurück, und Sie müssen 2 Pixel pro Byte berechnen.

> [!NOTE]
> Diese Methode unterstützt nur DIB-Abschnitts Bitmaps.

##  <a name="gettransparentcolor"></a>CImage:: gettransparentcolor

Ruft den indizierten Speicherort der transparenten Farbe in der Farbpalette ab.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Index der transparenten Farbe.

##  <a name="getwidth"></a>CImage:: getWidth

Ruft die Breite eines Bilds in Pixel ab.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Breite der Bitmap in Pixel.

##  <a name="isdibsection"></a>CImage:: isdibsection

Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die angefügte Bitmap ein DIB-Abschnitt ist. Andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn die Bitmap kein DIB-Abschnitt ist, können Sie die folgenden `CImage` Methoden nicht verwenden, die nur DIB-Abschnitts Bitmaps unterstützen:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [Getpixeladdress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

##  <a name="isindexed"></a>CImage:: isindebug

Bestimmt, ob die Pixel einer Bitmap einer Farbpalette zugeordnet werden.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn indiziert. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode gibt nur dann true zurück, wenn die Bitmap 8-Bit (256 Farben) oder kleiner ist.

> [!NOTE]
> Diese Methode unterstützt nur DIB-Abschnitts Bitmaps.

##  <a name="isnull"></a>CImage:: IsNull

Bestimmt, ob eine Bitmap momentan geladen ist.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode gibt true zurück, wenn eine Bitmap zurzeit nicht geladen ist. andernfalls false.

##  <a name="istransparencysupported"></a>CImage:: istransparkocysupported

Gibt an, ob die Anwendung transparente Bitmaps unterstützt.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die aktuelle Plattform Transparenz unterstützt. Andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn der Rückgabewert ungleich 0 (null) ist und Transparenz unterstützt wird, behandelt ein Aufrufen von [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt)oder [Draw](#draw) transparente Farben.

##  <a name="load"></a>CImage:: Load

Lädt ein Bild.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>Parameter

*pszFileName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen der zu ladenden Bilddatei enthält.

*pStream*<br/>
Ein Zeiger auf einen Stream, der den Namen der zu ladenden Bilddatei enthält.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standard.

### <a name="remarks"></a>Hinweise

Lädt das von *pszFileName* oder *pStream*angegebene Bild.

Gültige Bildtypen sind BMP, GIF, JPEG, PNG und TIFF.

##  <a name="loadfromresource"></a>CImage:: loadfromresource

Lädt ein Bild aus einer Bitmap-Ressource.

```
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>Parameter

*hInstance*<br/>
Handle für eine Instanz des Moduls, das das zu ladende Bild enthält.

*pszResourceName*<br/>
Ein Zeiger auf die Zeichenfolge, die den Namen der Ressource enthält, die das zu ladende Bild enthält.

*nIDResource*<br/>
Die ID der zu ladenden Ressource.

### <a name="remarks"></a>Hinweise

Die Ressource muss den Typ "Bitmap" aufweisen.

##  <a name="maskblt"></a>CImage:: MaskBlt

Kombiniert die Farbdaten für die Quell-und Ziel Bitmaps mithilfe der angegebenen Maske und des Raster Vorgangs.

```
BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    HBITMAP hbmMask,
    int xMask,
    int yMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    HBITMAP hbmMask,
    const POINT& pointMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const POINT& pointDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Parameter

*hDestDC*<br/>
Das Handle für das Modul, dessen ausführbare Datei die Ressource enthält.

*xDest*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*yDest*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*nDestWidth*<br/>
Die Breite des Ziel Rechtecks und der Quell Bitmap in logischen Einheiten.

*nDestHeight*<br/>
Die Höhe des Ziel Rechtecks und der Quell Bitmap in logischen Einheiten.

*xSrc*<br/>
Die logische x-Koordinate der oberen linken Ecke der Quell Bitmap.

*ySrc*<br/>
Die logische y-Koordinate der oberen linken Ecke der Quell Bitmap.

*hbmMask*<br/>
Handle für die Chrome-Masken Bitmap, kombiniert mit der Farb Bitmap im Quell Gerätekontext.

*xmask*<br/>
Der horizontale Pixel Offset für die Maske-Bitmap, die durch den *hbmmask* -Parameter angegeben wird.

*yMask*<br/>
Der vertikale Pixel Offset für die Maske-Bitmap, die durch den *hbmmask* -Parameter angegeben wird.

*dwROP*<br/>
Gibt die ternären Raster Vorgangs Codes für Vordergrund und Hintergrund an, die die-Methode verwendet, um die Kombination von Quell-und Zieldaten zu steuern. Der Code für den Hintergrund Raster Vorgang wird im hochwertigen Byte des höherwertigen Worts dieses Werts gespeichert. der Code für den Vordergrund-Raster Vorgang wird in einem nieder wertigen Byte des höchst wertigen Worts dieses Werts gespeichert. Das nieder wertige Wort dieses Werts wird ignoriert und sollte NULL sein. Eine Erläuterung der Vordergrund-und Hintergrundinformationen im Kontext dieser Methode finden `MaskBlt` Sie unter in der Windows SDK. Eine Liste der allgemeinen Raster Vorgangs Codes finden `BitBlt` Sie unter in der Windows SDK.

*rectDest*<br/>
Ein Verweis auf eine `RECT` -Struktur, die das Ziel identifiziert.

*pointSrc*<br/>
Eine `POINT` -Struktur, die die linke obere Ecke des Quell Rechtecks angibt.

*pointMask*<br/>
Eine `POINT` -Struktur, die die linke obere Ecke der Masken Bitmap angibt.

*pointDest*<br/>
Ein Verweis auf eine `POINT` -Struktur, die die linke obere Ecke des Ziel Rechtecks in logischen Einheiten bezeichnet.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode gilt nur für Windows NT, Version 4,0 und höher.

##  <a name="operator_hbitmap"></a>CImage:: Operator HBITMAP

Verwenden Sie diesen Operator, um das angefügte Windows-GDI `CImage` -Handle des-Objekts zu erhalten. Dieser Operator ist ein Typumwandlungs Operator, der die direkte Verwendung eines HBITMAP-Objekts unterstützt.

##  <a name="plgblt"></a>CImage::P lgblt

Führt eine Bitblock Übertragung von einem Rechteck in einem Quell Gerätekontext in ein Parallelogramm in einem Zielgeräte Kontext aus.

```
BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    HBITMAP hbmMask = NULL,
    int xMask = 0,
    int yMask = 0) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    const RECT& rectSrc,
    HBITMAP hbmMask = NULL,
    const POINT& pointMask = CPoint(0, 0)) const throw();
```

### <a name="parameters"></a>Parameter

*hDestDC*<br/>
Ein Handle für den Zielgeräte Kontext.

*pPoints*<br/>
Ein Zeiger auf ein Array von drei Punkten im logischen Raum, der drei Ecken des Ziel-parallelograms identifiziert. Die linke obere Ecke des Quell Rechtecks wird dem ersten Punkt in diesem Array zugeordnet, der oberen rechten Ecke des zweiten Punkts in diesem Array und der unteren linken Ecke zum dritten Punkt. Die untere rechte Ecke des Quell Rechtecks wird dem impliziten vierten Punkt im Parallelogram zugeordnet.

*hbmMask*<br/>
Ein Handle für eine optionale monochrome Bitmap, mit der die Farben des Quell Rechtecks maskiert werden.

*xSrc*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*ySrc*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*nSrcWidth*<br/>
Die Breite des Quell Rechtecks in logischen Einheiten.

*nSrcHeight*<br/>
Die Höhe des Quell Rechtecks in logischen Einheiten.

*xmask*<br/>
Die x-Koordinate der oberen linken Ecke der monochrome Bitmap.

*yMask*<br/>
Die y-Koordinate der oberen linken Ecke der monochrome Bitmap.

*rectSrc*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Koordinaten des Quell Rechtecks angibt.

*pointMask*<br/>
Eine [Punkt](/previous-versions/dd162805\(v=vs.85\)) Struktur, die die linke obere Ecke der Masken Bitmap angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn *hbmmask* eine gültige monochrome Bitmap identifiziert `PlgBit` , verwendet diese Bitmap, um die Bits der Farbdaten aus dem Quell Rechteck zu maskieren.

Diese Methode gilt nur für Windows NT, Version 4,0 und höher. Ausführlichere Informationen finden Sie unter [plgblt](/windows/win32/api/wingdi/nf-wingdi-plgblt) in der Windows SDK.

##  <a name="releasedc"></a>CImage:: ReleaseDC

Gibt den Gerätekontext frei.

```
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Hinweise

Da jeweils nur eine Bitmap in einem Gerätekontext ausgewählt werden kann, müssen Sie für jeden Aufruf `ReleaseDC` von [GetDC](#getdc)aufrufen.

##  <a name="releasegdiplus"></a>CImage:: releasegdiplus

Gibt die von GDI+ verwendeten Ressourcen frei.

```
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode muss aufgerufen werden, um Ressourcen freizugeben, die `CImage` von einem globalen Objekt zugeordnet werden. Weitere Informationen finden Sie unter [CImage:: CImage](#cimage).

##  <a name="save"></a>CImage:: Save

Speichert ein Bild im angegebenen Stream oder in der angegebenen Datei auf dem Datenträger.

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
Ein Zeiger auf ein COM-IStream-Objekt, das die Datei image Daten enthält.

*pszFileName*<br/>
Ein Zeiger auf den Dateinamen des Bilds.

*guidFileType*<br/>
Der Dateityp, in dem das Bild gespeichert werden soll. Kann einen der folgenden Werte annehmen:

- `ImageFormatBMP`Ein unkomprimiertes Bitmap-Bild.

- `ImageFormatPNG`Ein komprimiertes Bild für eine Portable Netzwerk Grafik (PNG).

- `ImageFormatJPEG`Ein mit JPEG komprimiertes Bild.

- `ImageFormatGIF`Ein mit GIF komprimiertes Bild.

> [!NOTE]
> Eine umfassende Liste der Konstanten finden Sie unter **Bild Datei Format Konstanten** in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standard.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion können Sie das Bild unter Verwendung eines angegebenen Namens und Typs speichern. Wenn der *guidfiletype* -Parameter nicht enthalten ist, wird die Dateierweiterung des Datei namens verwendet, um das Bildformat zu bestimmen. Wenn keine Erweiterung bereitgestellt wird, wird das Bild im BMP-Format gespeichert.

##  <a name="setcolortable"></a>CImage:: setcolortable

Legt die roten, grünen, blauen (RGB) Farbwerte für einen Bereich von Einträgen in der Palette des DIB-Abschnitts fest.

```
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Parameter

*iFirstColor*<br/>
Der Farbtabellen Index des ersten Eintrags, der festgelegt werden soll.

*nColors*<br/>
Die Anzahl der festzulegenden farbtabelleneinträge.

*prgbColors*<br/>
Ein Zeiger auf das Array von [rgbquad](/windows/win32/api/wingdi/ns-wingdi-rgbquad) -Strukturen, um die farbtabelleneinträge festzulegen.

### <a name="remarks"></a>Hinweise

Diese Methode unterstützt nur DIB-Abschnitts Bitmaps.

##  <a name="setpixel"></a>CImage:: SetPixel

Legt die Farbe eines Pixels an einer bestimmten Position in der Bitmap fest.

```
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die horizontale Position des festzulegenden Pixels.

*y*<br/>
Die vertikale Position des festzulegenden Pixels.

*Farbe*<br/>
Die Farbe, in der das Pixel festgelegt wird.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn die Pixelkoordinaten außerhalb des ausgewählten Clippingbereichs liegen.

##  <a name="setpixelindexed"></a>CImage:: setpixelindiziert

Legt die Pixelfarbe auf die Farbe fest, die sich in der Farbpalette unter *iIndex* befindet.

```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die horizontale Position des festzulegenden Pixels.

*y*<br/>
Die vertikale Position des festzulegenden Pixels.

*iIndex*<br/>
Der Index einer Farbe in der Farbpalette.

##  <a name="setpixelrgb"></a>CImage:: setpixelrgb

Legt das Pixel an den durch *x* und *y* angegebenen Positionen auf die durch *r*, *g*und *b*angegebenen Farben in einem roten, grünen, blauen (RGB) Bild fest.

```
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die horizontale Position des festzulegenden Pixels.

*y*<br/>
Die vertikale Position des festzulegenden Pixels.

*r*<br/>
Die Intensität der roten Farbe.

*g*<br/>
Die Intensität der grünen Farbe.

*b*<br/>
Die Intensität der blauen Farbe.

### <a name="remarks"></a>Hinweise

Die roten, grünen und blauen Parameter werden jeweils durch eine Zahl zwischen 0 und 255 dargestellt. Wenn Sie alle drei Parameter auf 0 (null) festlegen, ist die kombinierte resultierende Farbe schwarz. Wenn Sie alle drei Parameter auf 255 festlegen, ist die kombinierte resultierende Farbe weiß.

##  <a name="settransparentcolor"></a>CImage:: settransparentcolor

Legt eine Farbe an einer angegebenen indizierten Position als transparent fest.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Parameter

*iTransparentColor*<br/>
Der Index der Farbe, die auf transparent festgelegt werden soll, in einer Farbpalette. Wenn-1, wird keine Farbe auf transparent festgelegt.

### <a name="return-value"></a>Rückgabewert

Der Index der Farbe, die zuvor als transparent festgelegt wurde.

##  <a name="stretchblt"></a>CImage:: StretchBlt

Kopiert eine Bitmap aus dem Quell Gerätekontext in diesen aktuellen Gerätekontext.

```
BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Parameter

*hDestDC*<br/>
Ein Handle für den Zielgeräte Kontext.

*xDest*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*yDest*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*nDestWidth*<br/>
Die Breite des Ziel Rechtecks in logischen Einheiten.

*nDestHeight*<br/>
Die Höhe des Ziel Rechtecks in logischen Einheiten.

*dwROP*<br/>
Der auszuführende Raster Vorgang. Raster-Vorgangs Codes definieren genau, wie die Bits der Quelle, des Ziels und des Musters (wie durch den aktuell ausgewählten Pinsel definiert) zum bilden des Ziels kombiniert werden. Unter [BitBLT](/windows/win32/api/wingdi/nf-wingdi-bitblt) im Windows SDK finden Sie eine Liste mit anderen Code für den Raster Betrieb und deren Beschreibungen.

*rectDest*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die das Ziel identifiziert.

*xSrc*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*ySrc*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*nSrcWidth*<br/>
Die Breite des Quell Rechtecks in logischen Einheiten.

*nSrcHeight*<br/>
Die Höhe des Quell Rechtecks in logischen Einheiten.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` -Struktur, die die Quelle identifiziert.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [StretchBlt](/windows/win32/api/wingdi/nf-wingdi-stretchblt) in der Windows SDK.

##  <a name="transparentblt"></a>CImage:: TransparentBlt

Kopiert eine Bitmap aus dem Quell Gerätekontext in diesen aktuellen Gerätekontext.

```
BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    UINT crTransparent = CLR_INVALID) const throw();
```

### <a name="parameters"></a>Parameter

*hDestDC*<br/>
Ein Handle für den Zielgeräte Kontext.

*xDest*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*yDest*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Ziel Rechtecks.

*nDestWidth*<br/>
Die Breite des Ziel Rechtecks in logischen Einheiten.

*nDestHeight*<br/>
Die Höhe des Ziel Rechtecks in logischen Einheiten.

*crTransparent*<br/>
Die Farbe in der Quell Bitmap, die als transparent behandelt werden soll. Standardmäßig wird CLR_INVALID verwendet, um anzugeben, dass die Farbe, die derzeit als transparente Farbe des Bilds festgelegt ist, verwendet werden soll.

*rectDest*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die das Ziel identifiziert.

*xSrc*<br/>
Die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*ySrc*<br/>
Die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quell Rechtecks.

*nSrcWidth*<br/>
Die Breite des Quell Rechtecks in logischen Einheiten.

*nSrcHeight*<br/>
Die Höhe des Quell Rechtecks in logischen Einheiten.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` -Struktur, die die Quelle identifiziert.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls false.

### <a name="remarks"></a>Hinweise

`TransparentBlt`wird für Quell Bitmaps von 4 Bits pro Pixel und 8 Bits pro Pixel unterstützt. Verwenden Sie [CImage:: AlphaBlend](#alphablend) , um 32 Bits pro Pixel-Bitmaps mit Transparenz anzugeben.

### <a name="example"></a>Beispiel

```cpp
// Performs a transparent blit from the source image to the destination
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage,
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
    HDC hDstDC = NULL;
    BOOL bResult;

    if(pSrcImage == NULL || pDstImage == NULL)
    {
        // Invalid parameter
        return FALSE;
    }

    // Obtain a DC to the destination image
    hDstDC = pDstImage->GetDC();
    // Perform the blit
    bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

    // Release the destination DC
    pDstImage->ReleaseDC();

    return bResult;
}
```

## <a name="see-also"></a>Siehe auch

[MMXSwarm-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[SimpleImage-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Geräteunabhängige Bitmaps](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)<br/>
[Geräteunabhängige Bitmaps](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)
