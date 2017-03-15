---
title: CImage-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CImage
- ATL.CImage
- ATL::CImage
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
caps.latest.revision: 20
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f74e5952401d6f9608425681cd91120b648e7b13
ms.lasthandoff: 02/24/2017

---
# <a name="cimage-class"></a>CImage-Klasse
`CImage`bereitgestellt, einschließlich der Möglichkeit zum Laden und Speichern von Bildern in den Formaten JPEG, GIF, BMP und Portable Network Graphics (PNG).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CImage
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImage::CImage](#cimage)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImage::AlphaBlend](#alphablend)|Zeigt die Bitmaps, die transparent oder halbtransparent Pixel haben.|  
|[CImage::Attach](#attach)|Fügt ein `HBITMAP` zu einem `CImage` Objekt. Kann mit nicht-DIB Abschnitt Bitmaps oder DIB Abschnitt Bitmaps verwendet werden.|  
|[CImage::BitBlt](#bitblt)|Kopiert eine Bitmap aus dem Quell-Gerätekontext zum aktuellen Gerätekontext.|  
|[CImage::Create](#create)|Erstellt eine Bitmap der DIB-Abschnitt und fügt ihn an das zuvor erstellte `CImage` Objekt.|  
|[CImage::CreateEx](#createex)|Erstellt eine Bitmap des DIB-Abschnitt (mit zusätzlichen Parametern) und fügt ihn an das zuvor erstellte `CImage` Objekt.|  
|[CImage::Destroy](#destroy)|Trennt das Bitmap aus der `CImage` Objekt, und die Bitmap zerstört.|  
|[CImage::Detach](#detach)|Trennt das Bitmap aus einem `CImage` Objekt.|  
|[CImage::Draw](#draw)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck. **Zeichnen Sie** Streckt oder komprimiert die Bitmap an die Maße des Zielrechtecks, bei Bedarf anpassen und behandelt Alphablending und transparente Farben.|  
|[CImage::GetBits](#getbits)|Ruft einen Zeiger auf die tatsächliche Pixelwerte der Bitmap.|  
|[CImage::GetBPP](#getbpp)|Ruft die Bits pro Pixel ab.|  
|[CImage::GetColorTable](#getcolortable)|Ruft den Rot, Grün, Blau (RGB) Farbwerte aus einem Bereich von Einträgen in der Tabelle ab.|  
|[CImage::GetDC](#getdc)|Ruft den Gerätekontext, in dem die aktuelle Bitmap ausgewählt ist.|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Sucht nach verfügbaren Bildformate und deren Beschreibung.|  
|[CImage::GetHeight](#getheight)|Ruft die Höhe des aktuellen Bilds in Pixel ab.|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Sucht nach verfügbaren Bildformate und deren Beschreibung.|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Ruft die maximale Anzahl von Einträgen in der Tabelle ab.|  
|[CImage::GetPitch](#getpitch)|Ruft die Schriftbreite des aktuellen Bilds in Bytes ab.|  
|[CImage::GetPixel](#getpixel)|Ruft die Farbe des Pixels angegebenen *x* und *y*.|  
|[CImage::GetPixelAddress](#getpixeladdress)|Ruft die Adresse eines bestimmten Pixels.|  
|[CImage::GetTransparentColor](#gettransparentcolor)|Ruft die Position der transparente Farbe in der Tabelle ab.|  
|[CImage::GetWidth](#getwidth)|Ruft die Breite des aktuellen Bilds in Pixel ab.|  
|[CImage::IsDIBSection](#isdibsection)|Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.|  
|[CImage::IsIndexed](#isindexed)|Gibt an, dass eine Bitmap Farben einer Palette indizierte zugeordnet sind.|  
|[CImage::IsNull](#isnull)|Gibt an, ob eine Quellbitmap gerade geladen wird.|  
|[IsTransparencySupported](#istransparencysupported)|Gibt an, ob die Anwendung transparente Bitmaps unterstützt und für Windows 2000 oder höher kompiliert wurde.|  
|[CImage::Load](#load)|Lädt ein Bild aus der angegebenen Datei.|  
|[CImage::LoadFromResource](#loadfromresource)|Lädt ein Bild aus der angegebenen Ressource an.|  
|[CImage::MaskBlt](#maskblt)|Kombiniert die Farbdaten für die Quell- und Ziel-Bitmaps, die unter Verwendung der angegebenen Maske und Raster des Vorgangs.|  
|[CImage::PlgBlt](#plgblt)|Führt einen Bitblocktransfer aus einem Rechteck in einem Quellgerätekontext zu einem Parallelogramm in einem Ziel-Gerätekontext.|  
|[CImage::ReleaseDC](#releasedc)|Gibt den Gerätekontext frei, die mit abgerufen wurde [CImage::GetDC](#getdc).|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Von GDI + verwendeten Ressourcen frei. Muss aufgerufen werden, um Ressourcen freizugeben, die erstellt, indem ein globaler `CImage` Objekt.|  
|[CImage::Save](#save)|Speichert ein Bild mit dem angegebenen Typ. **Speichern Sie** Image-Optionen können nicht angeben.|  
|[CImage::SetColorTable](#setcolortable)|Legt fest, Rot, Grün, Blau RGB) Farbwerte in einem Bereich von Einträgen in der Farbtabelle der DIB-Abschnitt.|  
|[CImage::SetPixel](#setpixel)|Legt das Pixel an den angegebenen Koordinaten auf die angegebene Farbe fest.|  
|[CImage::SetPixelIndexed](#setpixelindexed)|Legt das Pixel an den angegebenen Koordinaten auf die Farbe am angegebenen Index der Palette fest.|  
|[CImage::SetPixelRGB](#setpixelrgb)|Legt das Pixel an den angegebenen Koordinaten auf der angegebenen Rot, Grün, Blau (RGB) Wert fest.|  
|[CImage::SetTransparentColor](#settransparentcolor)|Legt den Index der Farbe, die behandelt werden als transparent fest. Nur eine Farbe in einer Palette kann transparent sein.|  
|[CImage::StretchBlt](#stretchblt)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck, gestreckt oder komprimiert die Bitmap an die Maße des Zielrechtecks, falls erforderlich.|  
|[CImage::TransparentBlt](#transparentblt)|Kopiert eine Bitmap für die transparente Farbe aus dem Quell-Gerätekontext zum aktuellen Gerätekontext.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CImage::operator HBITMAP](#operator_hbitmap)|Gibt das Windows-Handle an der der `CImage` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CImage`nimmt die Bitmaps, die eine geräteunabhängige Bitmap (DIB)-Abschnitte oder nicht sind. Sie können jedoch [erstellen](#create) oder [CImage::Load](#load) mit DIB-Abschnitten. Sie können eine nicht-DIB Abschnittsbitmap anfügen ein `CImage` -Objekt unter Verwendung der [Anfügen](#attach), jedoch verwenden Sie dann die folgenden `CImage` -Methoden, die nur DIB Abschnitt Bitmaps unterstützen:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 Um festzustellen, ob eine angefügte Bitmap ein DIB-Abschnitt ist, rufen Sie [IsDibSection](#isdibsection)**.**  
  
> [!NOTE]
> **Hinweis** In Visual Studio .NET 2003 sind diese Klasse zählt die Anzahl der `CImage` Objekte erstellt werden. Jedes Mal, wenn der Zähler auf 0, die Funktion **GdiplusShutdown** wird automatisch aufgerufen, um von GDI + verwendeten Ressourcen freizugeben. Dadurch wird sichergestellt, dass alle `CImage` direkt oder indirekt von DLLs erstellten Objekte werden immer ordnungsgemäß gelöscht und **GdiplusShutdown** wird nicht aufgerufen, von `DllMain`.  
  
> [!NOTE]
>  Verwendung von globalen `CImage` Objekte in einer DLL wird nicht empfohlen. Wenn Sie eine globale verwenden müssen `CImage` Objekt in eine DLL Aufruf [CImage::ReleaseGDIPlus](#releasegdiplus) von GDI + verwendete Ressourcen explizit freigeben.  
  
 `CImage`kann nicht ausgewählt werden, in ein neues [CDC](../../mfc/reference/cdc-class.md). `CImage`erstellt einen eigenen **HDC** für das Bild. Da ein `HBITMAP` kann nur aktiviert werden, in eine **HDC** gleichzeitig die `HBITMAP` zugeordnet der `CImage` kann nicht ausgewählt werden, in ein anderes **HDC**. Sollten Sie eine `CDC`, Abrufen der **HDC** aus der `CImage` und für das [CDC::FromHandle] (.. /.. /MFC/Reference/CDC-Class.MD#cdc__fromhandle.  
  
## <a name="example"></a>Beispiel  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 Bei Verwendung `CImage` in einem MFC-Projekt, beachten Sie die Memberfunktionen in Ihrem Projekt erwarten, dass einen Zeiger auf eine [CBitmap](../../mfc/reference/cbitmap-class.md) Objekt. Wenn Sie verwenden möchten `CImage` mit einer solchen Funktion wie [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), verwenden [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), übergeben sie Ihr `CImage` `HBITMAP`, und verwenden Sie die zurückgegebene `CBitmap*`.  

  
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

  
 Durch `CImage`, haben Sie Zugriff auf die eigentlichen Bits an einem DIB-Abschnitt. Sie können ein `CImage` Objekt Sie bereits einen Abschnitt Win32 HBITMAP oder DIB verwendet.  
  
> [!NOTE]
>  Die folgenden `CImage` Methoden besitzen Beschränkungen für ihre Verwendung:  
  
|Methode|Begrenzung|  
|------------|----------------|  
|[PlgBlt](#plgblt)|Funktioniert mit nur Windows NT 4.0 oder höher. Funktioniert nicht auf Windows 95-und Windows 98 oder höher ausgeführt.|  
|[MaskBlt](#maskblt)|Funktioniert mit nur Windows NT 4.0 oder höher. Funktioniert nicht auf Windows 95-und Windows 98 oder höher ausgeführt.|  
|[AlphaBlend-Funktion](#alphablend)|Nur Windows 2000, Windows 98 und höher verwendet.|  
|[TransparentBlt](#transparentblt)|Nur Windows 2000, Windows 98 und höher verwendet.|  
|[Zeichnen-Befehl](#draw)|Transparenz mit nur Windows 2000, Windows 98 und höher unterstützt.|  
  
 Sie können `CImage` von MFC oder ATL  
  
> [!NOTE]
>  Beim Erstellen eines Projekts von `CImage`, definieren Sie `CString` , bevor Sie enthalten `atlimage.h`. Wenn das Projekt ATL ohne MFC verwendet, schließen Sie `atlstr.h` , bevor Sie enthalten `atlimage.h`. Wenn das Projekt verwendet MFC (oder wenn es sich um ein ATL-Projekt mit MFC-Unterstützung ist), schließen Sie `afxstr.h` , bevor Sie enthalten `atlimage.h`.  
>   
>  Sie müssen entsprechend enthalten `atlimage.h` , bevor Sie enthalten `atlimpl.cpp`. Hierzu einfach enthalten `atlimage.h` in Ihrer `stdafx.h`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlimage.h  
  
##  <a name="a-namealphablenda--cimagealphablend"></a><a name="alphablend"></a>CImage::AlphaBlend  
 Zeigt die Bitmaps, die transparent oder halbtransparent Pixel haben.  
  
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
 Handle für den Zielgerätekontext.  
  
 `xDest`  
 Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 *bSrcAlpha*  
 Ein Wert alpha-Transparenz auf die gesamte Quellbitmap verwendet werden. Die Standardeinstellung 0xff (255) wird davon ausgegangen, dass das Bild nicht transparent ist und Sie pro-Pixel-Alphawerten nur verwenden möchten.  
  
 `bBlendOp`  
 Die Alpha-blending-Funktion für Quelle und Zielbitmaps, einen globalen Alphawert auf die gesamte Quellbitmap und Formatinformationen für die Quell-Bitmap angewendet werden. Die Quelle und Ziel Blend-Funktionen sind zurzeit auf **AC_SRC_OVER**.  
  
 `pointDest`  
 Ein Verweis auf eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die oben links das Zielrechteck in logischen Einheiten bezeichnet.  
  
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
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel identifizieren.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Alpha-Blend Bitmaps unterstützen Farbe zu füllen, jeweils pro Pixel.  
  
 Wenn `bBlendOp` festgelegt ist, der in der Standardeinstellung **AC_SRC_OVER**, die Quellbitmap wird über die Zielbitmap basierend auf die Alphawerte Pixel der Quelle eingefügt.  

##  <a name="a-nameattacha--cimageattach"></a><a name="attach"></a>CImage::Attach  
 Fügt `hBitmap` zu einem `CImage` Objekt.  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hBitmap`  
 Ein Handle für ein `HBITMAP`.  
  
 *eOrientation*  
 Gibt die Ausrichtung der Bitmap. Einer der folgenden Werte ist möglich:  
  
- **DIBOR_DEFAULT** die Ausrichtung der Bitmap wird vom Betriebssystem bestimmt. Jedoch kann dies nicht immer die gewünschten Ergebnisse auf allen Betriebssystemen haben. Weitere Informationen hierzu finden Sie unter den folgenden Knowledge Base-Artikel ( **Q186586**): PRB: GetObject() immer gibt Positive Höhe für DIB-Abschnitten.  
  
- **DIBOR_BOTTOMUP** die Zeilen der Bitmap in umgekehrter Reihenfolge sind. Dies bewirkt, dass [CImage::GetBits](#getbits) zur Rückgabe eines Zeigers in der Nähe des Puffers Bitmap und [CImage::GetPitch](#getpitch) eine negative Zahl zurückgegeben.  
  
- **DIBOR_TOPDOWN** die Zeilen der Bitmap sind in der von oben nach unten. Dies bewirkt, dass [CImage::GetBits](#getbits) zur Rückgabe eines Zeigers auf das erste Byte des Puffers Bitmap und [CImage::GetPitch](#getpitch) eine positive Zahl zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap möglich nicht DIB Abschnittsbitmap oder DIB Abschnittsbitmap. Finden Sie unter [IsDIBSection](#isdibsection) für eine Liste der Methoden, mit denen Sie nur mit DIB Abschnitt Bitmaps.  
  
##  <a name="a-namebitblta--cimagebitblt"></a><a name="bitblt"></a>CImage::BitBlt  
 Kopiert eine Bitmap aus dem Quell-Gerätekontext zum aktuellen Gerätekontext.  
  
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
 Das Raster des Vorgangs ausgeführt werden. Raster-Operationscodes definieren genau wie die Bits von der Quelle, Ziel und das Muster kombiniert (gemäß der aktuell ausgewählten Pinsel), um das Ziel zu bilden. Finden Sie unter [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in der [!INCLUDE[winSDK](./includes/winsdk_md.md)] eine Liste der anderen rastervorgang Codes und Beschreibungen.  
  
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
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in der [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
##  <a name="a-namecimagea--cimagecimage"></a><a name="cimage"></a>CImage::CImage  
 Erstellt ein `CImage`-Objekt.  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Sobald Sie das Objekt erstellt haben, rufen Sie [erstellen](#create), [laden](#load), [LoadFromResource](#loadfromresource), oder [Anfügen](#attach) das Objekt eine Bitmap an.  
  
 **Hinweis** In Visual Studio diese Klasse zählt die Anzahl der `CImage` Objekte erstellt werden. Jedes Mal, wenn der Zähler auf 0, die Funktion **GdiplusShutdown** wird automatisch aufgerufen, um von GDI + verwendeten Ressourcen freizugeben. Dadurch wird sichergestellt, dass alle `CImage` direkt oder indirekt von DLLs erstellten Objekte werden immer ordnungsgemäß gelöscht und **GdiplusShutdown** wird nicht von DllMain aufgerufen.  
  
 Verwendung von globalen `CImage` Objekte in einer DLL wird nicht empfohlen. Wenn Sie eine globale verwenden müssen `CImage` Objekt in eine DLL Aufruf [CImage::ReleaseGDIPlus](#releasegdiplus) von GDI + verwendete Ressourcen explizit freigeben.  
  
##  <a name="a-namecreatea--cimagecreate"></a><a name="create"></a>CImage::Create  
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
 Die Höhe der `CImage` Bitmap in Pixel. Wenn `nHeight` positiv ist, wird die Bitmap eine Bottom-up-DIB und seinen Ursprung der unteren linken Ecke. Wenn `nHeight` ist negativ, wird die Bitmap eine Top-Down-DIB und seinen Ursprung die linke obere Ecke.  
  
 `nBPP`  
 Die Anzahl der Bits pro Pixel in der Bitmap. In der Regel 4, 8, 16, 24 oder 32. Kann 1 für monochrome Bitmaps oder maskiert.  
  
 `dwFlags`  
 Gibt an, ob das Objekt einen alpha-Kanal verfügt. Eine Kombination von&0; (null) oder mehrere der folgenden Werte sind möglich:  
  
- **CreateAlphaChannel** kann nur verwendet werden, wenn `nBPP` ist 32, und `eCompression` ist **BI_RGB**. Wenn angegeben, hat erstellte Image einen Alphawert (Transparenz) für jedes Pixel im 4. Byte jedes Pixels (nicht in einem nicht-alphanumerische 32-Bit-Abbild verwendeten) gespeichert. Alpha-Kanal wird automatisch verwendet, beim Aufrufen von [CImage::AlphaBlend](#alphablend).  
  
> [!NOTE]
>  Aufrufe [CImage::Draw](#draw), Bilder mit Alphakanal werden automatisch alpha gemischt an das Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namecreateexa--cimagecreateex"></a><a name="createex"></a>CImage::CreateEx  
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
 Die Höhe der `CImage` Bitmap in Pixel. Wenn `nHeight` positiv ist, wird die Bitmap eine Bottom-up-DIB und seinen Ursprung der unteren linken Ecke. Wenn `nHeight` ist negativ, wird die Bitmap eine Top-Down-DIB und seinen Ursprung die linke obere Ecke.  
  
 `nBPP`  
 Die Anzahl der Bits pro Pixel in der Bitmap. In der Regel 4, 8, 16, 24 oder 32. Kann 1 für monochrome Bitmaps oder maskiert.  
  
 `eCompression`  
 Gibt den Typ der Komprimierung für eine komprimierte Bottom-up-Bitmap (Top-Down-Dateien können nicht komprimiert werden). Kann einer der folgenden Werte sein:  
  
- **BI_RGB** das Format wird nicht komprimiert. Die Angabe dieses Werts beim Aufrufen von `CImage::CreateEx` entspricht dem Aufruf von `CImage::Create`.  
  
- **BI_BITFIELDS** das Format wird dekomprimiert, und die Farbtabelle besteht aus drei `DWORD` Farbe Masken, die angeben, die Rot, Grün und Blau Komponenten bzw. jedes Pixels. Dies ist gültig, wenn Sie mit 16 und 32-Bpp-Bitmaps verwendet.  
  
 *pdwBitfields*  
 Nur verwendet, wenn `eCompression` Wert **BI_BITFIELDS**, andernfalls muss er sein **NULL**. Ein Zeiger auf ein Array von drei `DWORD` Bitmasken, die festlegen, welche Bits jedes Pixels verwendet werden, für die Rot Grün und der Farbe, bzw. blauen. Weitere Informationen zu den Einschränkungen für die Bitfelder finden Sie unter [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) in der [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `dwFlags`  
 Gibt an, ob das Objekt einen alpha-Kanal verfügt. Eine Kombination von&0; (null) oder mehrere der folgenden Werte sind möglich:  
  
- **CreateAlphaChannel** kann nur verwendet werden, wenn `nBPP` ist 32, und `eCompression` ist **BI_RGB**. Wenn angegeben, hat erstellte Image einen Alphawert (Transparenz) für jedes Pixel im 4. Byte jedes Pixels (nicht in einem nicht-alphanumerische 32-Bit-Abbild verwendeten) gespeichert. Alpha-Kanal wird automatisch verwendet, beim Aufrufen von [CImage::AlphaBlend](#alphablend).  
  
    > [!NOTE]
    >  Aufrufe [CImage::Draw](#draw), Bilder mit Alphakanal werden automatisch alpha gemischt an das Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE** bei Erfolg. Andernfalls **FALSE**.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine 100 x 100 Pixel-Bitmap, die mit 16 Bits jedes Pixel zu codieren. In einem angegebenen 16-Bit-Pixel Bits 0-3 codieren Rotanteils, Bits 4 bis 7 codieren Grün und Bits 8 bis 11 codieren Blau. Die restlichen 4 Bits werden nicht verwendet.  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="a-namedestroya--cimagedestroy"></a><a name="destroy"></a>CImage::Destroy  
 Trennt das Bitmap aus der `CImage` Objekt, und die Bitmap zerstört.  
  
```
void Destroy() throw();
```  
  
##  <a name="a-namedetacha--cimagedetach"></a><a name="detach"></a>CImage::Detach  
 Trennt eine Bitmap aus einem `CImage` Objekt.  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die Bitmap getrennt, oder **NULL** keine Bitmap angehängt ist.  
  
##  <a name="a-namedrawa--cimagedraw"></a><a name="draw"></a>CImage::Draw  
 Kopiert eine Bitmap aus dem Quell-Gerätekontext für den aktuellen Gerätekontext.  
  
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
 Ein Handle für den Zielgerätekontext.  
  
 `xDest`  
 Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `rectDest`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel identifizieren.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
 `pointDest`  
 Ein Verweis auf eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die oben links das Zielrechteck in logischen Einheiten bezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 **Zeichnen Sie** führt den gleichen Vorgang als [StretchBlt](#stretchblt), es sei denn, das Bild eine transparente Farbe oder ein Alphakanal enthält. In diesem Fall **zeichnen** führt den gleichen Vorgang entweder als [TransparentBlt](#transparentblt) oder [AlphaBlend](#alphablend) je nach Bedarf.  
  
 Für Versionen von **zeichnen** nicht angeben, die ein Rechteck, das gesamte Quellbild ist die Standardeinstellung. Für die Version des **zeichnen** die keine Größe für das Zielrechteck, die Größe des Quellbilds ist die Standardeinstellung und kein Strecken oder verkleinern auftritt.  
  
##  <a name="a-namegetbitsa--cimagegetbits"></a><a name="getbits"></a>CImage::GetBits  
 Ruft einen Zeiger auf die tatsächliche Bitwerte eines bestimmten Pixels in einer Bitmap.  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Bitmap-Puffer. Wenn die Bitmap eine Bottom-up-DIB ist, in der Nähe der Zeiger weist des Ende des Puffers. Wenn die Bitmap eine Top-Down-DIB ist, verweist der Zeiger auf das erste Byte des Puffers.  
  
### <a name="remarks"></a>Hinweise  
 Mit diesem Zeiger, zusammen mit der von zurückgegebene Wert [GetPitch](#getpitch), Sie suchen und ändern Sie die einzelnen Pixel in einem Bild.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps. Folglich Sie Zugriff auf die Pixel des ein `CImage` -Objekt die gleiche Weise der Pixel eines DIB-Abschnitts. Der zurückgegebene Zeiger zeigt auf das Pixel an der Position (0, 0).  
  
##  <a name="a-namegetbppa--cimagegetbpp"></a><a name="getbpp"></a>CImage::GetBPP  
 Ruft den Wert der Bits pro Pixel.  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bits pro Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert bestimmt die Anzahl der Bits, die jedes Pixel zu definieren und die maximale Anzahl der Farben in der Bitmap.  
  
 Bits pro Pixel ist in der Regel 1, 4, 8, 16, 24 oder 32. Finden Sie unter der **BiBitCount** Mitglied [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) in den [!INCLUDE[winSDK](./includes/winsdk_md.md)] Weitere Informationen zu diesen Wert.  
  
##  <a name="a-namegetcolortablea--cimagegetcolortable"></a><a name="getcolortable"></a>CImage::GetColorTable  
 Einen Bereich von Einträgen in der Palette des Abschnitts DIB entnimmt Rot, Grün, Blau (RGB) Farbwerte.  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iFirstColor`  
 Die Farbe Tabellenindex des ersten Eintrags abrufen.  
  
 `nColors`  
 Die Anzahl der abzurufenden Einträge Farbe-Tabelle.  
  
 `prgbColors`  
 Ein Zeiger auf das Array von [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) Strukturen zum Abrufen der Farbe Tabelle Einträge.  
  
##  <a name="a-namegetdca--cimagegetdc"></a><a name="getdc"></a>CImage::GetDC  
 Ruft den Gerätekontext, der derzeit ausgewählte hinein Image aufweist.  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für einen Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Für jeden Aufruf von `GetDC`, benötigen Sie einen nachfolgenden Aufruf von [ReleaseDC](#releasedc).  
  
##  <a name="a-namegetexporterfilterstringa--cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a>CImage::GetExporterFilterString  
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
 Ein Verweis auf eine **CSimpleString** Objekt. Finden Sie unter **Hinweise** Weitere Informationen.  
  
 `aguidFileTypes`  
 Ein Array von GUIDs, wobei jedes Element einer der Dateitypen in der Zeichenfolge entspricht. Im Beispiel in `pszAllFilesDescription` unten `aguidFileTypes`[0] ist `GUID_NULL` und die verbleibenden Arraywerte Bilddateiformate, die durch das aktuelle Betriebssystem unterstützt werden.  
  
> [!NOTE]
>  Eine vollständige Liste der Konstanten, finden Sie unter **Image Format Dateikonstanten** in der [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `pszAllFilesDescription`  
 Wenn dieser Parameter nicht **NULL**, die Filterzeichenfolge wird ein zusätzlichen Filter haben, am Anfang der Liste. Mit diesem Filter wird den aktuellen Wert der haben `pszAllFilesDescription` für seine Beschreibung und akzeptiert Erweiterung von jedem anderen Ausführer in der Liste unterstützt.  
  
 Zum Beispiel:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Satz von Bitflags, welche Dateitypen ausschließen aus der Liste angeben. Zulässigen Flags sind:  
  
- **ExcludeGIF** = 0 x 01 schließt GIF-Dateien.  
  
- **ExcludeBMP** = 0 x 02 schließt BMP (Windows Bitmap) Dateien.  
  
- **ExcludeEMF** = 0 x 04 schließt EMF (Enhanced Metafile)-Dateien.  
  
- **ExcludeWMF** = 0 x 08 schließt WMF (Windows Metafile)-Dateien.  
  
- **ExcludeJPEG** = 0 x 10 schließt JPEG-Dateien.  
  
- **ExcludePNG** = 0 x 20 schließt PNG-Dateien.  
  
- **ExcludeTIFF** = 0 x 40 schließt TIFF-Dateien.  
  
- **ExcludeIcon** = 0 x 80 schließt ICO-(Symbol für Windows) Dateien.  
  
- **ExcludeOther** = 0 x 80000000 schließt einen anderen Dateityp oben nicht aufgeführt sind.  
  
- **ExcludeDefaultLoad** = 0 für alle Typen sind standardmäßig eingeschlossen Datei laden  
  
- **ExcludeDefaultSave** = **ExcludeIcon | ExcludeEMF | ExcludeWMF** zum Speichern, werden diese Dateien standardmäßig ausgeschlossen, da sie in der Regel über besondere Anforderungen verfügen.  
  
 `chSeparator`  
 Das Trennzeichen zwischen die Bildformate verwendet. Finden Sie unter **Hinweise** Weitere Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die resultierende Zeichenfolge übergeben, mit der MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) Objekt, das die Dateierweiterungen der verfügbaren Abbild verfügbar machen im Dialogfeld Datei speichern unter formatiert.  
  
 Der Parameter *StrExporter* hat das folgende Format:  
  
 Datei description0 | \*.ext0 | filedescription1 | \*ext1 |... DateiBeschreibung *n*|\*. ext *n*||  
  
 wobei ' |' wird durch das Trennzeichen angegeben `chSeparator`. Zum Beispiel:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Verwenden Sie das Standardtrennzeichen ' |', wenn Sie diese Zeichenfolge, um einer MFC übergeben `CFileDialog` Objekt. Verwenden Sie das null-Trennzeichen '\0', wenn Sie diese Zeichenfolge, um ein allgemeines Dialogfeld Datei speichern übergeben.  
  
##  <a name="a-namegetheighta--cimagegetheight"></a><a name="getheight"></a>CImage::GetHeight  
 Ruft die Höhe in Pixel eines Bildes ab.  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel eines Bilds.  
  
##  <a name="a-namegetimporterfilterstringa--cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a>CImage::GetImporterFilterString  
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
 Ein Verweis auf eine **CSimpleString** Objekt. Finden Sie unter **Hinweise** Weitere Informationen.  
  
 `aguidFileTypes`  
 Ein Array von GUIDs, wobei jedes Element einer der Dateitypen in der Zeichenfolge entspricht. Im Beispiel in `pszAllFilesDescription` unten `aguidFileTypes`[0] ist `GUID_NULL` mit dem restlichen Werte Bilddateiformate, die durch das aktuelle Betriebssystem unterstützt werden.  
  
> [!NOTE]
>  Eine vollständige Liste der Konstanten, finden Sie unter **Image Format Dateikonstanten** in der [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `pszAllFilesDescription`  
 Wenn dieser Parameter nicht **NULL**, die Filterzeichenfolge wird ein zusätzlichen Filter haben, am Anfang der Liste. Mit diesem Filter wird den aktuellen Wert der haben `pszAllFilesDescription` für seine Beschreibung und akzeptiert Erweiterung von jedem anderen Ausführer in der Liste unterstützt.  
  
 Zum Beispiel:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Satz von Bitflags, welche Dateitypen ausschließen aus der Liste angeben. Zulässigen Flags sind:  
  
- **ExcludeGIF** = 0 x 01 schließt GIF-Dateien.  
  
- **ExcludeBMP** = 0 x 02 schließt BMP (Windows Bitmap) Dateien.  
  
- **ExcludeEMF** = 0 x 04 schließt EMF (Enhanced Metafile)-Dateien.  
  
- **ExcludeWMF** = 0 x 08 schließt WMF (Windows Metafile)-Dateien.  
  
- **ExcludeJPEG** = 0 x 10 schließt JPEG-Dateien.  
  
- **ExcludePNG** = 0 x 20 schließt PNG-Dateien.  
  
- **ExcludeTIFF** = 0 x 40 schließt TIFF-Dateien.  
  
- **ExcludeIcon** = 0 x 80 schließt ICO-(Symbol für Windows) Dateien.  
  
- **ExcludeOther** = 0 x 80000000 schließt einen anderen Dateityp oben nicht aufgeführt sind.  
  
- **ExcludeDefaultLoad** = 0 für alle Typen sind standardmäßig eingeschlossen Datei laden  
  
- **ExcludeDefaultSave** = **ExcludeIcon | ExcludeEMF | ExcludeWMF** zum Speichern, werden diese Dateien standardmäßig ausgeschlossen, da sie in der Regel über besondere Anforderungen verfügen.  
  
 `chSeparator`  
 Das Trennzeichen zwischen die Bildformate verwendet. Finden Sie unter **Hinweise** Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die resultierende Zeichenfolge übergeben, mit der MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) Formate, Objekt, das die Dateierweiterungen der verfügbaren Abbild verfügbar machen die **Datei öffnen** Dialogfeld.  
  
 Der Parameter *StrImporter* hat das folgende Format:  
  
 Datei description0 | \*.ext0 | filedescription1 | \*ext1 |... DateiBeschreibung *n*|\*. ext *n*||  
  
 wobei ' |' wird durch das Trennzeichen angegeben `chSeparator`. Zum Beispiel:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Verwenden Sie das Standardtrennzeichen ' |', wenn Sie diese Zeichenfolge, um einer MFC übergeben `CFileDialog` Objekt. Das null-Trennzeichen '\0' verwenden, wenn Sie diese Zeichenfolge, um eine allgemeine übergeben **Datei öffnen** Dialogfeld.  
  
##  <a name="a-namegetmaxcolortableentriesa--cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableEntries  
 Ruft die maximale Anzahl von Einträgen in der Tabelle ab.  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Einträge in der Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="a-namegetpitcha--cimagegetpitch"></a><a name="getpitch"></a>CImage::GetPitch  
 Ruft die Tonhöhe eines Bildes ab.  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Tonhöhe des Bilds. Wenn der Wert negativ ist, die Bitmap ist eine Bottom-up-DIB und seinen Ursprung ist die linke untere Ecke. Wenn der Rückgabewert die Bitmap ist eine Top-Down-DIB und seinen Ursprung die linke obere Ecke ist positiv ist.  
  
### <a name="remarks"></a>Hinweise  
 Der Pitch ist die Entfernung in Bytes, der zwischen zwei Speicheradressen, die den Anfang einer Bitmapzeile darstellen und dem Beginn der nächsten Bitmapzeile. Da Tonhöhe in Byte gemessen wird, können die Tonhöhe eines Bilds um das Pixelformat zu ermitteln. Die Tonhöhe kann auch zusätzliche, für die Bitmap reservierten Speicher enthalten.  
  
 Verwendung `GetPitch` mit [GetBits](#getbits) einzelne Pixel eines Bildes zu finden.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="a-namegetpixela--cimagegetpixel"></a><a name="getpixel"></a>CImage::GetPixel  
 Ruft die Farbe des Pixels am angegebenen Speicherort ab *x* und *y*.  
  
```
COLORREF GetPixel(int x,int y) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Die X-Koordinate des Pixels.  
  
 *y*  
 Die y-Koordinate des Pixels.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rot, Grün, Blau (RGB) Wert des Pixels. Wenn Pixel außerhalb des aktuellen Ausschneidebereichs lautet der Rückgabewert ist **CLR_INVALID**.  
  
##  <a name="a-namegetpixeladdressa--cimagegetpixeladdress"></a><a name="getpixeladdress"></a>CImage::GetPixelAddress  
 Ruft die genaue Adresse eines Pixels ab.  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Die X-Koordinate des Pixels.  
  
 *y*  
 Die y-Koordinate des Pixels.  
  
### <a name="remarks"></a>Hinweise  
 Die Adresse wird bestimmt, die Koordinaten eines Pixels, die Tonhöhe der Bitmap und die Bits pro Pixel.  
  
 Formate, die weniger als 8 Bits pro Pixel aufweisen, gibt diese Methode die Adresse des mit dem Pixel Bytes. Wenn Ihr Bildformat 4 Bits pro Pixel, hat beispielsweise `GetPixelAddress` gibt die Adresse des ersten Pixels in Bytes, und Sie müssen für 2 Pixel pro Byte berechnen.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="a-namegettransparentcolora--cimagegettransparentcolor"></a><a name="gettransparentcolor"></a>CImage::GetTransparentColor  
 Ruft den indizierten Position der transparente Farbe in der Farbpalette ab.  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der transparente Farbe.  
  
##  <a name="a-namegetwidtha--cimagegetwidth"></a><a name="getwidth"></a>CImage::GetWidth  
 Ruft die Breite in Pixel eines Bildes ab.  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Bitmap in Pixel.  
  
##  <a name="a-nameisdibsectiona--cimageisdibsection"></a><a name="isdibsection"></a>CImage::IsDIBSection  
 Bestimmt, ob die angefügte Bitmap ein DIB-Abschnitt ist.  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die angefügte Bitmap ein DIB-Abschnitt ist. Andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Bitmap nicht um eine DIB-Abschnitt ist, können keine der folgenden `CImage` -Methoden, die nur DIB Abschnitt Bitmaps unterstützen:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="a-nameisindexeda--cimageisindexed"></a><a name="isindexed"></a>CImage::IsIndexed  
 Bestimmt, ob die Pixel der Bitmap eine Farbpalette zugeordnet sind.  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn andernfalls indizierte **false**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt **true** nur, wenn die Bitmap mit 8 Bit (256 Farben) oder weniger.  
  
> [!NOTE]
>  Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="a-nameisnulla--cimageisnull"></a><a name="isnull"></a>CImage::IsNull  
 Bestimmt, ob eine Bitmap gerade geladen wird.  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt **True** ist eine Bitmap nicht aktuell geladen; andernfalls **False**.  
  
##  <a name="a-nameistransparencysupporteda--cimageistransparencysupported"></a><a name="istransparencysupported"></a>IsTransparencySupported  
 Gibt an, ob die Anwendung transparente Bitmaps unterstützt und für Windows 2000 oder höher kompiliert wurde.  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die aktuelle Plattform Transparenz unterstützt. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert ungleich NULL ist und Transparenz unterstützt wird, einen Aufruf von [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), oder [zeichnen](#draw) transparente Farben behandelt.  
  
 Wenn die Anwendung für die Verwendung mit Betriebssystemen vor Windows 2000 oder Windows 98 kompiliert wird, gibt diese Methode immer 0, auch bei neueren Betriebssystemen zurück.  
  

##  <a name="a-nameloada--cimageload"></a><a name="load"></a>CImage::Load  
 Lädt ein Bild.  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszFileName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Bilddatei zu laden.  
  
 `pStream`  
 Ein Zeiger auf einen Stream mit dem Namen der Bilddatei zu laden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Lädt das angegebene Bild *PszFileName* oder `pStream`.  
  
 Gültiges Bildtypen sind BMP, GIF, JPEG, PNG und TIFF.  
  
##  <a name="a-nameloadfromresourcea--cimageloadfromresource"></a><a name="loadfromresource"></a>CImage::LoadFromResource  
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
 Handle für eine Instanz des Moduls mit dem Abbild geladen werden.  
  
 `pszResourceName`  
 Ein Zeiger auf die Zeichenfolge mit dem Namen der Ressource, die zu ladenden Bilds enthält.  
  
 `nIDResource`  
 Die ID der Ressource geladen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Ressource muss vom Typ `BITMAP`.  
  
##  <a name="a-namemaskblta--cimagemaskblt"></a><a name="maskblt"></a>CImage::MaskBlt  
 Kombiniert die Farbdaten für die Quell- und Ziel-Bitmaps, die unter Verwendung der angegebenen Maske und Raster des Vorgangs.  
  
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
 Das Handle für das Modul, dessen ausführbare Datei die Ressource enthält.  
  
 `xDest`  
 Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logische Arbeitseinheiten Zielbitmap Rechteck und Quelle.  
  
 `nDestHeight`  
 Die Höhe in logische Arbeitseinheiten Zielbitmap Rechteck und Quelle.  
  
 `xSrc`  
 Die logische X-Koordinate der oberen linken Ecke der Bitmap für die Datenquelle.  
  
 `ySrc`  
 Die logische y-Koordinate der oberen linken Ecke der Bitmap für die Datenquelle.  
  
 `hbmMask`  
 Handle für die monochrome Maskenbitmap in Kombination mit der Farbbitmap im Quellgerätekontext.  
  
 `xMask`  
 Der horizontale Pixel-Offset für den angegebenen Maskenbitmap der `hbmMask` Parameter.  
  
 `yMask`  
 Der vertikale Pixel-Offset für den angegebenen Maskenbitmap der `hbmMask` Parameter.  
  
 `dwROP`  
 Gibt die Vordergrund- und Hintergrundfarben ternäre rastervorgangscode, die die Methode verwendet, um die Kombination von Quell-und Zieldaten zu steuern. Der Hintergrund Raster Vorgangscode wird in das höherwertige Wort dieses Werts das höherwertige Byte gespeichert. der Vordergrund Raster Vorgangscode wird in das untere Byte das höherwertige Wort dieses Werts gespeichert. das niederwertige Wort von dieser Wert wird ignoriert, und sollte&0; (null) sein. Eine Erläuterung der Vordergrund- und Hintergrundfarbe im Kontext dieser Methode, finden Sie unter `MaskBlt` in der [!INCLUDE[winSDK](./includes/winsdk_md.md)]. Eine Liste der allgemeinen rastervorgangscode, finden Sie unter `BitBlt` in der [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `rectDest`  
 Ein Verweis auf eine `RECT` -Struktur, die das Ziel identifiziert.  
  
 `pointSrc`  
 Ein `POINT` Struktur, der angibt, in der oberen linken Ecke des Quellrechtecks.  
  
 `pointMask`  
 Ein **Punkt** -Struktur, die der oberen linken Ecke der Maskenbitmap für die angibt.  
  
 `pointDest`  
 Ein Verweis auf eine **Punkt** -Struktur, die oben links das Zielrechteck in logischen Einheiten bezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gilt für Windows NT, Version 4.0 und höher vorgesehen.  
  
##  <a name="a-nameoperatorhbitmapa--cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a>CImage::operator HBITMAP  
 Verwenden Sie diesen Operator zum Abrufen der angefügten Windows GDI-Handle für die `CImage` Objekt. Dieser Operator ist ein Typumwandlungsoperator verwendet, die direkte Verwendung von unterstützt ein `HBITMAP` Objekt.  
  
##  <a name="a-nameplgblta--cimageplgblt"></a><a name="plgblt"></a>CImage::PlgBlt  
 Führt einen Bitblocktransfer aus einem Rechteck in einem Quellgerätekontext zu einem Parallelogramm in einem Ziel-Gerätekontext.  
  
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
 Ein Handle für den Zielgerätekontext.  
  
 *pPoints*  
 Ein Zeiger auf ein Array von drei Punkten in logischer Speicherplatz, die drei Ecken des Zielparallelogramms zu identifizieren. Der erste Punkt in diesem Array oben rechts auf den zweiten Punkt in diesem Array und der unteren linken Ecke dem dritten Punkt wird der oberen linken Ecke des Quellrechtecks zugeordnet. Der unteren rechten Ecke des Quellrechtecks wird die implizite vierten Punkt in der Parallelogramm zugeordnet.  
  
 `hbmMask`  
 Ein Handle für eine optionale monochrome Bitmap, die verwendet wird, um die Farben des Quellrechtecks.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `xMask`  
 Die X-Koordinate der oberen linken Ecke der monochrome Bitmap.  
  
 `yMask`  
 Die y-Koordinate der oberen linken Ecke der monochrome Bitmap.  
  
 `rectSrc`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die den angegebenen Koordinaten des Quellrechtecks.  
  
 `pointMask`  
 Ein [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die der oberen linken Ecke der Maskenbitmap für die angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `hbmMask` identifiziert eine gültige monochrome Bitmap **PlgBit** diese Bitmap verwendet, um die Bits der Farbdaten vom Quellrechtecks zu maskieren.  
  
 Diese Methode gilt für Windows NT, Version 4.0 und höher vorgesehen. Finden Sie unter [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) in den [!INCLUDE[winSDK](./includes/winsdk_md.md)] Ausführlichere Informationen.  
  
##  <a name="a-namereleasedca--cimagereleasedc"></a><a name="releasedc"></a>CImage::ReleaseDC  
 Gibt den Gerätekontext frei.  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Da nur eine Bitmap in einem Gerätekontext gleichzeitig ausgewählt werden kann, müssen Sie aufrufen `ReleaseDC` für jeden Aufruf von [GetDC](#getdc).  
  
##  <a name="a-namereleasegdiplusa--cimagereleasegdiplus"></a><a name="releasegdiplus"></a>CImage::ReleaseGDIPlus  
 Von GDI + verwendeten Ressourcen frei.  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode muss aufgerufen werden, um Ressourcen freizugeben, die von einer globalen zugeordneten `CImage` Objekt. Finden Sie unter [CImage::CImage](#cimage).  
  
##  <a name="a-namesavea--cimagesave"></a><a name="save"></a>CImage::Save  
 Speichert ein Bild in den angegebenen Stream oder eine Datei auf dem Datenträger.  
  
```
HRESULT Save(IStream* pStream,
 REFGUID guidFileType) const throw();

HRESULT Save(LPCTSTR pszFileName,
 REFGUID guidFileType= GUID_NULL) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 Ein Zeiger auf ein COM-IStream-Objekt, das Daten des Bilds enthält.  
  
 *pszFileName*  
 Ein Zeiger auf den Dateinamen für das Bild.  
  
 `guidFileType`  
 Der zum Speichern des Bilds als Dateityp. Einer der folgenden Werte ist möglich:  
  
- **ImageFormatBMP** eine dekomprimierte Bitmap-Bild.  
  
- **ImageFormatPNG** komprimiertes Bild ein Portable Network Graphic (PNG).  
  
- **ImageFormatJPEG** komprimierte ein JPEG-Bild.  
  
- **ImageFormatGIF** komprimierte ein GIF-Bild.  
  
> [!NOTE]
>  Eine vollständige Liste der Konstanten, finden Sie unter **Image Format Dateikonstanten** in der [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Speichern des Abbilds mithilfe eines angegebenen Namens und Typs. Wenn die `guidFileType` Parameter nicht enthalten ist, bestimmt das Format der Dateinamen-Erweiterung verwendet werden. Wenn keine Erweiterung angegeben ist, wird das Bild im BMP-Format gespeichert.  
  
##  <a name="a-namesetcolortablea--cimagesetcolortable"></a><a name="setcolortable"></a>CImage::SetColorTable  
 Legt die Rot, Grün, Blau (RGB) Farbwerte für einen Bereich von Einträgen in der Palette des Abschnitts DIB fest.  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iFirstColor`  
 Die Farbe Tabellenindex des ersten Eintrags fest.  
  
 `nColors`  
 Die Anzahl der Einträge Farbe fest.  
  
 `prgbColors`  
 Ein Zeiger auf das Array von [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) Strukturen zum Festlegen der Farbe Tabelle Einträge.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt nur DIB Abschnitt Bitmaps.  
  
##  <a name="a-namesetpixela--cimagesetpixel"></a><a name="setpixel"></a>CImage::SetPixel  
 Legt die Farbe eines Pixels an einer angegebenen Position in der Bitmap.  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Die horizontale Position des festzulegenden Pixels.  
  
 *y*  
 Die vertikale Position des festzulegenden Pixels.  
  
 `color`  
 Die Farbe, die die Pixel festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn das Pixel liegen außerhalb des ausgewählten Ausschneidebereichs koordiniert.  
  
##  <a name="a-namesetpixelindexeda--cimagesetpixelindexed"></a><a name="setpixelindexed"></a>CImage::SetPixelIndexed  
 Legt die Farbe des Pixels auf die Farbe am `iIndex` in der Farbpalette.  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Die horizontale Position des festzulegenden Pixels.  
  
 *y*  
 Die vertikale Position des festzulegenden Pixels.  
  
 `iIndex`  
 Der Index einer Farbe in der Farbpalette.  
  
##  <a name="a-namesetpixelrgba--cimagesetpixelrgb"></a><a name="setpixelrgb"></a>CImage::SetPixelRGB  
 Legt die Pixel an den angegebenen Speicherorten *x* und *y* die Farben, die durch angegebene *r*, *g*, und *b*, in einem Rot, Grün, Blau (RGB)-Image.  
  
```
void SetPixelRGB(  
 int x,
 int y,
 BYTE r,
 BYTE g,
 BYTE b) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Die horizontale Position des festzulegenden Pixels.  
  
 *y*  
 Die vertikale Position des festzulegenden Pixels.  
  
 *r*  
 Die Intensität der Farbe Rot.  
  
 *g*  
 Die Intensität der Farbe Grün.  
  
 *b*  
 Die Intensität der Farbe Blau.  
  
### <a name="remarks"></a>Hinweise  
 Die roten, grünen und blauen Parameter werden jeweils durch eine Zahl zwischen 0 und 255 dargestellt. Wenn Sie alle drei Parameter auf&0; (null) festlegen, ist die kombinierte Ergebnisfarbe Schwarz. Wenn Sie alle drei Parameter auf 255 festgelegt, ist die kombinierte resultierende Farbe Weiß.  
  
##  <a name="a-namesettransparentcolora--cimagesettransparentcolor"></a><a name="settransparentcolor"></a>CImage::SetTransparentColor  
 Legt eine Farbe an einer angegebenen indizierten Position als transparent fest.  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *iTransparentColor*  
 Der Index in einer Farbpalette die Farbe auf transparent fest. Wenn –&1; ist, wird keine Farbe auf transparent festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der Farbe festgelegt zuvor als transparent.  
  
##  <a name="a-namestretchblta--cimagestretchblt"></a><a name="stretchblt"></a>CImage::StretchBlt  
 Kopiert eine Bitmap aus dem Quell-Gerätekontext zum aktuellen Gerätekontext.  
  
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
 Ein Handle für den Zielgerätekontext.  
  
 `xDest`  
 Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 `dwROP`  
 Das Raster des Vorgangs ausgeführt werden. Raster-Operationscodes definieren genau wie die Bits von der Quelle, Ziel und das Muster kombiniert (gemäß der aktuell ausgewählten Pinsel), um das Ziel zu bilden. Finden Sie unter [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in der [!INCLUDE[winSDK](./includes/winsdk_md.md)] eine Liste der anderen rastervorgang Codes und Beschreibungen.  
  
 `rectDest`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel identifizieren.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) in der [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
##  <a name="a-nametransparentblta--cimagetransparentblt"></a><a name="transparentblt"></a>CImage::TransparentBlt  
 Kopiert eine Bitmap aus dem Quell-Gerätekontext zum aktuellen Gerätekontext.  
  
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
 Ein Handle für den Zielgerätekontext.  
  
 `xDest`  
 Die X-Koordinate in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `yDest`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Die Breite in logischen Einheiten des Zielrechtecks.  
  
 `nDestHeight`  
 Die Höhe in logischen Einheiten des Zielrechtecks.  
  
 *crTransparent*  
 Die Farbe in die Quellbitmap als transparent behandelt. In der Standardeinstellung **CLR_INVALID**, gibt an, dass die Farbe, die derzeit als die transparente Farbe des Bilds festlegen verwendet werden soll.  
  
 `rectDest`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die das Ziel identifizieren.  
  
 `xSrc`  
 Die X-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `ySrc`  
 Die y-Koordinate, in in logischen Einheiten der oberen linken Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Die Breite in logischen Einheiten des Quellrechtecks.  
  
 `nSrcHeight`  
 Die Höhe in logischen Einheiten des Quellrechtecks.  
  
 `rectSrc`  
 Ein Verweis auf eine `RECT` -Struktur, die Quelle zu identifizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn erfolgreich, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 `TransparentBlt`wird für die Quelle von Bitmaps aus 4 Bits pro Pixel und 8 Bits pro Pixel unterstützt. Verwendung [CImage::AlphaBlend](#alphablend) 32 Bits pro Pixel Bitmaps mit Transparenz angeben.  
  
  
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
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)
 [geräteunabhängige Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   










