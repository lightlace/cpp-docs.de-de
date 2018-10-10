---
title: CImage-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/01/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df61ebeea72a7cf860237b760288cc47ff353bf2
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890659"
---
# <a name="cimage-class"></a>CImage-Klasse

`CImage` Bietet erweiterte Bitmapunterstützung, einschließlich der Möglichkeit zum Laden und Speichern von Bildern in JPEG, GIF, BMP und Portable Network Graphics (PNG).

> [!IMPORTANT]
> Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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
|[CImage::AlphaBlend](#alphablend)|Zeigt die Bitmaps, die transparent oder halbtransparent Pixel aufweisen.|
|[CImage::Attach](#attach)|Fügt ein HBITMAP ab, um eine `CImage` Objekt. Kann mit nicht-DIB Abschnitt Bitmaps oder DIB Abschnitt Bitmaps verwendet werden.|
|[CImage::BitBlt](#bitblt)|Kopiert eine Bitmap aus dem Quellgerätekontext für diese aktuelle Gerätekontext.|
|[CImage::Create](#create)|Erstellt eine Bitmap der DIB-Abschnitt, und fügt ihn an das zuvor erstellte `CImage` Objekt.|
|[CImage::CreateEx](#createex)|Erstellt eine Bitmap des DIB-Abschnitt (mit zusätzlichen Parametern), und fügt ihn an das zuvor erstellte `CImage` Objekt.|
|[CImage::Destroy](#destroy)|Trennt das Bitmap aus der `CImage` Objekt aus, und löscht die Bitmap.|
|[CImage::Detach](#detach)|Trennt das Bitmap aus einem `CImage` Objekt.|
|[CImage::Draw](#draw)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck. `Draw` Streckt oder komprimiert die Bitmap an die Maße des Zielrechtecks, bei Bedarf entsprechend und behandelt alpha-blending und transparenten Farben.|
|[CImage::GetBits](#getbits)|Ruft einen Zeiger auf die tatsächliche Pixelwerte der Bitmap ab.|
|[CImage::GetBPP](#getbpp)|Ruft die Bits pro Pixel ab.|
|[CImage::GetColorTable](#getcolortable)|Ruft die Rot, Grün, Blau (RGB) Farbwerte aus einem Bereich von Einträgen in der Tabelle ab.|
|[CImage::GetDC](#getdc)|Ruft ab den Gerätekontext, die für den aktuelle Bitmap ausgewählt wird.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Sucht nach verfügbaren Bildformate und deren Beschreibungen.|
|[CImage::GetHeight](#getheight)|Ruft die Höhe des aktuellen Bilds in Pixel ab.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Sucht nach verfügbaren Bildformate und deren Beschreibungen.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Ruft die maximale Anzahl von Einträgen in der Color-Tabelle ab.|
|[CImage::GetPitch](#getpitch)|Ruft die Schriftbreite des aktuellen Bilds in Byte ab.|
|[CImage::GetPixel](#getpixel)|Ruft die Farbe des Pixels gemäß *x* und *y*.|
|[CImage::GetPixelAddress](#getpixeladdress)|Ruft die Adresse des ein angegebenes Pixel ab.|
|[CImage::GetTransparentColor](#gettransparentcolor)|Ruft die Position des die transparente Farbe in der Tabelle ab.|
|[CImage::GetWidth](#getwidth)|Ruft die Breite des aktuellen Bilds in Pixel ab.|
|[CImage::IsDIBSection](#isdibsection)|Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.|
|[CImage::IsIndexed](#isindexed)|Gibt an, dass eine indizierte Palette der Bitmap Farben zugeordnet sind.|
|[CImage::IsNull](#isnull)|Gibt an, wenn eine Quell-Bitmap aktuell geladen ist.|
|[CImage::IsTransparencySupported](#istransparencysupported)|Gibt an, ob die Anwendung transparente Bitmaps unterstützt.|
|[CImage::Load](#load)|Lädt ein Bild aus der angegebenen Datei.|
|[CImage::LoadFromResource](#loadfromresource)|Lädt ein Bild aus der angegebenen Ressource an.|
|[CImage::MaskBlt](#maskblt)|Kombiniert die Farbdaten für die Verwendung der angegebenen Maske und rastervorgang Quelle und Ziel-Bitmaps.|
|[CImage::PlgBlt](#plgblt)|Führt einen Bitblocktransfer aus einem Rechteck in einem Quellgerätekontext in ein Parallelogramm in einem Ziel-Gerätekontext.|
|[CImage::ReleaseDC](#releasedc)|Gibt den Gerätekontext frei, die mit abgerufen wurden [CImage::GetDC](#getdc).|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Gibt die von GDI + verwendete Ressourcen frei. Muss aufgerufen werden, um Ressourcen freizugeben, die durch eine globale erstellt `CImage` Objekt.|
|[CImage::Save](#save)|Speichert ein Bild als den angegebenen Typ. `Save` imageoptionen kann nicht angegeben werden.|
|[CImage::SetColorTable](#setcolortable)|Legt die Rot-, Grün-, Blaukomponenten RGB) Farbwerte in einem Bereich von Einträgen in der Tabelle "Farbe" das DIB-Abschnitt.|
|[CImage::SetPixel](#setpixel)|Das Pixel festgelegt auf den angegebenen Koordinaten auf die angegebene Farbe.|
|[CImage::SetPixelIndexed](#setpixelindexed)|Das Pixel festgelegt auf den angegebenen Koordinaten auf die Farbe am angegebenen Index der Palette.|
|[CImage::SetPixelRGB](#setpixelrgb)|Legt das Pixel an den angegebenen Koordinaten auf der angegebenen Rot, Grün, Blau (RGB) Wert fest.|
|[CImage::SetTransparentColor](#settransparentcolor)|Legt den Index der zu behandelnde Farbe als transparent. Nur eine Farbe in einer Palette kann transparent sein.|
|[CImage::StretchBlt](#stretchblt)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck, gestreckt oder komprimiert wird bei Bedarf die Bitmap an die Maße des Zielrechtecks, angepasst an.|
|[CImage::TransparentBlt](#transparentblt)|Kopiert eine Bitmap für die transparente Farbe aus dem Quellgerätekontext für diese aktuelle Gerätekontext.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CImage::operator HBITMAP](#operator_hbitmap)|Gibt zurück, das Windows-Handle, das angefügt wird, um die `CImage` Objekt.|

## <a name="remarks"></a>Hinweise

`CImage` nimmt die Bitmaps, die beiden Abschnitte geräteunabhängige Bitmap (DIB) sind; Sie können jedoch [erstellen](#create) oder [CImage::Load](#load) mit nur DIB-Abschnitte. Sie können eine nicht-DIB Abschnittsbitmap Anfügen einer `CImage` -Objekt mit [Anfügen](#attach), kann jedoch nicht klicken Sie dann die folgenden `CImage` Methoden, die nur Bitmaps, Abschnitt DIB unterstützen:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

Um zu bestimmen, wenn eine angefügte Bitmap ein DIB-Abschnitt ist, rufen [IsDibSection](#isdibsection).

> [!NOTE]
> In Visual Studio .NET 2003 sind diese Klasse zählt die Anzahl der `CImage` erstellten Objekte. Jedes Mal, wenn sich der Zähler auf 0 (null) die Funktion `GdiplusShutdown` automatisch aufgerufen, um die von GDI + verwendeten Ressourcen freizugeben. Dadurch wird sichergestellt, dass alle `CImage` direkt oder indirekt von DLLs erstellten Objekte sind immer ordnungsgemäß gelöscht werden und dass `GdiplusShutdown` wird nicht aufgerufen werden, von `DllMain`.

> [!NOTE]
> Globale `CImage` Objekte in eine DLL-Datei wird nicht empfohlen. Wenn Sie eine globale verwenden müssen `CImage` Objekt in eine DLL, Aufruf [CImage::ReleaseGDIPlus](#releasegdiplus) explizit von GDI + verwendete Ressourcen freigegeben.

`CImage` kann nicht ausgewählt werden, in eine neue [CDC](../../mfc/reference/cdc-class.md). `CImage` erstellt eine eigene HDC für das Image an. Da ein HBITMAP nur in einem HDC gleichzeitig ausgewählt werden kann, die HBITMAP zugeordneten der `CImage` kann nicht in einem anderen HDC ausgewählt werden. Wenn Sie eine CDC benötigen, Abrufen der HDC aus der `CImage` und für das [CDC::FromHandle] (.. /.. /MFC/Reference/CDC-Class.MD#cdc__fromhandle.

## <a name="example"></a>Beispiel

```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

Bei Verwendung von `CImage` in einem MFC-Projekt, beachten Sie die Member-Funktionen in Ihrem Projekt erwarten, dass einen Zeiger auf eine [CBitmap](../../mfc/reference/cbitmap-class.md) Objekt. Wenn Sie verwenden möchten `CImage` mit einer solchen Funktion, wie [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), verwenden [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), übergeben sie Ihre `CImage` HBITMAP, und verwenden Sie das zurückgegebene `CBitmap*`.  

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

Über `CImage`, haben Sie Zugriff auf die eigentlichen Bits an einem DIB-Abschnitt. Sie können eine `CImage` Objekt Sie zuvor einen Abschnitt Win32 HBITMAP oder DIB verwendet.

Sie können `CImage` von MFC oder ATL

> [!NOTE]
> Wenn Sie erstellen ein Projekt mit `CImage`, müssen Sie definieren `CString` bevor Sie einfügen `atlimage.h`. Wenn Ihr Projekt ATL ohne MFC verwendet, schließen Sie `atlstr.h` bevor Sie einfügen `atlimage.h`. Wenn Ihr Projekt verwendet MFC (oder wenn es sich um ein ATL-Projekt mit MFC-Unterstützung ist), schließen Sie `afxstr.h` bevor Sie einfügen `atlimage.h`.  
>   
> Sie müssen ebenso einschließen `atlimage.h` bevor Sie einfügen `atlimpl.cpp`. Ganz einfach dazu gehören `atlimage.h` in Ihre `stdafx.h`.

## <a name="requirements"></a>Anforderungen

**Header:** atlimage.h

##  <a name="alphablend"></a>  CImage::AlphaBlend

Zeigt die Bitmaps, die transparent oder halbtransparent Pixel aufweisen.

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
Handle für den Ziel-Gerätekontext.

*xDest*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*yDest*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*bSrcAlpha*<br/>
Ein alpha-Transparenz-Wert, auf die gesamte Quell-Bitmap verwendet werden. Der Standardwert 0xff (255) wird davon ausgegangen, dass Ihr Image nicht transparent ist und Sie pro-Pixel-Alphawerten nur verwenden möchten.

*bBlendOp*<br/>
Die Alpha-blending-Funktion für Quelle und Zielbitmaps, eine globale alpha-Wert, auf das gesamte Quell-Bitmap, und der Formatierungsinformationen für die Quell-Bitmap angewendet werden. Die Quelle und Ziel Blend-Funktionen sind derzeit auf AC_SRC_OVER beschränkt.

*pointDest*<br/>
Ein Verweis auf eine [Punkt](https://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die die oben links das Zielrechteck, in logischen Einheiten bezeichnet.

*nDestWidth*<br/>
Die Breite in logischen Einheiten des Zielrechtecks.

*nDestHeight*<br/>
Die Höhe in logischen Einheiten des Zielrechtecks.

*xSrc*<br/>
Die logische X-Koordinate der oberen linken Ecke des Quellrechtecks.

*ySrc*<br/>
Die logische y-Koordinate der oberen linken Ecke des Quellrechtecks.

*nSrcWidth*<br/>
Die Breite in logischen Einheiten des Quellrechtecks.

*nSrcHeight*<br/>
Die Höhe in logischen Einheiten des Quellrechtecks.

*rectDest*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel zu identifizieren.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` Struktur, die die Quelle zu identifizieren.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Alpha-Blend Bitmaps unterstützen die Kombination von Farbe auf einer pro-Pixel-Basis.

Wenn *bBlendOp* festgelegt ist die Standardeinstellung AC_SRC_OVER, befindet sich die Quell-Bitmap über die Zielbitmap basierend auf die Alphawerte Pixel der Quelle.  

##  <a name="attach"></a>  CImage::Attach

Fügt *hBitmap* zu einem `CImage` Objekt.

```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Parameter

*hBitmap*<br/>
Ein Handle für ein HBITMAP ab.

*eOrientation*<br/>
Gibt die Ausrichtung der Bitmap. Einer der folgenden Werte ist möglich:

- DIBOR_DEFAULT die Ausrichtung der Bitmap wird vom Betriebssystem bestimmt.

- DIBOR_BOTTOMUP sind die Zeilen der Bitmap in umgekehrter Reihenfolge. Dies bewirkt, dass [CImage::GetBits](#getbits) um einen Zeiger am Ende des Puffers Bitmap zurückzugeben und [CImage::GetPitch](#getpitch) eine negative Zahl zurückgegeben.

- DIBOR_TOPDOWN sind die Zeilen der Bitmap in von oben nach unten. Dies bewirkt, dass [CImage::GetBits](#getbits) um einen Zeiger auf das erste Byte des Puffers Bitmap zurückzugeben und [CImage::GetPitch](#getpitch) eine positive Zahl zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Bitmap kann entweder eine nicht-DIB Abschnittsbitmap oder eine Bitmap der DIB-Abschnitt sein. Finden Sie unter [IsDIBSection](#isdibsection) im Abschnitt für eine Liste der Methoden, mit denen Sie nur mit DIB Bitmaps.

##  <a name="bitblt"></a>  CImage::BitBlt

Kopiert eine Bitmap aus dem Quellgerätekontext für diese aktuelle Gerätekontext.

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
Das Ziel HDC.

*xDest*<br/>
Die logische X-Koordinate der oberen linken Ecke des Zielrechtecks.

*yDest*<br/>
Die logische y-Koordinate der oberen linken Ecke des Zielrechtecks.

*dwROP*<br/>
Der rastervorgang ausgeführt werden. Raster-Operationscodes definieren genau, wie die Bits von der Quelle, Ziel und das Muster kombinieren (gemäß der aktuell ausgewählten Pinsel), um das Ziel bilden. Finden Sie unter [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) im Windows SDK für eine Liste mit anderen rastervorgang Codes und deren Beschreibungen aufgeführt.

*pointDest*<br/>
Ein [Punkt](https://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, der angibt, in der oberen linken Ecke des Zielrechtecks.

*nDestWidth*<br/>
Die Breite in logischen Einheiten des Zielrechtecks.

*nDestHeight*<br/>
Die Höhe in logischen Einheiten des Zielrechtecks.

*xSrc*<br/>
Die logische X-Koordinate der oberen linken Ecke des Quellrechtecks.

*ySrc*<br/>
Die logische y-Koordinate der oberen linken Ecke des Quellrechtecks.

*rectDest*<br/>
Ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das Zielrechteck angibt.

*pointSrc*<br/>
Ein `POINT` Struktur, der angibt, in der oberen linken Ecke des Quellrechtecks.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) im Windows SDK.

##  <a name="cimage"></a>  CImage::CImage

Erstellt ein `CImage`-Objekt.

```
CImage() throw();
```

### <a name="remarks"></a>Hinweise

Sobald Sie das Objekt erstellt haben, rufen Sie [erstellen](#create), [Load](#load), [LoadFromResource](#loadfromresource), oder [Anfügen](#attach) eine Bitmap an das Objekt anzufügen.

**Beachten Sie** In Visual Studio kann diese Klasse zählt die Anzahl der `CImage` erstellten Objekte. Jedes Mal, wenn sich der Zähler auf 0 (null) die Funktion `GdiplusShutdown` automatisch aufgerufen, um die von GDI + verwendeten Ressourcen freizugeben. Dadurch wird sichergestellt, dass alle `CImage` direkt oder indirekt von DLLs erstellten Objekte sind immer ordnungsgemäß gelöscht werden und dass `GdiplusShutdown` aus DllMain nicht aufgerufen wird.

Globale `CImage` Objekte in eine DLL-Datei wird nicht empfohlen. Wenn Sie eine globale verwenden müssen `CImage` Objekt in eine DLL, Aufruf [CImage::ReleaseGDIPlus](#releasegdiplus) explizit von GDI + verwendete Ressourcen freigegeben.

##  <a name="create"></a>  CImage::Create

Erstellt eine `CImage` bitmap aus, und fügen Sie ihn an das zuvor erstellte `CImage` Objekt.

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

*nHeight*<br/>
Die Höhe der `CImage` Bitmap in Pixel. Wenn *nHeight* positiv ist, wird die Bitmap ist einem DIB von unten nach oben und dessen Ursprung die linke untere Ecke. Wenn *nHeight* ist negativ, wird die Bitmap eine DIB von oben nach unten und dessen Ursprung ist die obere linke Ecke.

*nBPP*<br/>
Die Anzahl von Bits pro Pixel in der Bitmap. In der Regel 4, 8, 16, 24 oder 32. 1 für die monochrome Bitmaps oder Masken kann sein.

*dwFlags*<br/>
Gibt an, wenn das Bitmapobjekt einen alpha-Kanal verfügt. Eine Kombination von 0 (null) oder mehrere der folgenden Werte sind möglich:

- *CreateAlphaChannel* kann nur verwendet werden, wenn *nBPP* ist 32. und *eCompression* BI_RGB ist. Wenn angegeben, hat das erstellte Image einen Alphawerte (Transparenz) Wert für jedes Pixel, die in der 4. Byte der einzelnen Pixel (in einem nicht-alphanumerischen 32-Bit-Abbild nicht verwendeten) gespeichert. Diese alpha-Kanal wird automatisch verwendet, beim Aufrufen von [CImage::AlphaBlend](#alphablend).

> [!NOTE]
> Aufrufe [CImage::Draw](#draw), Bilder mit einem Alphakanal werden automatisch alpha gemischt an das Ziel.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="createex"></a>  CImage::CreateEx

Erstellt eine `CImage` bitmap aus, und fügen Sie ihn an das zuvor erstellte `CImage` Objekt.

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

*nHeight*<br/>
Die Höhe der `CImage` Bitmap in Pixel. Wenn *nHeight* positiv ist, wird die Bitmap ist einem DIB von unten nach oben und dessen Ursprung die linke untere Ecke. Wenn *nHeight* ist negativ, wird die Bitmap eine DIB von oben nach unten und dessen Ursprung ist die obere linke Ecke.

*nBPP*<br/>
Die Anzahl von Bits pro Pixel in der Bitmap. In der Regel 4, 8, 16, 24 oder 32. 1 für die monochrome Bitmaps oder Masken kann sein.

*eCompression*<br/>
Gibt den Typ der Komprimierung für komprimierte Bottom-up-Bitmap (von oben nach unten DIBs können nicht komprimiert werden). Kann einer der folgenden Werte sein:

- BI_RGB Format werden nicht komprimiert. Die Angabe dieses Werts beim Aufrufen von `CImage::CreateEx` entspricht dem Aufruf `CImage::Create`.

- BI_BITFIELDS Format werden nicht komprimiert, und die Farbtabelle besteht aus drei der folgenden DWORD-Farbe Masken, mit die die Komponenten roten, grünen und blauen bzw. der einzelnen Pixel angegeben. Dies ist gültig, wenn mit 16 und 32-Bpp-Bitmaps verwendet.

*pdwBitfields*<br/>
Nur verwendet, wenn *eCompression* festgelegt ist, BI_BITFIELDS, andernfalls diese muss NULL sein. Ein Zeiger auf ein Array von drei DWORD Bitmasken, die angeben, welche Bits der einzelnen Pixel bzw. für die Rot-, Grün- und blauen-Komponenten der Farbe verwendet werden. Weitere Informationen zu den Einschränkungen für die Bitfelder finden Sie unter [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) im Windows SDK.

*dwFlags*<br/>
Gibt an, wenn das Bitmapobjekt einen alpha-Kanal verfügt. Eine Kombination von 0 (null) oder mehrere der folgenden Werte sind möglich:

- *CreateAlphaChannel* kann nur verwendet werden, wenn *nBPP* ist 32. und *eCompression* BI_RGB ist. Wenn angegeben, hat das erstellte Image einen Alphawerte (Transparenz) Wert für jedes Pixel, die in der 4. Byte der einzelnen Pixel (in einem nicht-alphanumerischen 32-Bit-Abbild nicht verwendeten) gespeichert. Diese alpha-Kanal wird automatisch verwendet, beim Aufrufen von [CImage::AlphaBlend](#alphablend).

   > [!NOTE]
   > Aufrufe [CImage::Draw](#draw), Bilder mit einem Alphakanal werden automatisch alpha gemischt an das Ziel.

### <a name="return-value"></a>Rückgabewert

Bei Erfolg TRUE. Andernfalls "false".

### <a name="example"></a>Beispiel

Das folgende Beispiel erstellt eine 100 x 100 Pixel-Bitmap, die mithilfe von 16 Bits jedes Pixel zu codieren. In einem angegebenen 16-Bit-Pixel Bits 0-3, codieren die Rotkomponente, Bits 4-7 codieren, Grün und Bits 8 bis 11 codieren Blau. Die verbleibenden 4 Bits werden nicht verwendet.  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

##  <a name="destroy"></a>  CImage::Destroy

Trennt das Bitmap aus der `CImage` Objekt aus, und löscht die Bitmap.

```
void Destroy() throw();
```

##  <a name="detach"></a>  CImage::Detach

Trennt eine Bitmap aus einem `CImage` Objekt.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für die Bitmap getrennt oder NULL, wenn keine Bitmap zugeordnet ist.

##  <a name="draw"></a>  CImage::Draw

Kopiert eine Bitmap aus den Quellgerätekontext an den aktuellen Gerätekontext an.

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
Ein Handle für den Ziel-Gerätekontext.

*xDest*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*yDest*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*nDestWidth*<br/>
Die Breite in logischen Einheiten des Zielrechtecks.

*nDestHeight*<br/>
Die Höhe in logischen Einheiten des Zielrechtecks.

*xSrc*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*ySrc*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*nSrcWidth*<br/>
Die Breite in logischen Einheiten des Quellrechtecks.

*nSrcHeight*<br/>
Die Höhe in logischen Einheiten des Quellrechtecks.

*rectDest*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel zu identifizieren.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` Struktur, die die Quelle zu identifizieren.

*pointDest*<br/>
Ein Verweis auf eine [Punkt](https://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die die oben links das Zielrechteck, in logischen Einheiten bezeichnet.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

`Draw` Führt den gleichen Vorgang wie [StretchBlt](#stretchblt), es sei denn, das Image eine transparente Farbe oder einen Alphakanal enthält. In diesem Fall `Draw` führt den gleichen Vorgang entweder als [TransparentBlt](#transparentblt) oder [AlphaBlend](#alphablend) nach Bedarf.

Für Versionen von `Draw` , die einem Quellrechteck nicht angeben, das gesamte Quellbild ist die Standardeinstellung. Für die Version des `Draw` , wird eine Größe für das Zielrechteck angeben, die Größe des Quellbilds ist die Standardeinstellung und keine größenanpassung oder verkleinern auftritt.

##  <a name="getbits"></a>  CImage::GetBits

Ruft einen Zeiger auf die tatsächliche Bitwerte ein angegebenes Pixel in einer Bitmap ab.

```
void* GetBits() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Bitmap-Puffer. Wenn die Bitmap eine Bottom-up-DIB ist, nahezu der Zeiger weist das Ende des Puffers. Wenn die Bitmap eine DIB von oben nach unten der Zeiger verweist auf das erste Byte des Puffers ist.

### <a name="remarks"></a>Hinweise

Verwenden der this-Zeiger, zusammen mit den Rückgabewert von [GetPitch](#getpitch), Sie suchen und ändern Sie die einzelnen Pixel in einem Bild.

> [!NOTE]
> Diese Methode unterstützt nur Bitmaps, Abschnitt DIB; Folglich Sie Zugriff auf die Pixel von einer `CImage` Objekt die gleiche Weise, die Sie die Pixel eines Abschnitts DIB würde. Der zurückgegebene Zeiger verweist auf das Pixel an der Position (0, 0).

##  <a name="getbpp"></a>  CImage::GetBPP

Ruft den Wert für Bits pro Pixel.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bits pro Pixel.

### <a name="remarks"></a>Hinweise

Dieser Wert bestimmt die Anzahl der Bits, die jedes Pixel zu definieren und die maximale Anzahl von Farben in der Bitmap.

Die Bits pro Pixel ist in der Regel 1, 4, 8, 16, 24 oder 32. Finden Sie unter den `biBitCount` Mitglied [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) im Windows SDK für Weitere Informationen zu diesen Wert.

##  <a name="getcolortable"></a>  CImage::GetColorTable

Ruft die Rot, Grün, Blau (RGB) Farbwerte aus einem Bereich von Einträgen in der Palette des Abschnitts DIB ab.

```
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Parameter

*iFirstColor*<br/>
Die Farbe Tabellenindex des ersten Eintrags abrufen.

*nColors*<br/>
Die Anzahl der Farbtabelleneinträge abrufen.

*prgbColors*<br/>
Ein Zeiger auf das Array von [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) Strukturen, um die Farbe abrufen Tabelle Einträge.

##  <a name="getdc"></a>  CImage::GetDC

Ruft den Gerätekontext, die dem Image darin ausgewählt verfügt derzeit über ab.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für einen Gerätekontext.

### <a name="remarks"></a>Hinweise

Für jeden Aufruf von `GetDC`, benötigen Sie einen nachfolgenden Aufruf von [ReleaseDC](#releasedc).

##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString

Sucht nach Bildformate verfügbar für das Speichern von Bildern.

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
Ein Verweis auf ein `CSimpleString`-Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen.

*aguidFileTypes*<br/>
Ein Array von GUIDs, wobei jedes Element auf einen der Dateitypen in der Zeichenfolge entspricht. Im Beispiel in *PszAllFilesDescription* folgenden *AguidFileTypes*[0] GUID_NULL ist und die verbleibenden Arraywerte sind die Image-Dateiformate, die vom aktuellen Betriebssystem unterstützt.

> [!NOTE]
> Eine vollständige Liste von Konstanten, finden Sie unter **Image Format Dateikonstanten** im Windows SDK.

*pszAllFilesDescription*<br/>
Wenn dieser Parameter nicht NULL ist, müssen die Filterzeichenfolge ein zusätzlichen Filter am Anfang der Liste. Dieser Filter wird den aktuellen Wert der haben *PszAllFilesDescription* für seine Beschreibung und akzeptiert Erweiterung von jeder anderen Exporter-Tool in der Liste unterstützt werden.

Zum Beispiel:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
_T("All Image Files"));
```


*dwExclude*<br/>
Satz von Bitflags, welche Dateitypen ausschließen aus der Liste angeben. Zulässigen Flags sind:

- `excludeGIF` = 0 x 01 schließt GIF-Dateien.

- `excludeBMP` = 0 x 02 schließt BMP (Bitmap Windows)-Dateien.

- `excludeEMF` = 0 x 04 schließt EMF (Enhanced Metafile)-Dateien.

- `excludeWMF` = 0 x 08 schließt WMF (Windows Metafile)-Dateien.

- `excludeJPEG` = 0 x 10 schließt JPEG-Dateien.

- `excludePNG` = 0 x 20 schließt PNG-Dateien.

- `excludeTIFF` = 0 x 40 schließt TIFF-Dateien.

- `excludeIcon` = 0 x 80 schließt ICO-(Symbol "Windows")-Dateien.

- `excludeOther` = 0 x 80000000 schließt jeder andere Dateityp oben nicht aufgeführt sind.

- `excludeDefaultLoad` = 0 für das Laden, alle Dateien, die standardmäßig die Typen enthalten sind

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Zum Speichern, werden diese Dateien standardmäßig ausgeschlossen, da in der Regel besondere Anforderungen haben.

*chSeparator*<br/>
Das Trennzeichen zwischen den Bildformate verwendet wird. Finden Sie unter **"Hinweise"** für Weitere Informationen.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Sie können die resultierende Zeichenfolge übergeben, mit Ihrem MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) Objekt, das die Dateierweiterungen der verfügbaren Images verfügbar zu machen das Dialogfeld "Datei speichern unter" formatiert.

Der Parameter *StrExporter* weist das Format auf:

Datei description0&#124;\*.ext0&#124;filedescription1&#124;\*. erw1&#124;.. .file Beschreibung *n*&#124;\*ext *n*&#124;&#124;

wobei "&#124;" wird durch das Trennzeichen angegeben `chSeparator`. Zum Beispiel:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Verwenden Sie das Standardtrennzeichen "&#124;" Wenn Sie diese Zeichenfolge, um einer MFC übergeben `CFileDialog` Objekt. Verwenden Sie das null-Trennzeichen '\0', wenn Sie diese Zeichenfolge, um ein allgemeines Dialogfeld Datei speichern übergeben.

##  <a name="getheight"></a>  CImage::GetHeight

Ruft die Höhe in Pixel eines Bilds ab.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Höhe in Pixel eines Bilds.

##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString

Sucht nach verfügbaren Bildformate zum Laden von Bildern.

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
Ein Verweis auf ein `CSimpleString`-Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen.

*aguidFileTypes*<br/>
Ein Array von GUIDs, wobei jedes Element auf einen der Dateitypen in der Zeichenfolge entspricht. Im Beispiel in *PszAllFilesDescription* folgenden *AguidFileTypes*[0] GUID_NULL, durch die verbleibenden Arraywerte sind die Image-Dateiformate, die vom aktuellen Betriebssystem unterstützt.

> [!NOTE]
> Eine vollständige Liste von Konstanten, finden Sie unter **Image Format Dateikonstanten** im Windows SDK.

*pszAllFilesDescription*<br/>
Wenn dieser Parameter nicht NULL ist, müssen die Filterzeichenfolge ein zusätzlichen Filter am Anfang der Liste. Dieser Filter wird den aktuellen Wert der haben *PszAllFilesDescription* für seine Beschreibung und akzeptiert Erweiterung von jeder anderen Exporter-Tool in der Liste unterstützt werden.

Zum Beispiel:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
_T("All Image Files"));
```


*dwExclude*<br/>
Satz von Bitflags, welche Dateitypen ausschließen aus der Liste angeben. Zulässigen Flags sind:

- `excludeGIF` = 0 x 01 schließt GIF-Dateien.

- `excludeBMP` = 0 x 02 schließt BMP (Bitmap Windows)-Dateien.

- `excludeEMF` = 0 x 04 schließt EMF (Enhanced Metafile)-Dateien.

- `excludeWMF` = 0 x 08 schließt WMF (Windows Metafile)-Dateien.

- `excludeJPEG` = 0 x 10 schließt JPEG-Dateien.

- `excludePNG` = 0 x 20 schließt PNG-Dateien.

- `excludeTIFF` = 0 x 40 schließt TIFF-Dateien.

- `excludeIcon` = 0 x 80 schließt ICO-(Symbol "Windows")-Dateien.

- `excludeOther` = 0 x 80000000 schließt jeder andere Dateityp oben nicht aufgeführt sind.

- `excludeDefaultLoad` = 0 für das Laden, alle Dateien, die standardmäßig die Typen enthalten sind

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Zum Speichern, werden diese Dateien standardmäßig ausgeschlossen, da in der Regel besondere Anforderungen haben.

*chSeparator*<br/>
Das Trennzeichen zwischen den Bildformate verwendet wird. Finden Sie unter **"Hinweise"** für Weitere Informationen.

### <a name="remarks"></a>Hinweise

Sie können die resultierende Zeichenfolge übergeben, mit Ihrem MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) Formate, Objekt, das die Dateierweiterungen der verfügbaren Images verfügbar zu machen die **Datei öffnen** Dialogfeld.

Der Parameter *StrImporter* weist das Format auf:

Datei description0&#124;\*.ext0&#124;filedescription1&#124;\*. erw1&#124;.. .file Beschreibung *n*&#124;\*ext *n*&#124;&#124;

in denen "&#124;" ist das Trennzeichen, anhand des *ChSeparator*. Zum Beispiel:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Verwenden Sie das Standardtrennzeichen "&#124;" Wenn Sie diese Zeichenfolge, um einer MFC übergeben `CFileDialog` Objekt. Die null-Trennzeichen '\0' verwenden, wenn Sie diese Zeichenfolge in eine allgemeine übergeben **Datei öffnen** Dialogfeld.

##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries

Ruft die maximale Anzahl von Einträgen in der Color-Tabelle ab.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Einträge in der Color-Tabelle.

### <a name="remarks"></a>Hinweise

Diese Methode unterstützt nur Bitmaps, Abschnitt DIB.

##  <a name="getpitch"></a>  CImage::GetPitch

Ruft die Schriftbreite eines Bilds ab.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Schriftbreite des Bilds. Wenn der zurückgegebene Wert negativ ist, die Bitmap ist eine von unten nach oben DIB und dessen Ursprung ist die linke untere Ecke. Wenn der Rückgabewert positiv ist, die Bitmap ist einem DIB von oben nach unten, und dessen Ursprung ist die obere linke Ecke.

### <a name="remarks"></a>Hinweise

Die Schriftbreite ist die Entfernung in Bytes, die zwischen zwei Speicheradressen, die den Anfang einer Bitmapzeile darstellen und dem Beginn der nächsten Bitmapzeile. Da Tonhöhe in Bytes angegeben ist, kann die Tonhöhe eines Bilds Sie das Pixelformat zu ermitteln. Die Schriftbreite kann auch mit zusätzlichen Arbeitsspeicher reserviert für die Bitmap enthalten.

Verwendung `GetPitch` mit [GetBits](#getbits) einzelnen Pixel eines Bilds zu finden.

> [!NOTE]
> Diese Methode unterstützt nur Bitmaps, Abschnitt DIB.

##  <a name="getpixel"></a>  CImage::GetPixel

Ruft die Farbe des Pixels an die vom angegebenen Speicherort *x* und *y*.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die X-Koordinate des Pixels.

*y*<br/>
Die y-Koordinate des Pixels.

### <a name="return-value"></a>Rückgabewert

Der Rot, Grün, Blau (RGB)-Wert des Pixels. Wenn das Pixel außerhalb des aktuellen Ausschneidebereichs ist, ist der Rückgabewert CLR_INVALID an.

##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress

Ruft die genaue Adresse eines Pixels ab.

```
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die X-Koordinate des Pixels.

*y*<br/>
Die y-Koordinate des Pixels.

### <a name="remarks"></a>Hinweise

Die Adresse wird bestimmt, gemäß den Koordinaten eines Pixels, der die Schriftbreite der Bitmap und die Bits pro Pixel.

Für die Formate, die weniger als 8 Bits pro Pixel aufweisen, gibt diese Methode die Adresse des Bytes, die das Pixel enthält. Wenn Ihr Bildformat 4 Bits pro Pixel ist z. B. `GetPixelAddress` gibt die Adresse des ersten Pixels in das Byte, und Sie müssen für 2 Pixel pro Byte berechnen.

> [!NOTE]
> Diese Methode unterstützt nur Bitmaps, Abschnitt DIB.

##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor

Ruft ab, die indizierte Position des die transparente Farbe in der Farbpalette.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Index, der die transparente Farbe.

##  <a name="getwidth"></a>  CImage::GetWidth

Ruft die Breite in Pixel eines Bilds ab.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Breite der Bitmap in Pixel.

##  <a name="isdibsection"></a>  CImage::IsDIBSection

Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die angefügte Bitmap ein DIB-Abschnitt ist. Andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn die Bitmap nicht um ein DIB-Abschnitt ist, können keine der folgenden `CImage` Methoden, die nur Bitmaps, Abschnitt DIB unterstützen:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

##  <a name="isindexed"></a>  CImage::IsIndexed

Bestimmt, ob eine Farbpalette der Bitmap Pixel zugeordnet sind.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Rückgabewert

True, wenn indiziert. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode gibt "true" zurück, nur dann, wenn die Bitmap mit 8-Bit ist (256 Farben) oder weniger.

> [!NOTE]
> Diese Methode unterstützt nur Bitmaps, Abschnitt DIB.

##  <a name="isnull"></a>  CImage::IsNull

Bestimmt, ob eine Bitmap momentan geladen ist.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode gibt TRUE zurück, wenn eine Bitmap nicht gerade geladen wird. andernfalls "false".

##  <a name="istransparencysupported"></a>  IsTransparencySupported

Gibt an, ob die Anwendung transparente Bitmaps unterstützt.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die aktuelle Plattform Transparenz unterstützt. Andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn der Rückgabewert ungleich NULL ist, und Transparenz unterstützt, einen Aufruf von [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), oder [zeichnen](#draw) transparente Farben behandelt wird.

##  <a name="load"></a>  CImage::Load

Lädt ein Bild.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>Parameter

*pszFileName*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Bilddatei, die geladen werden.

*pStream*<br/>
Ein Zeiger auf einen Datenstrom mit dem Namen der Bilddatei, die geladen werden.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Lädt das angegebene Bild *PszFileName* oder *pStream*.

Gültiges Image-Typen sind, BMP, GIF, JPEG, PNG und TIFF.

##  <a name="loadfromresource"></a>  CImage::LoadFromResource

Lädt ein Bild aus einer BITMAP-Ressource.

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
Handle für eine Instanz des Moduls mit dem Image geladen werden.

*pszResourceName*<br/>
Ein Zeiger auf die Zeichenfolge, die mit dem Namen der Ressource, die zu ladenden Bilds enthält.

*nIDResource*<br/>
Die ID der Ressource geladen werden soll.

### <a name="remarks"></a>Hinweise

Die Ressource muss vom Typ BITMAP sein.

##  <a name="maskblt"></a>  CImage::MaskBlt

Kombiniert die Farbdaten für die Verwendung der angegebenen Maske und rastervorgang Quelle und Ziel-Bitmaps.

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
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*yDest*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*nDestWidth*<br/>
Die Breite in logischen Einheiten, der die Zielbitmap Rechteck und Quelle.

*nDestHeight*<br/>
Die Höhe in logischen Einheiten, der die Zielbitmap Rechteck und Quelle.

*xSrc*<br/>
Die logische X-Koordinate der oberen linken Ecke der Quellbitmap.

*ySrc*<br/>
Die logische y-Koordinate der oberen linken Ecke der Quellbitmap.

*hbmMask*<br/>
Handle für die monochrome Maske-Bitmap, kombiniert mit der Farbe Bitmap im Quellgerätekontext.

*xMask*<br/>
Der horizontale Pixel-Offset für die Maskenbitmap, die gemäß der *HbmMask* Parameter.

*yMask*<br/>
Der vertikale Pixel-Offset für die Maskenbitmap, die gemäß der *HbmMask* Parameter.

*dwROP*<br/>
Gibt an, Vordergrund und Hintergrund ternäre rastervorgangscode, die die Methode verwendet, um die Kombination aus Quell-und Zieldaten zu steuern. Die Hintergrund-Raster Vorgangscode wird in das höherwertige Wort dieses Werts das höherwertige Byte gespeichert. der Vordergrund Raster Vorgangscode wird in das höherwertige Wort dieses Werts das niederwertige Byte gespeichert. das niederwertige Wort von dieser Wert wird ignoriert, und sollte Null sein. Eine Beschreibung der Vordergrund- und Hintergrundfarbe im Kontext dieser Methode finden Sie unter `MaskBlt` im Windows SDK. Eine Liste der allgemeinen rastervorgangscode, finden Sie unter `BitBlt` im Windows SDK.

*rectDest*<br/>
Ein Verweis auf eine `RECT` Struktur, die das Ziel zu identifizieren.

*pointSrc*<br/>
Ein `POINT` Struktur, der angibt, in der oberen linken Ecke des Quellrechtecks.

*pointMask*<br/>
Ein `POINT` -Struktur, die links oben auf der Maskenbitmap für die angibt.

*pointDest*<br/>
Ein Verweis auf eine `POINT` Struktur, die die oben links das Zielrechteck, in logischen Einheiten bezeichnet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode gilt für Windows NT, Version 4.0 und höher vorgesehen.

##  <a name="operator_hbitmap"></a>  CImage::operator HBITMAP

Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle des erhalten die `CImage` Objekt. Dieser Operator ist ein Umwandlungsoperator, die direkte Verwendung von ein HBITMAP-Objekt unterstützt.

##  <a name="plgblt"></a>  CImage::PlgBlt

Führt einen Bitblocktransfer aus einem Rechteck in einem Quellgerätekontext in ein Parallelogramm in einem Ziel-Gerätekontext.

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
Ein Handle für den Ziel-Gerätekontext.

*pPoints*<br/>
Ein Zeiger auf ein Array von drei Punkten in logischer Speicherplatz, die drei Ecken des Zielparallelogramms zu identifizieren. Der erste Punkt in dieses Array ab, der oberen rechten Ecke zum zweiten Punkt in diesem Array und der unteren linken Ecke aus, dem dritten Punkt wird der oberen linken Ecke des Quellrechtecks zugeordnet. Der unteren rechten Ecke des Quellrechtecks wird bis zum vierten implizite Punkt in der Parallelogramm zugeordnet.

*hbmMask*<br/>
Ein Handle für eine optionale monochrome Bitmap, die verwendet wird, um die Farben des Quellrechtecks zu maskieren.

*xSrc*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*ySrc*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*nSrcWidth*<br/>
Die Breite in logischen Einheiten des Quellrechtecks.

*nSrcHeight*<br/>
Die Höhe in logischen Einheiten des Quellrechtecks.

*xMask*<br/>
Die X-Koordinate der oberen linken Ecke der monochrome Bitmap.

*yMask*<br/>
Die y-Koordinate der oberen linken Ecke der monochrome Bitmap.

*rectSrc*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die mit den angegebenen Koordinaten des Quellrechtecks.

*pointMask*<br/>
Ein [Punkt](https://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die links oben auf der Maskenbitmap für die angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn *HbmMask* identifiziert eine gültige monochrome Bitmap `PlgBit` diese Bitmap verwendet, um die Bits der Farbdaten vom Quellrechtecks zu maskieren.

Diese Methode gilt für Windows NT, Version 4.0 und höher vorgesehen. Finden Sie unter [PlgBlt](/windows/desktop/api/wingdi/nf-wingdi-plgblt) im Windows SDK für ausführlichere Informationen.

##  <a name="releasedc"></a>  CImage::ReleaseDC

Gibt den Gerätekontext frei.

```
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Hinweise

Da nur eine Bitmap für einen Gerätekontext gleichzeitig ausgewählt werden kann, müssen Sie aufrufen `ReleaseDC` für jeden Aufruf von [GetDC](#getdc).

##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus

Gibt die von GDI + verwendete Ressourcen frei.

```
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode muss aufgerufen werden, um Ressourcen freizugeben, die von einer globalen zugeordneten `CImage` Objekt. Finden Sie unter [CImage::CImage](#cimage).

##  <a name="save"></a>  CImage::Save

Speichert ein Bild in den angegebenen Stream oder eine Datei auf dem Datenträger.

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
Ein Zeiger auf ein COM-IStream-Objekt, das die Bilddaten für die Datei enthält.

*pszFileName*<br/>
Ein Zeiger auf den Dateinamen für das Image.

*guidFileType*<br/>
Der Dateityp zum Speichern des Bilds als. Einer der folgenden Werte ist möglich:

- `ImageFormatBMP` Eine nicht komprimierte Bitmap-Bild.

- `ImageFormatPNG` Ein komprimiertes Bild der Grafik PNG (Portable Network).

- `ImageFormatJPEG` Eine komprimierte JPEG-Bild.

- `ImageFormatGIF` Ein komprimiertes GIF-Bild.

> [!NOTE]
> Eine vollständige Liste von Konstanten, finden Sie unter **Image Format Dateikonstanten** im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um das Image mithilfe eines angegebenen Namens und Typs zu speichern. Wenn die *GuidFileType* Parameter nicht angegeben, den Dateinamen die Erweiterung wird verwendet, um das Image-Format zu bestimmen. Wenn keine Erweiterung angegeben wird, wird das Bild im BMP-Format gespeichert werden.

##  <a name="setcolortable"></a>  CImage::SetColorTable

Legt die Rot, Grün, Blau (RGB) Farbwerte für einen Bereich von Einträgen in der Palette des Abschnitts DIB fest.

```
void SetColorTable(
    UINT iFirstColor, 
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Parameter

*iFirstColor*<br/>
Der Color-Tabelle-Index des ersten Eintrags festgelegt.

*nColors*<br/>
Die Anzahl der Farbtabelleneinträge festlegen.

*prgbColors*<br/>
Ein Zeiger auf das Array von [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) Strukturen, die die Farbe festgelegt Tabelle Einträge.

### <a name="remarks"></a>Hinweise

Diese Methode unterstützt nur Bitmaps, Abschnitt DIB.

##  <a name="setpixel"></a>  CImage::SetPixel

Legt die Farbe eines Pixels an einer bestimmten Position in der Bitmap an.

```
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die horizontale Position des festzulegenden Pixels.

*y*<br/>
Die vertikale Position des festzulegenden Pixels.

*Farbe*<br/>
Die Farbe, die das Pixel festgelegt werden.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn das Pixel liegen außerhalb des ausgewählten Clippingbereichs koordiniert.

##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed

Legt die Farbe des Pixels auf die Farbe am *iIndex* in der Farbpalette.

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

##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB

Legt die Pixel auf den von angegebenen Speicherorten *x* und *y* auf die Farben, angegeben durch *r*, *g*, und *b*, in das ein Rot, Grün, Blau (RGB)-Image.

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
Die Intensität der Farbe Rot.

*g*<br/>
Die Intensität der Farbe Grün.

*b*<br/>
Die Intensität der Farbe Blau.

### <a name="remarks"></a>Hinweise

Die Rot-, Grün- und Blau-Parameter werden jeweils durch eine Zahl zwischen 0 und 255 dargestellt. Wenn Sie alle drei Parameter auf 0 (null) festlegen, ist die kombinierte resultierende Farbe Schwarz. Wenn Sie alle drei Parameter auf 255 festgelegt haben, ist die kombinierte resultierende Farbe Weiß.

##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor

Legt eine Farbe an einer bestimmten indizierten Position als transparent fest.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Parameter

*iTransparentColor*<br/>
Der Index, in der eine Farbpalette, der die Farbe, die auf transparent festgelegt. Wenn-1 ist, wird keine Farbe auf transparent festgelegt.

### <a name="return-value"></a>Rückgabewert

Der Index der Farbe festlegen zuvor als transparent.

##  <a name="stretchblt"></a>  CImage::StretchBlt

Kopiert eine Bitmap aus dem Quellgerätekontext für diese aktuelle Gerätekontext.

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
Ein Handle für den Ziel-Gerätekontext.

*xDest*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*yDest*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*nDestWidth*<br/>
Die Breite in logischen Einheiten des Zielrechtecks.

*nDestHeight*<br/>
Die Höhe in logischen Einheiten des Zielrechtecks.

*dwROP*<br/>
Der rastervorgang ausgeführt werden. Raster-Operationscodes definieren genau, wie die Bits von der Quelle, Ziel und das Muster kombinieren (gemäß der aktuell ausgewählten Pinsel), um das Ziel bilden. Finden Sie unter [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) im Windows SDK für eine Liste mit anderen rastervorgang Codes und deren Beschreibungen aufgeführt.

*rectDest*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel zu identifizieren.

*xSrc*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*ySrc*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*nSrcWidth*<br/>
Die Breite in logischen Einheiten des Quellrechtecks.

*nSrcHeight*<br/>
Die Höhe in logischen Einheiten des Quellrechtecks.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` Struktur, die die Quelle zu identifizieren.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [StretchBlt](/windows/desktop/api/wingdi/nf-wingdi-stretchblt) im Windows SDK.

##  <a name="transparentblt"></a>  CImage::TransparentBlt

Kopiert eine Bitmap aus dem Quellgerätekontext für diese aktuelle Gerätekontext.

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
Ein Handle für den Ziel-Gerätekontext.

*xDest*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*yDest*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.

*nDestWidth*<br/>
Die Breite in logischen Einheiten des Zielrechtecks.

*nDestHeight*<br/>
Die Höhe in logischen Einheiten des Zielrechtecks.

*crTransparent*<br/>
Die Farbe in der Quell-Bitmap, als transparent behandelt werden sollen. Standardmäßig CLR_INVALID, sollte die Option gibt an, dass derzeit als transparente Farbe des Bilds der Farbe festlegen verwendet werden.

*rectDest*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel zu identifizieren.

*xSrc*<br/>
Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*ySrc*<br/>
Die y-Koordinate in logischen Einheiten der oberen linken Ecke des Quellrechtecks.

*nSrcWidth*<br/>
Die Breite in logischen Einheiten des Quellrechtecks.

*nSrcHeight*<br/>
Die Höhe in logischen Einheiten des Quellrechtecks.

*rectSrc*<br/>
Ein Verweis auf eine `RECT` Struktur, die die Quelle zu identifizieren.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls "false".

### <a name="remarks"></a>Hinweise

`TransparentBlt` wird für die Quelle von Bitmaps aus 4 Bits pro Pixel und 8 Bits pro Pixel unterstützt. Verwendung [CImage::AlphaBlend](#alphablend) 32 Bits pro Pixel Bitmaps mit Transparenz angeben.

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

[MMXSwarm-Beispiel](../../visual-cpp-samples.md)<br/>
[SimpleImage-Beispiel](../../visual-cpp-samples.md)<br/>
[Geräteunabhängige Bitmaps](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)<br/>
[Geräteunabhängige Bitmaps](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)   
