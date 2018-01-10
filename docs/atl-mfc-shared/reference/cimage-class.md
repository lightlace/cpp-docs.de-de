---
title: CImage-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d2720fb2b1e558b564615e1589735fe84688374b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cimage-class"></a>CImage-Klasse
`CImage`bietet erweiterte Bitmapunterstützung, einschließlich der Möglichkeit zum Laden und speichern Sie die Bilder in JPEG, GIF, BMP und Portable Network Graphics (PNG).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CImage::AlphaBlend](#alphablend)|Zeigt die Bitmaps, die transparent oder halbtransparenten Pixel haben.|  
|[CImage::Attach](#attach)|Fügt eine `HBITMAP` zu einem `CImage` Objekt. Kann mit nicht-DIB Abschnitt Bitmaps oder DIB Abschnitt Bitmaps verwendet werden.|  
|[CImage::BitBlt](#bitblt)|Kopiert eine Bitmap aus dem Quellgerätekontext für diese aktuelle Gerätekontext.|  
|[CImage::Create](#create)|Erstellt eine DIB Abschnittsbitmap und fügt ihn der zuvor erstellten `CImage` Objekt.|  
|[CImage::CreateEx](#createex)|Erstellt eine DIB Abschnittsbitmap (mit zusätzlichen Parametern) und fügt ihn der zuvor erstellten `CImage` Objekt.|  
|[CImage::Destroy](#destroy)|Trennt die Bitmap aus der `CImage` Objekt, und zerstört die Bitmap.|  
|[CImage::Detach](#detach)|Trennt die Bitmap aus einem `CImage` Objekt.|  
|[CImage::Draw](#draw)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck. **Zeichnen Sie** Streckt oder komprimiert die Bitmap die Maße des Zielrechtecks, bei Bedarf angepasst und behandelt Alphablending und transparenten Farben.|  
|[CImage::GetBits](#getbits)|Ruft einen Zeiger auf die tatsächliche Pixelwerte der Bitmap ab.|  
|[CImage::GetBPP](#getbpp)|Ruft die Bits pro Pixel ab.|  
|[CImage::GetColorTable](#getcolortable)|Ruft den Rot, Grün, Blau () RGB-Werte aus einem Bereich von Einträgen in der Tabelle ab.|  
|[CImage::GetDC](#getdc)|Ruft ab den Gerätekontext, der in dem aktuelle Bitmap ausgewählt ist.|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Sucht nach der verfügbaren Bildformate und deren Beschreibungen.|  
|[CImage::GetHeight](#getheight)|Ruft die Höhe des aktuellen Bilds in Pixel ab.|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Sucht nach der verfügbaren Bildformate und deren Beschreibungen.|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Ruft die maximale Anzahl von Einträgen in der Tabelle ab.|  
|[CImage::GetPitch](#getpitch)|Ruft die Tonhöhe, der das aktuelle Bild, in Bytes ab.|  
|[CImage::GetPixel](#getpixel)|Ruft die Farbe des Pixels gemäß *x* und *y*.|  
|[CImage::GetPixelAddress](#getpixeladdress)|Ruft die Adresse eines bestimmten Pixels ab.|  
|[CImage::GetTransparentColor](#gettransparentcolor)|Ruft die Position des die transparente Farbe in der Tabelle ab.|  
|[CImage::GetWidth](#getwidth)|Ruft die Breite des aktuellen Bilds in Pixel ab.|  
|[CImage::IsDIBSection](#isdibsection)|Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.|  
|[CImage::IsIndexed](#isindexed)|Gibt an, dass eine indizierte Palette eine Bitmap Farben zugeordnet werden.|  
|[CImage::IsNull](#isnull)|Gibt an, ob eine Quellbitmap momentan geladen ist.|  
|[IsTransparencySupported](#istransparencysupported)|Gibt an, ob die Anwendung unterstützt transparente Bitmaps für Windows 2000 oder höher kompiliert wurde.|  
|[CImage::Load](#load)|Lädt ein Bild aus der angegebenen Datei.|  
|[CImage::LoadFromResource](#loadfromresource)|Lädt ein Bild aus der angegebenen Ressource an.|  
|[CImage::MaskBlt](#maskblt)|Kombiniert die Farbdaten für die Quell- und Zielschemas Bitmaps, die unter Verwendung der angegebenen Maske und auszuführenden Vorgangs an.|  
|[CImage::PlgBlt](#plgblt)|Führt einen Bitblocktransfer aus einem Rechteck in einem Quellgerätekontext in ein Parallelogramm in einem Ziel-Gerätekontext aus.|  
|[CImage::ReleaseDC](#releasedc)|Gibt den Gerätekontext frei, die mit abgerufenen [CImage::GetDC](#getdc).|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Gibt die von GDI + verwendete Ressourcen frei. Muss aufgerufen werden, um Ressourcen freizugeben, die erstellt, indem ein globaler `CImage` Objekt.|  
|[CImage::Save](#save)|Speichert ein Bild als den angegebenen Typ. **Speichern Sie** Image-Optionen können nicht angeben.|  
|[CImage::SetColorTable](#setcolortable)|Versetzt wird rot, Grün, Blau RGB) Farbwerte in einem Bereich von Einträgen in der Tabelle der Farbe des Abschnitts DIB.|  
|[CImage::SetPixel](#setpixel)|Legt das Pixel an den angegebenen Koordinaten auf der angegebenen Farbe.|  
|[CImage::SetPixelIndexed](#setpixelindexed)|Legt das Pixel an den angegebenen Koordinaten, die Farbe am angegebenen Index aus der Palette fest.|  
|[CImage::SetPixelRGB](#setpixelrgb)|Legt das Pixel an den angegebenen Koordinaten auf der angegebenen Rot, Grün, Blau-Wert fest.|  
|[CImage::SetTransparentColor](#settransparentcolor)|Legt den Index der ausgewählten Farbe behandelt werden als transparent. Nur eine Farbe in einer Palette kann transparent sein.|  
|[CImage::StretchBlt](#stretchblt)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck, Strecken oder komprimiert die Bitmap an die Maße des Zielrechtecks, angepasst.|  
|[CImage::TransparentBlt](#transparentblt)|Kopiert eine Bitmap mit transparente Farbe aus dem Quellgerätekontext für diese aktuelle Gerätekontext.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImage::operator HBITMAP](#operator_hbitmap)|Gibt die Windows-Handle an der die `CImage` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CImage`nimmt die Bitmaps, die entweder Abschnitte geräteunabhängige Bitmap (DIB) oder nicht verwendet werden. Sie können jedoch [erstellen](#create) oder [CImage::Load](#load) mit nur DIB Abschnitte. Sie können eine nicht DIB Abschnittsbitmap anfügen eine `CImage` -Objekt mit [Anfügen](#attach), dann kann jedoch die folgenden `CImage` -Methoden, die nur DIB Abschnitt Bitmaps unterstützen:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 Um festzustellen, ob eine angefügte Bitmap ein DIB-Abschnitt ist, rufen [IsDibSection](#isdibsection)**.**  
  
> [!NOTE]
> **Hinweis** In Visual Studio .NET 2003 sind diese Klasse hält die Anzahl der Anzahl von `CImage` erstellten Objekte. Wenn der Zähler auf 0 (null) die Funktion **GdiplusShutdown** automatisch aufgerufen, um von GDI + verwendeten Ressourcen freizugeben. Dadurch wird sichergestellt, dass alle `CImage` direkt oder indirekt von DLLs erstellten Objekte zerstört werden immer richtig und die **GdiplusShutdown** wird nicht aufgerufen werden, von `DllMain`.  
  
> [!NOTE]
>  Verwendung von globalen `CImage` Objekte in einer DLL wird nicht empfohlen. Wenn Sie einen globalen verwenden müssen `CImage` Objekt in eine DLL Aufruf [CImage::ReleaseGDIPlus](#releasegdiplus) von GDI + verwendete Ressourcen explizit freigeben.  
  
 `CImage`kann nicht ausgewählt werden, in eine neue [CDC](../../mfc/reference/cdc-class.md). `CImage`erstellt einen eigenen **HDC** für das Bild. Da ein `HBITMAP` kann nur ausgewählt werden, in einem **HDC** zu einem Zeitpunkt die `HBITMAP` zugeordnet der `CImage` kann nicht ausgewählt werden, in eine andere **HDC**. Wenn Sie müssen eine `CDC`, Abrufen der **HDC** aus der `CImage` und weisen Sie ihm [CDC::FromHandle] (.. /.. /MFC/Reference/CDC-Class.MD#cdc__fromhandle.  
  
## <a name="example"></a>Beispiel  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 Bei Verwendung von `CImage` in einem MFC-Projekt, beachten Sie, welche Member-Funktionen in Ihrem Projekt erwarten, dass einen Zeiger auf eine [CBitmap](../../mfc/reference/cbitmap-class.md) Objekt. Wenn Sie verwenden möchten `CImage` mit einer solchen Funktion wie [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), verwenden [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), übergeben Sie ihn Ihrer `CImage` `HBITMAP`, und verwenden Sie die zurückgegebenen `CBitmap*`.  

  
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

  
 Über `CImage`, haben Sie Zugriff auf die tatsächlichen Bits von einem Abschnitt DIB. Sie können eine `CImage` Objekt Sie zuvor einen Abschnitt Win32 HBITMAP oder DIB verwendet.  
  
> [!NOTE]
>  Die folgenden `CImage` Methoden besitzen Beschränkungen für ihre Verwendung:  
  
|Methode|Einschränkung|  
|------------|----------------|  
|[PlgBlt](#plgblt)|Funktioniert mit nur Windows NT 4.0 oder höher. Funktioniert nicht auf Anwendungen auf Windows 95-und Windows 98 oder höher ausgeführt.|  
|[MaskBlt](#maskblt)|Funktioniert mit nur Windows NT 4.0 oder höher. Funktioniert nicht auf Anwendungen auf Windows 95-und Windows 98 oder höher ausgeführt.|  
|[AlphaBlend](#alphablend)|Verwendet nur Windows 2000, Windows 98 und höher.|  
|[TransparentBlt](#transparentblt)|Verwendet nur Windows 2000, Windows 98 und höher.|  
|[Zeichnen-Befehl](#draw)|Transparenz mit nur Windows 2000, Windows 98 und höher unterstützt.|  
  
 Sie können `CImage` von MFC oder ATL  
  
> [!NOTE]
>  Beim Erstellen eines Projekts von `CImage`, müssen Sie definieren `CString` bevor Sie einfügen `atlimage.h`. Wenn das Projekt ATL ohne MFC verwendet, schließen Sie `atlstr.h` bevor Sie einfügen `atlimage.h`. Wenn das Projekt verwendet MFC (oder wenn sie eine ATL-Projekt mit MFC-Unterstützung ist), schließen Sie `afxstr.h` bevor Sie einfügen `atlimage.h`.  
>   
>  Sie müssen entsprechend enthalten `atlimage.h` bevor Sie einfügen `atlimpl.cpp`. Hierzu einfach enthalten `atlimage.h` in Ihrer `stdafx.h`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlimage.h  
  
##  <a name="alphablend"></a>CImage::AlphaBlend  
 Zeigt die Bitmaps, die transparent oder halbtransparenten Pixel haben.  
  
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
 `hDestDC`  
 Handle für den Ziel-Gerätekontext.  
  
 `xDest`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 *bSrcAlpha*  
 Ein alpha Transparenzwert für die gesamte Quellbitmap verwendet werden soll. Die Standardeinstellung 0xff (255) wird davon ausgegangen, dass das Bild nicht transparent ist und Sie nur alphanumerische Werte pixelbasierte verwenden möchten.  
  
 `bBlendOp`  
 Die Alphablending Funktion für Quelle und Zielbitmaps, einem globalen Alphawert auf die gesamte Quellbitmap und Formatinformationen für die Quellbitmap angewendet werden soll. Die Quell- und Zielschemas Blend-Funktionen sind zurzeit auf **AC_SRC_OVER**.  
  
 `pointDest`  
 Ein Verweis auf eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die der oberen linken Ecke des Zielrechtecks in logischen Einheiten bezeichnet.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 `xSrc`  
 Die logische X-Koordinate der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die logische y-Koordinate der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `rectDest`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur identifiziert das Ziel.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Alpha-Blend Bitmaps unterstützen Kombination von Farbe auf Basis eines pro Pixel.  
  
 Wenn `bBlendOp` festgelegt ist, der in der Standardeinstellung **AC_SRC_OVER**, die Quellbitmap wird über die Zielbitmap basierend auf den Alphawerten des Pixel der Quelle eingefügt.  

##  <a name="attach"></a>CImage::Attach  
 Fügt `hBitmap` zu einem `CImage` Objekt.  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hBitmap`  
 Ein Handle für ein `HBITMAP`.  
  
 *eOrientation*  
 Gibt die Ausrichtung der Bitmap. Einer der folgenden Werte ist möglich:  
  
- **DIBOR_DEFAULT** die Ausrichtung der Bitmap wird vom Betriebssystem bestimmt. Allerdings kann dadurch nicht immer die gewünschten Ergebnisse von allen Betriebssystemen ausgeschlossen. Weitere Informationen dazu finden Sie unter den folgenden Knowledge Base-Artikel ( **Q186586**): PRB: GetObject() immer gibt Positive Höhe für DIB Abschnitte.  
  
- **DIBOR_BOTTOMUP** die Zeilen der Bitmap in umgekehrter Reihenfolge sind. Dies bewirkt, dass [CImage::GetBits](#getbits) zur Rückgabe eines Zeigers gegen Ende des Puffers Bitmap und [CImage::GetPitch](#getpitch) eine negative Zahl zurückgegeben.  
  
- **DIBOR_TOPDOWN** befinden sich die Zeilen der Bitmap in oben nach unten. Dies bewirkt, dass [CImage::GetBits](#getbits) zur Rückgabe eines Zeigers auf das erste Byte des Puffers Bitmap und [CImage::GetPitch](#getpitch) eine positive Zahl zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap möglich nicht DIB Abschnittsbitmap oder DIB Abschnittsbitmap. Finden Sie unter [IsDIBSection](#isdibsection) im Abschnitt Bitmaps, eine Liste der Methoden, die nur mit DIB verwendet werden können.  
  
##  <a name="bitblt"></a>CImage::BitBlt  
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
 `hDestDC`  
 Das Ziel **HDC**.  
  
 `xDest`  
 Die logische X-Koordinate der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die logische y-Koordinate der oberen linken Ecke des Zielrechtecks.  
  
 `dwROP`  
 Des auszuführenden Vorgangs ausgeführt werden. Raster-Operationscodes definieren genau wie die Bits von der Quelle, Ziel und dem Muster kombiniert werden (gemäß der aktuell ausgewählten Pinsel) um das Ziel zu bilden. Finden Sie unter [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in das Windows SDK für eine Liste mit anderen rastervorgang Codes und Beschreibungen.  
  
 `pointDest`  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, der angibt, in der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 `xSrc`  
 Die logische X-Koordinate der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die logische y-Koordinate der oberen linken Ecke des Quellrechtecks.  
  
 `rectDest`  
 Ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das Zielrechteck angibt.  
  
 `pointSrc`  
 Ein **Punkt** Struktur, der angibt, in der oberen linken Ecke des Quellrechtecks.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) im Windows SDK.  
  
##  <a name="cimage"></a>CImage::CImage  
 Erstellt ein `CImage`-Objekt.  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Sobald Sie das Objekt erstellt haben, rufen Sie [erstellen](#create), [laden](#load), [LoadFromResource](#loadfromresource), oder [Anfügen](#attach) eine Bitmap an das Objekt anzufügen.  
  
 **Hinweis** In Visual Studio kann diese Klasse hält die Anzahl der Anzahl von `CImage` erstellten Objekte. Wenn der Zähler auf 0 (null) die Funktion **GdiplusShutdown** automatisch aufgerufen, um von GDI + verwendeten Ressourcen freizugeben. Dadurch wird sichergestellt, dass alle `CImage` direkt oder indirekt von DLLs erstellten Objekte zerstört werden immer richtig und die **GdiplusShutdown** nicht aus DllMain aufgerufen wird.  
  
 Verwendung von globalen `CImage` Objekte in einer DLL wird nicht empfohlen. Wenn Sie einen globalen verwenden müssen `CImage` Objekt in eine DLL Aufruf [CImage::ReleaseGDIPlus](#releasegdiplus) von GDI + verwendete Ressourcen explizit freigeben.  
  
##  <a name="create"></a>CImage::Create  
 Erstellt eine `CImage` bitmap, und fügen Sie es an das zuvor erstellte `CImage` Objekt.  
  
```
BOOL Create(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Die Breite der `CImage` Bitmap in Pixel.  
  
 `nHeight`  
 Die Höhe der `CImage` Bitmap in Pixel. Wenn `nHeight` positiv ist, wird die Bitmap ist eine von unten nach oben DIB und Ursprungssite ist die linke untere Ecke. Wenn `nHeight` ist negativ ist, die Bitmap ist eine Top-Down-DIB und seinen Ursprung die linke obere Ecke.  
  
 `nBPP`  
 Die Anzahl von Bits pro Pixel in der Bitmap. In der Regel 4, 8, 16, 24 oder 32. 1 für monochrome Bitmaps oder Masken ist möglich.  
  
 `dwFlags`  
 Gibt an, ob das Bitmapobjekt einen alpha-Kanal verfügt. Eine Kombination von 0 (null) oder mehrere der folgenden Werte ist möglich:  
  
- **CreateAlphaChannel** kann nur verwendet werden, wenn `nBPP` beträgt 32, und `eCompression` ist **BI_RGB**. Wenn angegeben, hat das erstellte Bild ein Alphawerte (Transparenz) jedem Pixel, in dem 4. Byte jedes Pixels (nicht in einem nicht-alphanumerische 32-Bit-Image verwendet wird) gespeichert. Alpha-Kanal wird automatisch verwendet, wenn Aufrufen [CImage::AlphaBlend](#alphablend).  
  
> [!NOTE]
>  Aufrufe [CImage::Draw](#draw), Bilder mit einen alpha-Kanal werden automatisch alpha gemischt an das Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="createex"></a>CImage::CreateEx  
 Erstellt eine `CImage` bitmap, und fügen Sie es an das zuvor erstellte `CImage` Objekt.  
  
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
 `nWidth`  
 Die Breite der `CImage` Bitmap in Pixel.  
  
 `nHeight`  
 Die Höhe der `CImage` Bitmap in Pixel. Wenn `nHeight` positiv ist, wird die Bitmap ist eine von unten nach oben DIB und Ursprungssite ist die linke untere Ecke. Wenn `nHeight` ist negativ ist, die Bitmap ist eine Top-Down-DIB und seinen Ursprung die linke obere Ecke.  
  
 `nBPP`  
 Die Anzahl von Bits pro Pixel in der Bitmap. In der Regel 4, 8, 16, 24 oder 32. 1 für monochrome Bitmaps oder Masken ist möglich.  
  
 `eCompression`  
 Gibt den Typ der Komprimierung für eine komprimierte Bottom-up-Bitmap (DIB von oben nach unten können nicht komprimiert werden). Kann einer der folgenden Werte sein:  
  
- **BI_RGB** weist das Format dekomprimiert. Die Angabe dieses Werts beim Aufrufen von `CImage::CreateEx` entspricht dem Aufruf `CImage::Create`.  
  
- **BI_BITFIELDS** das Format wird dekomprimiert und die Farbe Tabelle besteht aus drei `DWORD` Masken für Farbe, die angeben, die Rot, Grün und Blau Komponenten bzw. jedes Pixels. Dies ist gültig, wenn mit 16 - und 32-Bit pro Pixel Bitmaps verwendet.  
  
 *pdwBitfields*  
 Nur verwendet, wenn `eCompression` festgelegt ist, um **BI_BITFIELDS**, andernfalls muss er **NULL**. Ein Zeiger auf ein Array von drei `DWORD` Bitmasken, angeben, welche Bits pro Pixel verwendet werden, für den roten Grün und bzw. blauen Komponenten der ausgewählten Farbe. Weitere Informationen zu den Einschränkungen für die Bitfelder finden Sie unter [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) im Windows SDK.  
  
 `dwFlags`  
 Gibt an, ob das Bitmapobjekt einen alpha-Kanal verfügt. Eine Kombination von 0 (null) oder mehrere der folgenden Werte ist möglich:  
  
- **CreateAlphaChannel** kann nur verwendet werden, wenn `nBPP` beträgt 32, und `eCompression` ist **BI_RGB**. Wenn angegeben, hat das erstellte Bild ein Alphawerte (Transparenz) jedem Pixel, in dem 4. Byte jedes Pixels (nicht in einem nicht-alphanumerische 32-Bit-Image verwendet wird) gespeichert. Alpha-Kanal wird automatisch verwendet, wenn Aufrufen [CImage::AlphaBlend](#alphablend).  
  
    > [!NOTE]
    >  Aufrufe [CImage::Draw](#draw), Bilder mit einen alpha-Kanal werden automatisch alpha gemischt an das Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** bei Erfolg. Andernfalls **"false"**.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine 100 x 100 Pixel-Bitmap, die mithilfe von 16 Bits zum Codieren von jedem Pixel. In einer angegebenen 16-Bit-Pixel Bits 0-3 codieren Rotanteils Bits 4-7-Codierung Grün und Bits 8 bis 11, codieren Blau. Die verbleibenden 4 Bits werden nicht verwendet.  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="destroy"></a>CImage::Destroy  
 Trennt die Bitmap aus der `CImage` Objekt, und zerstört die Bitmap.  
  
```
void Destroy() throw();
```  
  
##  <a name="detach"></a>CImage::Detach  
 Trennt eine Bitmap aus einem `CImage` Objekt.  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die Bitmap getrennt, oder **NULL** , wenn keine Bitmap verbunden ist.  
  
##  <a name="draw"></a>CImage::Draw  
 Kopiert eine Bitmap aus dem Quellgerätekontext für den aktuellen Gerätekontext.  
  
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
 `hDestDC`  
 Ein Handle für den Ziel-Gerätekontext.  
  
 `xDest`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `rectDest`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur identifiziert das Ziel.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
 `pointDest`  
 Ein Verweis auf eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die der oberen linken Ecke des Zielrechtecks in logischen Einheiten bezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 **Zeichnen Sie** führt den gleichen Vorgang als [StretchBlt](#stretchblt), es sei denn, das Bild eine transparente Farbe oder einen alpha-Kanal enthält. In diesem Fall **zeichnen** führt den gleichen Vorgang entweder als [TransparentBlt](#transparentblt) oder [AlphaBlend](#alphablend) nach Bedarf.  
  
 Für Versionen von **zeichnen** , die einem Quellrechteck nicht angeben, das gesamte Quellbild ist die Standardeinstellung. Für die Version des **zeichnen** , in denen eine Größe für das Zielrechteck angegeben ist, die Größe des Quellbilds ist die Standardeinstellung und keine Strecken oder verkleinern auftritt.  
  
##  <a name="getbits"></a>CImage::GetBits  
 Ruft einen Zeiger auf die tatsächliche Bit-Werte eines bestimmten Pixels in einer Bitmap ab.  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Puffer mithilfe einer Bitmap. Wenn die Bitmap eine von unten nach oben DIB ist, Nähe der Zeiger weist das Ende des Puffers. Wenn die Bitmap eine Top-Down-DIB, der Zeiger verweist auf das erste Byte des Puffers ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der this-Zeiger, zusammen mit den Rückgabewert von [GetPitch](#getpitch), können Sie suchen und ändern Sie die einzelnen Pixel in einem Bild.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps; Folglich Sie Zugriff auf die Pixel ein `CImage` Objekt die gleiche Weise die Pixel eines Abschnitts DIB möchten. Der zurückgegebene Zeiger verweist auf das Pixel an der Position (0, 0).  
  
##  <a name="getbpp"></a>CImage::GetBPP  
 Ruft den Wert für Bits pro Pixel.  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bits pro Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert bestimmt die Anzahl der Bits, die jedem Pixel definieren und die maximale Anzahl der Farben in der Bitmap.  
  
 Die Bits pro Pixel ist in der Regel 1, 4, 8, 16, 24 oder 32. Finden Sie unter der **BiBitCount** Mitglied [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) in das Windows SDK für Weitere Informationen zu diesen Wert.  
  
##  <a name="getcolortable"></a>CImage::GetColorTable  
 Ruft den Rot, Grün, Blau () RGB-Werte aus einem Bereich von Einträgen in der Palette des Abschnitts DIB ab.  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iFirstColor`  
 Der Index der Farbe des ersten Eintrags abrufen.  
  
 `nColors`  
 Die Anzahl der abzurufenden Einträge Farbe-Tabelle.  
  
 `prgbColors`  
 Ein Zeiger auf das Array von [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) Strukturen, die die Farbe abrufen-Tabelle Einträge.  
  
##  <a name="getdc"></a>CImage::GetDC  
 Ruft ab den Gerätekontext, der derzeit ausgewählte hinein Image aufweist.  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für einen Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Für jeden Aufruf von `GetDC`, benötigen Sie einen nachfolgenden Aufruf von [ReleaseDC](#releasedc).  
  
##  <a name="getexporterfilterstring"></a>CImage::GetExporterFilterString  
 Speichern von Bildern sucht Bildformate verfügbar.  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Parameter  
 *strExporters*  
 Ein Verweis auf eine **CSimpleString** Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen.  
  
 `aguidFileTypes`  
 Ein Array von GUIDs, wobei jedes Element einer der Dateitypen in der Zeichenfolge entspricht. Im Beispiel im `pszAllFilesDescription` unten `aguidFileTypes`[0] ist `GUID_NULL` und die verbleibenden Arraywerte sind die Image-Dateiformate, die durch das aktuelle Betriebssystem unterstützt.  
  
> [!NOTE]
>  Eine vollständige Liste der Konstanten finden Sie unter **Image Format Dateikonstanten** im Windows SDK.  
  
 `pszAllFilesDescription`  
 Wenn dieser Parameter nicht **NULL**, die Filterzeichenfolge verfügen über ein zusätzlicher Filter am Anfang der Liste. Dieser Filter wird den aktuellen Wert der haben `pszAllFilesDescription` für seine Beschreibung und akzeptiert Sie Dateien von einer Erweiterung, die von jeder anderen Exporter-Tool in der Liste unterstützt.  
  
 Zum Beispiel:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Der Satz von Bitflags, welche Dateitypen ausschließen aus der Liste angeben. Zulässigen Flags sind:  
  
- **ExcludeGIF** = 0 x 01 schließt GIF-Dateien.  
  
- **ExcludeBMP** = 0 x 02 schließt BMP (Windows-Bitmap)-Dateien.  
  
- **ExcludeEMF** = 0 x 04 schließt EMF (Enhanced Metafile)-Dateien.  
  
- **ExcludeWMF** = 0 x 08 schließt WMF (Windows Metafile)-Dateien.  
  
- **ExcludeJPEG** = 0 x 10 schließt JPEG-Dateien.  
  
- **ExcludePNG** = 0 x 20 schließt PNG-Dateien.  
  
- **ExcludeTIFF** = 0 x 40 schließt TIFF-Dateien.  
  
- **ExcludeIcon** = 0 x 80 schließt ICO (Symbol "Windows")-Dateien.  
  
- **ExcludeOther** = 0 x 80000000 schließt einen anderen Dateityp oben nicht aufgeführt sind.  
  
- **ExcludeDefaultLoad** = 0 für alle Typen sind standardmäßig eingeschlossen Datei laden  
  
- **ExcludeDefaultSave** = **ExcludeIcon &#124; ExcludeEMF &#124; ExcludeWMF** zum Speichern, werden diese Dateien standardmäßig ausgeschlossen, da sie in der Regel über besondere Anforderungen verfügen.  
  
 `chSeparator`  
 Das Trennzeichen zwischen den Bildformate verwendet. Finden Sie unter **"Hinweise"** für Weitere Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die resultierende Zeichenfolge übergeben, mit der MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) Objekt, das die Dateierweiterungen der verfügbaren Images verfügbar machen im Dialogfeld Datei speichern unter formatiert.  
  
 Der Parameter *StrExporter* weist das Format auf:  
  
 Datei description0 &#124; \*.ext0 &#124; filedescription1 &#124; \*ext1 &#124;... DateiBeschreibung  *n* &#124;\*. Ext  *n* &#124; &#124;  
  
 wobei "&#124;" wird durch das Zeichen als Trennzeichen angegeben `chSeparator`. Zum Beispiel:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Verwenden Sie das Standardtrennzeichen "&#124;", wenn Sie diese Zeichenfolge, um einer MFC übergeben `CFileDialog` Objekt. Verwenden Sie das null-Trennzeichen '\0', wenn Sie diese Zeichenfolge, um ein häufig verwendetes Dialogfeld Datei speichern übergeben.  
  
##  <a name="getheight"></a>CImage::GetHeight  
 Ruft die Höhe in Pixel, der einem Bild ab.  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel, ein Bild.  
  
##  <a name="getimporterfilterstring"></a>CImage::GetImporterFilterString  
 Sucht nach verfügbaren Bildformate zum Laden von Bildern.  
  
```
static HRESULT GetImporterFilterString(CSimpleString& strImporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultLoad,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Parameter  
 *strImporters*  
 Ein Verweis auf eine **CSimpleString** Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen.  
  
 `aguidFileTypes`  
 Ein Array von GUIDs, wobei jedes Element einer der Dateitypen in der Zeichenfolge entspricht. Im Beispiel im `pszAllFilesDescription` unten `aguidFileTypes`[0] ist `GUID_NULL` mit dem Array der verbleibenden Werte Bilddateiformaten, die durch das aktuelle Betriebssystem unterstützt werden.  
  
> [!NOTE]
>  Eine vollständige Liste der Konstanten finden Sie unter **Image Format Dateikonstanten** im Windows SDK.  
  
 `pszAllFilesDescription`  
 Wenn dieser Parameter nicht **NULL**, die Filterzeichenfolge verfügen über ein zusätzlicher Filter am Anfang der Liste. Dieser Filter wird den aktuellen Wert der haben `pszAllFilesDescription` für seine Beschreibung und akzeptiert Sie Dateien von einer Erweiterung, die von jeder anderen Exporter-Tool in der Liste unterstützt.  
  
 Zum Beispiel:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Der Satz von Bitflags, welche Dateitypen ausschließen aus der Liste angeben. Zulässigen Flags sind:  
  
- **ExcludeGIF** = 0 x 01 schließt GIF-Dateien.  
  
- **ExcludeBMP** = 0 x 02 schließt BMP (Windows-Bitmap)-Dateien.  
  
- **ExcludeEMF** = 0 x 04 schließt EMF (Enhanced Metafile)-Dateien.  
  
- **ExcludeWMF** = 0 x 08 schließt WMF (Windows Metafile)-Dateien.  
  
- **ExcludeJPEG** = 0 x 10 schließt JPEG-Dateien.  
  
- **ExcludePNG** = 0 x 20 schließt PNG-Dateien.  
  
- **ExcludeTIFF** = 0 x 40 schließt TIFF-Dateien.  
  
- **ExcludeIcon** = 0 x 80 schließt ICO (Symbol "Windows")-Dateien.  
  
- **ExcludeOther** = 0 x 80000000 schließt einen anderen Dateityp oben nicht aufgeführt sind.  
  
- **ExcludeDefaultLoad** = 0 für alle Typen sind standardmäßig eingeschlossen Datei laden  
  
- **ExcludeDefaultSave** = **ExcludeIcon &#124; ExcludeEMF &#124; ExcludeWMF** zum Speichern, werden diese Dateien standardmäßig ausgeschlossen, da sie in der Regel über besondere Anforderungen verfügen.  
  
 `chSeparator`  
 Das Trennzeichen zwischen den Bildformate verwendet. Finden Sie unter **"Hinweise"** für Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die resultierende Zeichenfolge übergeben, mit der MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) Objekt, das die Dateierweiterungen der verfügbaren Images verfügbar zu machen formatiert wird, der **Datei öffnen** (Dialogfeld).  
  
 Der Parameter *StrImporter* weist das Format auf:  
  
 Datei description0 &#124; \*.ext0 &#124; filedescription1 &#124; \*ext1 &#124;... DateiBeschreibung  *n* &#124;\*. Ext  *n* &#124; &#124;  
  
 wobei "&#124;" wird durch das Zeichen als Trennzeichen angegeben `chSeparator`. Zum Beispiel:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Verwenden Sie das Standardtrennzeichen "&#124;", wenn Sie diese Zeichenfolge, um einer MFC übergeben `CFileDialog` Objekt. Die null-Trennzeichen '\0' verwenden, wenn Sie diese Zeichenfolge, eine allgemeine übergeben **Datei öffnen** (Dialogfeld).  
  
##  <a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableEntries  
 Ruft die maximale Anzahl von Einträgen in der Tabelle ab.  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Einträge in der Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="getpitch"></a>CImage::GetPitch  
 Ruft die Tonhöhe eines Bilds ab.  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Tonhöhe des Bilds. Wenn der zurückgegebene Wert negativ ist, die Bitmap ist eine von unten nach oben DIB und Ursprungssite ist die linke untere Ecke. Wenn der Rückgabewert die Bitmap ist eine Top-Down-DIB und Ursprungssite ist die linke obere Ecke positiv ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Tonhöhe, entspricht dem Abstand, in Bytes, der zwischen zwei Speicheradressen, die den Anfang einer Bitmapzeile darstellen und dem Anfang der nächsten Bitmapzeile mithilfe einer. Da Tonhöhe in Bytes gemessen wird, kann die Tonhöhe eines Bilds Sie das Pixelformat zu bestimmen. Die Tonhöhe kann auch zusätzliche, für die Bitmap reservierten Speicher enthalten.  
  
 Verwendung `GetPitch` mit [GetBits](#getbits) einzelne Pixel eines Bilds gefunden.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="getpixel"></a>CImage::GetPixel  
 Ruft die Farbe des Pixels an der vom angegebenen Position ab *x* und *y*.  
  
```
COLORREF GetPixel(int x,int y) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die X-Koordinate des Pixels.  
  
 *y*  
 Die y-Koordinate des Pixels.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rot, Grün, Blau (RGB)-Wert des Pixels. Das Pixel außerhalb des aktuellen Ausschneidebereichs, der Rückgabewert ist **CLR_INVALID**.  
  
##  <a name="getpixeladdress"></a>CImage::GetPixelAddress  
 Ruft die genaue Adresse eines Pixels ab.  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die X-Koordinate des Pixels.  
  
 *y*  
 Die y-Koordinate des Pixels.  
  
### <a name="remarks"></a>Hinweise  
 Die Adresse richtet sich danach die Koordinaten eines Pixels, die Tonhöhe der Bitmap und die Bits pro Pixel.  
  
 Für die Formate, die weniger als 8 Bits pro Pixel haben, gibt diese Methode die Adresse des Bytes, die das Pixel enthält. Wenn Ihr Bildformat 4 Bits pro Pixel, hat beispielsweise `GetPixelAddress` gibt die Adresse des ersten Pixels in das Byte, und Sie müssen für 2 Pixel pro Byte berechnen.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="gettransparentcolor"></a>CImage::GetTransparentColor  
 Ruft den indizierten Position die transparente Farbe in der Farbpalette ab.  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index für die transparente Farbe.  
  
##  <a name="getwidth"></a>CImage::GetWidth  
 Ruft die Breite in Pixel, der einem Bild ab.  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Bitmap in Pixel.  
  
##  <a name="isdibsection"></a>CImage::IsDIBSection  
 Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** , wenn die angefügte Bitmap ein DIB-Abschnitt ist. Andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Bitmap nicht um einen Abschnitt DIB ist, nicht möglich, verwenden Sie die folgende `CImage` -Methoden, die nur DIB Abschnitt Bitmaps unterstützen:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="isindexed"></a>CImage::IsIndexed  
 Bestimmt, ob eine Bitmap Pixel eine Farbpalette zugeordnet sind.  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn indiziert ist; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt **"true"** nur, wenn die Bitmap 8-Bit (256 Farben) oder weniger.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="isnull"></a>CImage::IsNull  
 Bestimmt, ob eine Bitmap ist derzeit geladen.  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt **"true"** ist eine Bitmap nicht aktuell geladen wird; andernfalls **"false"**.  
  
##  <a name="istransparencysupported"></a>IsTransparencySupported  
 Gibt an, ob die Anwendung unterstützt transparente Bitmaps für Windows 2000 oder höher kompiliert wurde.  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die aktuelle Plattform Transparenz unterstützt. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der zurückgegebene Wert ungleich NULL ist und Transparenz unterstützt wird, einen Aufruf von [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), oder [zeichnen](#draw) transparente Farben behandelt.  
  
 Wenn die Anwendung für die Verwendung mit Betriebssystemen vor Windows 2000 oder Windows 98 kompiliert wird, gibt diese Methode immer 0, auch unter neueren Betriebssystemen zurück.  
  

##  <a name="load"></a>CImage::Load  
 Lädt ein Bild an.  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszFileName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der zu ladenden Bilddatei enthält.  
  
 `pStream`  
 Ein Zeiger auf einen Stream mit dem Namen des zu ladenden Bilddatei.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Lädt das Bild gemäß *PszFileName* oder `pStream`.  
  
 Gültige imagetypen sind BMP, GIF, JPEG, PNG und TIFF.  
  
##  <a name="loadfromresource"></a>CImage::LoadFromResource  
 Lädt ein Bild aus einer `BITMAP` Ressource.  
  
```
void LoadFromResource(
 HINSTANCE hInstance,
 LPCTSTR pszResourceName) throw();

void LoadFromResource(
 HINSTANCE hInstance,
 UINT nIDResource) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Handle für eine Instanz des Moduls mit dem Bild geladen werden.  
  
 `pszResourceName`  
 Ein Zeiger auf die Zeichenfolge, die mit dem Namen der Ressource, die zu ladende Bild enthält.  
  
 `nIDResource`  
 Die ID der Ressource geladen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Ressource muss vom Typ `BITMAP`.  
  
##  <a name="maskblt"></a>CImage::MaskBlt  
 Kombiniert die Farbdaten für die Quell- und Zielschemas Bitmaps, die unter Verwendung der angegebenen Maske und auszuführenden Vorgangs an.  
  
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
 `hDestDC`  
 Das Handle für das Modul, dessen ausführbare Datei der Ressource enthält.  
  
 `xDest`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logische Arbeitseinheiten Zielbitmap Rechteck und Quelle.  
  
 `nDestHeight`  
 Die Höhe in logische Arbeitseinheiten Zielbitmap Rechteck und Quelle.  
  
 `xSrc`  
 Die logische X-Koordinate der oberen linken Ecke des Quellbitmaps.  
  
 `ySrc`  
 Die logische y-Koordinate der oberen linken Ecke des Quellbitmaps.  
  
 `hbmMask`  
 Handle für die monochrome Maskenbitmap mit Farbe Bitmap in dem Quellgerätekontext kombiniert.  
  
 `xMask`  
 Der horizontale Pixel-Offset für die Maskenbitmap gemäß der `hbmMask` Parameter.  
  
 `yMask`  
 Der vertikale Pixel-Offset für die Maskenbitmap gemäß der `hbmMask` Parameter.  
  
 `dwROP`  
 Gibt die Vordergrund- und Hintergrundfarben ternäre rastervorgangscode, die die Methode verwendet, um die Kombination von Quell-und Zieldaten zu steuern. Der Hintergrund auszuführenden Vorgangscode wird in das höherwertige Wort dieses Werts das höherwertige Byte gespeichert. im Vordergrund auszuführenden Vorgangscode wird in das höherwertige Wort dieses Werts das niederwertige Byte gespeichert. das niederwertige Wort dieses Werts wird ignoriert, und es sollte 0 (null) sein. Eine Erläuterung der Vorder- und Hintergrundfarbe im Kontext dieser Methode, finden Sie unter `MaskBlt` im Windows SDK. Eine Liste der allgemeinen rastervorgangscode, finden Sie unter `BitBlt` im Windows SDK.  
  
 `rectDest`  
 Ein Verweis auf eine `RECT` Struktur identifiziert das Ziel.  
  
 `pointSrc`  
 Ein `POINT` Struktur, der angibt, in der oberen linken Ecke des Quellrechtecks.  
  
 `pointMask`  
 Ein **Punkt** -Struktur, die oben links der Maskenbitmap für die angibt.  
  
 `pointDest`  
 Ein Verweis auf eine **Punkt** Struktur, die der oberen linken Ecke des Zielrechtecks in logischen Einheiten bezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gilt für Windows NT, Version 4.0 und höher vorgesehen.  
  
##  <a name="operator_hbitmap"></a>CImage::operator HBITMAP  
 Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle Abrufen der `CImage` Objekt. Dieser Operator wird ein Typumwandlungsoperator, die direkte Verwendung von unterstützt ein `HBITMAP` Objekt.  
  
##  <a name="plgblt"></a>CImage::PlgBlt  
 Führt einen Bitblocktransfer aus einem Rechteck in einem Quellgerätekontext in ein Parallelogramm in einem Ziel-Gerätekontext aus.  
  
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
 `hDestDC`  
 Ein Handle für den Ziel-Gerätekontext.  
  
 *pPoints*  
 Ein Zeiger auf ein Array von drei Punkten in logischer Speicherplatz, die drei Ecken des Parallelogramms ergibt Ziel zu identifizieren. Der erste Punkt in diesem Array, der oberen rechten Ecke auf den zweiten Punkt in diesem Array und die linke untere Ecke dem dritten Punkt wird der oberen linken Ecke des Quellrechtecks zugeordnet. Der unteren rechten Ecke des Quellrechtecks wird bis zum vierten implizite Punkt in der Parallelogramm zugeordnet.  
  
 `hbmMask`  
 Ein Handle für eine optionale monochrome Bitmap, die verwendet wird, um die Farben des Quellrechtecks zu maskieren.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `xMask`  
 Die X-Koordinate der oberen linken Ecke der monochrome Bitmap.  
  
 `yMask`  
 Die y-Koordinate der oberen linken Ecke der monochrome Bitmap.  
  
 `rectSrc`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Koordinaten des Quellrechtecks angibt.  
  
 `pointMask`  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die oben links der Maskenbitmap für die angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `hbmMask` identifiziert eine gültige monochrome Bitmap **PlgBit** diese Bitmap verwendet, um die Bits der Farbdaten vom Quellrechtecks zu maskieren.  
  
 Diese Methode gilt für Windows NT, Version 4.0 und höher vorgesehen. Finden Sie unter [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) in das Windows SDK für ausführlichere Informationen.  
  
##  <a name="releasedc"></a>CImage::ReleaseDC  
 Gibt den Gerätekontext frei.  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Da nur eine Bitmap einen Gerätekontext gleichzeitig ausgewählt werden kann, müssen Sie aufrufen `ReleaseDC` für jeden Aufruf von [GetDC](#getdc).  
  
##  <a name="releasegdiplus"></a>CImage::ReleaseGDIPlus  
 Gibt die von GDI + verwendete Ressourcen frei.  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode muss aufgerufen werden, um Ressourcen freizugeben, die von einer globalen belegten `CImage` Objekt. Finden Sie unter [CImage::CImage](#cimage).  
  
##  <a name="save"></a>CImage::Save  
 Speichert ein Bild in den angegebenen Stream oder eine Datei auf dem Datenträger.  
  
```
HRESULT Save(IStream* pStream,
 REFGUID guidFileType) const throw();

HRESULT Save(LPCTSTR pszFileName,
 REFGUID guidFileType= GUID_NULL) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 Ein Zeiger auf ein COM-IStream-Objekt, das die Bilddaten für die Datei enthält.  
  
 *pszFileName*  
 Ein Zeiger auf den Dateinamen für das Bild.  
  
 `guidFileType`  
 Den Dateityp, das Abbild als speichern. Einer der folgenden Werte ist möglich:  
  
- **ImageFormatBMP** eine nicht komprimierte Bitmap-Bild.  
  
- **ImageFormatPNG** komprimierte Abbild ein Grafik PNG (Portable Network).  
  
- **ImageFormatJPEG** komprimierte ein JPEG-Bild.  
  
- **ImageFormatGIF** GIF ein komprimiertes Bild.  
  
> [!NOTE]
>  Eine vollständige Liste der Konstanten finden Sie unter **Image Format Dateikonstanten** im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um das Abbild mithilfe eines angegebenen Namens und Typs zu speichern. Wenn die `guidFileType` Parameter nicht enthalten ist, die Dateierweiterung der Dateiname wird verwendet, um das Image-Format zu bestimmen. Wenn keine Erweiterung angegeben wird, wird das Bild im BMP-Format gespeichert werden.  
  
##  <a name="setcolortable"></a>CImage::SetColorTable  
 Legt die Rot, Grün, Blau () RGB-Werte für einen Bereich von Einträgen in der Palette des Abschnitts DIB fest.  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iFirstColor`  
 Der Index der Farbe des ersten Eintrags fest.  
  
 `nColors`  
 Die Anzahl der Farbe Tabelleneinträge festlegen.  
  
 `prgbColors`  
 Ein Zeiger auf das Array von [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) Strukturen zum Festlegen der Farbe-Tabelle Einträge.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="setpixel"></a>CImage::SetPixel  
 Legt die Farbe des Pixels an einer angegebenen Position in der Bitmap an.  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die horizontale Position des Pixels festgelegt.  
  
 *y*  
 Die vertikale Position des Pixels festgelegt.  
  
 `color`  
 Die Farbe auf der Sie das Pixel festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn das Pixel liegen außerhalb des Clippingbereichs ausgewählten koordiniert.  
  
##  <a name="setpixelindexed"></a>CImage::SetPixelIndexed  
 Legt die Farbe des Pixels der Farbe am `iIndex` in der Farbpalette.  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die horizontale Position des Pixels festgelegt.  
  
 *y*  
 Die vertikale Position des Pixels festgelegt.  
  
 `iIndex`  
 Der Index einer Farbe in der Farbpalette.  
  
##  <a name="setpixelrgb"></a>CImage::SetPixelRGB  
 Legt das Pixel an den Speicherorten von angegebenen *x* und *y* die Farben erkennbar *r*, *g*, und *b*, ein Rot, Grün, Blau (RGB)-Image.  
  
```
void SetPixelRGB(  
 int x,
 int y,
 BYTE r,
 BYTE g,
 BYTE b) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die horizontale Position des Pixels festgelegt.  
  
 *y*  
 Die vertikale Position des Pixels festgelegt.  
  
 *r*  
 Die Intensität der Farbe Rot.  
  
 *g*  
 Die Intensität der Farbe Grün.  
  
 *b*  
 Die Intensität der Farbe Blau.  
  
### <a name="remarks"></a>Hinweise  
 Die Rot-, Grün- und Blau-Parameter werden jeweils durch eine Zahl zwischen 0 und 255 dargestellt. Wenn Sie alle drei Parameter auf 0 (null) festlegen, ist die kombinierte resultierende Farbe Schwarz. Wenn Sie alle drei Parameter auf 255 festgelegt, ist die kombinierte resultierende Farbe Weiß.  
  
##  <a name="settransparentcolor"></a>CImage::SetTransparentColor  
 Legt eine Farbe an einer angegebenen indizierten Position als transparent fest.  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *iTransparentColor*  
 Der Index in einer Farbpalette, der die Farbe auf transparent festgelegt. Wenn-1 ist, wird keine Farbe auf transparent festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der ausgewählten Farbe zuvor als transparent festgelegt.  
  
##  <a name="stretchblt"></a>CImage::StretchBlt  
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
 `hDestDC`  
 Ein Handle für den Ziel-Gerätekontext.  
  
 `xDest`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 `dwROP`  
 Des auszuführenden Vorgangs ausgeführt werden. Raster-Operationscodes definieren genau wie die Bits von der Quelle, Ziel und dem Muster kombiniert werden (gemäß der aktuell ausgewählten Pinsel) um das Ziel zu bilden. Finden Sie unter [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in das Windows SDK für eine Liste mit anderen rastervorgang Codes und Beschreibungen.  
  
 `rectDest`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur identifiziert das Ziel.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) im Windows SDK.  
  
##  <a name="transparentblt"></a>CImage::TransparentBlt  
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
 `hDestDC`  
 Ein Handle für den Ziel-Gerätekontext.  
  
 `xDest`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 *crTransparent*  
 Die Farbe in die Quellbitmap, als transparent behandelt werden sollen. Standardmäßig **CLR_INVALID**, gibt an, dass die Farbe, die derzeit festgelegt, wie die transparente Farbe des Bilds verwendet werden soll.  
  
 `rectDest`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur identifiziert das Ziel.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten, die von der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** bei Erfolg, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 `TransparentBlt`wird für die Quelle von Bitmaps aus 4 Bits pro Pixel und 8 Bits pro Pixel unterstützt. Verwendung [CImage::AlphaBlend](#alphablend) 32 Bits pro Pixel Bitmaps Zwischenfarbe angeben.  
  
  
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
 [MMXSwarm-Beispiel](../../visual-cpp-samples.md)   
 [SimpleImage-Beispiel](../../visual-cpp-samples.md)   
 [Geräteunabhängige Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md) [geräteunabhängige Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   









