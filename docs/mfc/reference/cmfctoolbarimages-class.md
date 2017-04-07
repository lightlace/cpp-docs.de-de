---
title: Klasse CMFCToolBarImages | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::AdaptColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::CleanUp
- AFXTOOLBARIMAGES/CMFCToolBarImages::Clear
- AFXTOOLBARIMAGES/CMFCToolBarImages::ConvertTo32Bits
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyImageToClipboard
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyTo
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateFromImageList
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateRegionFromImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::DeleteImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Draw
- AFXTOOLBARIMAGES/CMFCToolBarImages::DrawEx
- AFXTOOLBARIMAGES/CMFCToolBarImages::EnableRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::EndDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::ExtractIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::FillDitheredRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetBitsPerPixel
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetCount
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWell
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWellLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLastImageRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMask
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetResourceOffset
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetScale
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::GrayImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::Is32BitTransparencySupported
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsReadOnly
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsScaled
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsUserImagesList
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsValid
- AFXTOOLBARIMAGES/CMFCToolBarImages::Load
- AFXTOOLBARIMAGES/CMFCToolBarImages::LoadStr
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapFromSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapTo3dColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColorAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::Mirror
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmap
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmapVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::OnSysColorChange
- AFXTOOLBARIMAGES/CMFCToolBarImages::PrepareDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Save
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetSingleImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::SmoothResize
- AFXTOOLBARIMAGES/CMFCToolBarImages::UpdateImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::PreMultiplyAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::m_bDisableTrueColorAlpha
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarImages class
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: 31
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
ms.openlocfilehash: ff94497108033b17d52b79594fdbe30e8ed7da03
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarimages-class"></a>CMFCToolBarImages-Klasse
Die Bilder auf einer Symbolleiste. Die `CMFCToolBarImages` Klasse verwaltet die Symbolleistenbilder, die aus Anwendungsressourcen oder aus Dateien geladen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::CMFCToolBarImages](#cmfctoolbarimages)|Erstellt ein `CMFCToolBarImages`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::AdaptColors](#adaptcolors)||  
|[CMFCToolBarImages::AddIcon](#addicon)|Die Symbolleistenbilder hinzugefügt ein Symbol.|  
|[CMFCToolBarImages::AddImage](#addimage)|Die Symbolleistenbilder, die hinzugefügt eine Bitmap.|  
|[CMFCToolBarImages::CleanUp](#cleanup)||  
|[CMFCToolBarImages::Clear](#clear)|Gibt die Systemressourcen, die auf dieses Objekt frei.|  
|[CMFCToolBarImages::ConvertTo32Bits](#convertto32bits)|Konvertiert unterstrichen Bitmaps 32 Bpp-Bilder.|  
|[CMFCToolBarImages::CopyImageToClipboard](#copyimagetoclipboard)||  
|[CMFCToolBarImages::CopyTo](#copyto)||  
|[CMFCToolBarImages::CreateFromImageList](#createfromimagelist)|Initialisiert die Symbolleistenbilder, die aus einer Bildliste ( [CImageList-Klasse](../../mfc/reference/cimagelist-class.md)).|  
|[CMFCToolBarImages::CreateRegionFromImage](#createregionfromimage)||  
|[CMFCToolBarImages::DeleteImage](#deleteimage)|Löscht das Bild, das einen angegebenen Index aus der Symbolleistenbilder hat, wenn dieser Symbolleistenbilder, die benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::Draw](#draw)|Zeichnet ein Symbolleistenbild der einzelnen (Schaltfläche).|  
|[CMFCToolBarImages::DrawEx](#drawex)||  
|[CMFCToolBarImages::EnableRTL](#enablertl)||  
|[CMFCToolBarImages::EndDrawImage](#enddrawimage)|Nachdem Sie ein Symbolleistenbild gezeichnet wird, gibt Sie Systemressourcen frei.|  
|[CMFCToolBarImages::ExtractIcon](#extracticon)|Gibt das Symbol zurück, das einen angegebene Image Index über die Symbolleistenbilder aufweist.|  
|[CMFCToolBarImages::FillDitheredRect](#fillditheredrect)|Füllt ein Rechteck mit einem Pinsel, der über die Symbolleiste Hintergrundfarben verfügt.|  
|[CMFCToolBarImages::GetAlwaysLight](#getalwayslight)||  
|[CMFCToolBarImages::GetBitsPerPixel](#getbitsperpixel)|Aktuelle Auflösung des unterstrichenen Images zurückgegeben.|  
|[CMFCToolBarImages::GetCount](#getcount)|Gibt die Anzahl der Abbilder auf der Symbolleiste auf zurück.|  
|[CMFCToolBarImages::GetDisabledImageAlpha](#getdisabledimagealpha)|Gibt den alpha-Kanal-Wert, der für deaktivierte Bilder verwendet wird.|  
|[CMFCToolBarImages::GetFadedImageAlpha](#getfadedimagealpha)||  
|[CMFCToolBarImages::GetImageSize](#getimagesize)|Ruft die Größe der Symbolleistenbilder, die im Arbeitsspeicher (Größe der Datenquelle) gespeichert werden oder die Größe der Symbolleistenbilder, die auf dem Bildschirm (Größe) gezeichnet werden.|  
|[CMFCToolBarImages::GetImageWell](#getimagewell)|Gibt das Handle für die Bitmap, die alle Symbolleistenbilder enthält.|  
|[CMFCToolBarImages::GetImageWellLight](#getimagewelllight)||  
|[CMFCToolBarImages::GetLastImageRect](#getlastimagerect)||  
|[CMFCToolBarImages::GetLightPercentage](#getlightpercentage)||  
|[CMFCToolBarImages::GetMapTo3DColors](#getmapto3dcolors)||  
|[CMFCToolBarImages::GetMask](#getmask)||  
|[CMFCToolBarImages::GetResourceOffset](#getresourceoffset)|Gibt den Index des Bildes für eine angegebene Ressource-ID.|  
|[CMFCToolBarImages::GetScale](#getscale)|Gibt die aktuelle Skalierung unterstrichenen Images zurück.|  
|[CMFCToolBarImages::GetTransparentColor](#gettransparentcolor)||  
|[CMFCToolBarImages::GrayImages](#grayimages)|Die Symbolleistenbilder, die für eine deaktivierte aussehen wird abgeblendet.|  
|[CMFCToolBarImages::Is32BitTransparencySupported](#is32bittransparencysupported)|Bestimmt, ob das Betriebssystem 32-Bit-alpha-blending unterstützt.|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](#ispremultiplyautocheck)||  
|[CMFCToolBarImages::IsRTL](#isrtl)|Bestimmt, ob die Unterstützung für rechts-nach-links (RTL) aktiviert ist.|  
|[CMFCToolBarImages::IsReadOnly](#isreadonly)|Bestimmt, ob die Symbolleistenbilder, die schreibgeschützt sind.|  
|[CMFCToolBarImages::IsScaled](#isscaled)|Erfahren Sie, ob die unterstrichenen Bilder oder nicht skaliert werden.|  
|[CMFCToolBarImages::IsUserImagesList](#isuserimageslist)|Bestimmt, ob dieser Symbolleistenbilder, die benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::IsValid](#isvalid)|Bestimmt, ob dieser Symbolleistenbilder, die eine gültige Symbolleistenbild enthält.|  
|[CMFCToolBarImages::Load](#load)|Lädt Symbolleistenbilder, von Systemressourcen oder aus einer Datei.|  
|[CMFCToolBarImages::LoadStr](#loadstr)||  
|[CMFCToolBarImages::MapFromSysColor](#mapfromsyscolor)||  
|[CMFCToolBarImages::MapTo3dColors](#mapto3dcolors)||  
|[CMFCToolBarImages::MapToSysColor](#maptosyscolor)||  
|[CMFCToolBarImages::MapToSysColorAlpha](#maptosyscoloralpha)||  
|[CMFCToolBarImages::Mirror](#mirror)|Horizontal spiegelt alle Symbolleistenbilder.|  
|[CMFCToolBarImages::MirrorBitmap](#mirrorbitmap)|Horizontal spiegelt eine Bitmap.|  
|[CMFCToolBarImages::MirrorBitmapVert](#mirrorbitmapvert)||  
|[CMFCToolBarImages::MirrorVert](#mirrorvert)||  
|[CMFCToolBarImages::OnSysColorChange](#onsyscolorchange)||  
|[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)|Ordnet die Ressourcen, die erforderlich sind, um ein Symbolleistenbild in einer angegebenen Größe zu zeichnen.|  
|[CMFCToolBarImages::Save](#save)|Die Symbolleistenbilder in einer Datei gespeichert, wenn dieser Symbolleistenbilder, die benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::SetAlwaysLight](#setalwayslight)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha)|Legt den alpha-Kanal-Wert, der für deaktivierte Bilder verwendet wird.|  
|[CMFCToolBarImages::SetFadedImageAlpha](#setfadedimagealpha)||  
|[CMFCToolBarImages::SetImageSize](#setimagesize)|Legt die Größe eines Bilds Symbolleiste (Größe der Datenquelle).|  
|[CMFCToolBarImages::SetLightPercentage](#setlightpercentage)||  
|[CMFCToolBarImages::SetMapTo3DColors](#setmapto3dcolors)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](#setpremultiplyautocheck)||  
|[CMFCToolBarImages::SetSingleImage](#setsingleimage)||  
|[CMFCToolBarImages::SetTransparentColor](#settransparentcolor)|Legt die transparente Farbe der Symbolleistenbilder fest.|  
|[CMFCToolBarImages::SmoothResize](#smoothresize)|Ändert die reibungslos unterstrichen Bilder Größe.|  
|[CMFCToolBarImages::UpdateImage](#updateimage)|Aktualisiert eine benutzerdefinierte Symbolleiste-Image aus einer Bitmap.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](#premultiplyalpha)||  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::m_bDisableTrueColorAlpha](#m_bdisabletruecoloralpha)|`TRUE`Falls angegeben, Alphablending (32-Bit-Farbe) deaktiviert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die vollständige Bitmap der Symbolleistenbilder, die von verwalteten `CMFCToolbarImages` umfasst eine oder mehrere kleine Symbolleistenbilder (Schaltflächen) eine feste Größe.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie eine `CMFCToolBarImages` Objekt mit verschiedenen Methoden in der `CMFCToolBarImages` Klasse. Das Beispiel zeigt, wie legen Sie die Größe des Bilds Symbolleiste, ein Bild zu laden und die transparente Farbe des Bilds. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#32;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&33;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCToolBarImages`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarimages.h  
  
##  <a name="adaptcolors"></a>CMFCToolBarImages::AdaptColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AdaptColors(
    COLORREF clrBase,  
    COLORREF clrTone);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrBase`  
 [in] `clrTone`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addicon"></a>CMFCToolBarImages::AddIcon  
 Die Liste der Symbolleistenbilder, die hinzugefügt ein Symbol.  
  
```  
int AddIcon(
    HICON hIcon,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hIcon`  
 Ein Handle für das Symbol hinzugefügt werden.  
  
 [in] `bAlphaBlend`  
 `TRUE`Wenn dieses Symbol mit Alphablending verwendet wird. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Bilds Symbolleiste, das hinzugefügt wurde, wenn die Methode erfolgreich ist; andernfalls -1.  
  
##  <a name="addimage"></a>CMFCToolBarImages::AddImage  
 Die Symbolleistenbilder, die hinzugefügt eine Bitmap.  
  
```  
int AddImage(
    HBITMAP hbmp,  
    BOOL bSetBitPerPixel=FALSE);

int AddImage(
    const CMFCToolBarImages& imageList,  
    int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hbmp`  
 Das Handle für die Bitmap hinzu.  
  
 [in] `bSetBitPerPixel`  
 `TRUE`Wenn die `CMFCToolBarImages` Objekt verwendet die Farbtiefe (Bits pro Pixel), der das neue Abbild; `FALSE` Wenn das `CMFCToolbarImages` -Objekt hält die aktuelle Farbtiefe.  
  
 [in] `imageList`  
 Ein Verweis auf ein `CMFCToolbarImages` -Objekt, das das hinzuzufügende enthält.  
  
 [in] `nIndex`  
 Der Index in der Quelle `CMFCToolbarImages` Objekt des Bilds hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Symbolleiste von Bildern, die die `CMFCToolBarImages` -Objekt verwaltet wird, nachdem die neue Bitmap erfolgreich hinzugefügt wurde&1;, wenn der Vorgang fehlgeschlagen ist.  
  
##  <a name="cleanup"></a>CMFCToolBarImages::CleanUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall CleanUp();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="clear"></a>CMFCToolBarImages::Clear  
 Geben Sie Systemressourcen frei, die [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) Objekt zugewiesen.  
  
```  
void Clear();
```  
  
##  <a name="cmfctoolbarimages"></a>CMFCToolBarImages::CMFCToolBarImages  
 Erstellt ein `CMFCToolBarImages`-Objekt.  
  
```  
CMFCToolBarImages();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein `CMFCToolBarImages` Objekt, dessen Renderingmodul initialisiert und legt die Größe des Abbilds auf den Standardwert 16 x 15 Pixel. Verwendung [CMFCToolBarImages::SetImageSize](#setimagesize) die Größe des Abbilds zu ändern, bevor Sie Bilder hinzufügen.  
  
##  <a name="copyimagetoclipboard"></a>CMFCToolBarImages::CopyImageToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyImageToClipboard(int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iImage`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copyto"></a>CMFCToolBarImages::CopyTo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyTo(CMFCToolBarImages& imageList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `imageList`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="createfromimagelist"></a>CMFCToolBarImages::CreateFromImageList  
 Initialisiert die Symbolleistenbilder, die aus einer [CImageList-Klasse](../../mfc/reference/cimagelist-class.md) Objekt.  
  
```  
BOOL CreateFromImageList(const CImageList& imageList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `imageList`  
 Die Bildliste für Symbolleistenbilder, die als Quelle verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um der Liste Symbolleiste Bilder aus einer externen Bildliste schnell zu initialisieren.  
  
##  <a name="createregionfromimage"></a>CMFCToolBarImages::CreateRegionFromImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static HRGN __stdcall CreateRegionFromImage(
    HBITMAP bmp,  
    COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bmp`  
 [in] `clrTransparent`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="deleteimage"></a>CMFCToolBarImages::DeleteImage  
 Löscht das benutzerdefinierte Abbild, das einem angegebenen aus der Symbolleiste-Images Index.  
  
```  
BOOL DeleteImage(int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iImage`  
 Gibt den nullbasierten Index des Bilds zu löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Image erfolgreich gelöscht wurde. `FALSE` Bildindex ungültig, wird die `CMFCToolbarImages` Objekt ist temporär und die `CMFCToolbarImages` -Objekt enthält keine benutzerdefinierten Images, oder wenn ein anderer Fehler aufgetreten ist.  
  
##  <a name="draw"></a>CMFCToolBarImages::Draw  
 Zeichnet ein Bild in einzelne Symbolleiste.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int x,  
    int y,  
    int iImageIndex,  
    BOOL bHilite=FALSE,  
    BOOL bDisabled=FALSE,  
    BOOL bIndeterminate=FALSE,  
    BOOL bShadow=FALSE,  
    BOOL bInactive=FALSE,  
    BYTE alphaSrc=255);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `x`  
 Die X-Koordinate der linken Seite des Rechtecks, in dem das Bild ist, gezeichnet werden soll.  
  
 [in] `y`  
 Die Y-Koordinate des oberen Rands des Rechtecks, in dem das Bild ist, gezeichnet werden soll.  
  
 [in] `iImageIndex`  
 Der nullbasierte Index des Bilds angezeigt werden.  
  
 [in] `bHilite`  
 `TRUE`Wenn das Bild ist hervorgehoben werden. andernfalls `FALSE`.  
  
 [in] `bDisabled`  
 `TRUE`Wenn das Bild im deaktivierten Stil gezeichnet werden; andernfalls `FALSE`.  
  
 [in] `bIndeterminate`  
 `TRUE`Wenn das Bild ist in den unbestimmten Zustand Stil gezeichnet wird. andernfalls `FALSE`.  
  
 [in] `bShadow`  
 `TRUE`Wenn das Bild mit einem Schatten gezeichnet werden; andernfalls `FALSE`.  
  
 [in] `bInactive`  
 `TRUE`Wenn das Bild ist in den inaktiven Status Stil gezeichnet wird. andernfalls `FALSE`.  
  
 [in] `alphaSrc`  
 Der Wert des Alphakanals (Deckkraft). Ein Wert von 255 bedeutet das Bild gezeichneten undurchsichtig ist. Der Wert 0 bedeutet, dass das Bild transparent gezeichnet wird. Dieser Wert wird verwendet, nur für 32-Bit-Farbbildern und Bilder, die einen Windows Vista-Glas-Stil angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das angegebene Bild erfolgreich angezeigt wurde. `FALSE` Bildindex ist ungültig, oder ein anderer Fehler aufgetreten ist.  
  
##  <a name="drawex"></a>CMFCToolBarImages::DrawEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    CRect rect,  
    int iImageIndex,  
    ImageAlignHorz horzAlign = ImageAlignHorzLeft,  
    ImageAlignVert vertAlign = ImageAlignVertTop,  
    CRect rectSrc = CRect(0,
    0,
    0,
    0),  
    BYTE alphaSrc = 255);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `rect`  
 [in] `iImageIndex`  
 [in] `horzAlign`  
 [in] `vertAlign`  
 [in] `rectSrc`  
 [in] `0`  
 [in] `0)`  
 [in] `alphaSrc`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablertl"></a>CMFCToolBarImages::EnableRTL  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall EnableRTL(BOOL bIsRTL = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enddrawimage"></a>CMFCToolBarImages::EndDrawImage  
 Systemressourcen frei, [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage) zugewiesen, nachdem Sie ein Symbolleistenbild, durch Aufrufen von zeichnen [CMFCToolBarImages::Draw](#draw).  
  
```  
void EndDrawImage(CAfxDrawState& ds);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ds`  
 Ein Verweis auf die `CAfxDrawState` -Objekt, das an übergebene die `PrepareDrawImage` Methode.  
  
##  <a name="extracticon"></a>CMFCToolBarImages::ExtractIcon  
 Gibt das Symbol zurück, das einen angegebene Image Index über die Symbolleistenbilder aufweist.  
  
```  
HICON ExtractIcon(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der nullbasierte Index in der Bildliste, an der sich das Bild, das als Symbol extrahiert werden befindet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die extrahierten Symbol oder `NULL` Wenn `nIndex` liegt außerhalb des Bereichs.  
  
##  <a name="fillditheredrect"></a>CMFCToolBarImages::FillDitheredRect  
 Füllt ein Rechteck mit den Hintergrundfarben Symbolleiste.  
  
```  
static void FillDitheredRect(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Die Koordinaten eines Rechtecks ausfüllen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um ein Rechteck mit einer Farbe zu füllen, die den Durchschnitt der Systemfarben COLOR_BTNFACE und COLOR_BTNHIGHLIGHT haben. Wenn das System maximal 256 Farben verwendet, wird das Rechteck mit einem Dithering Muster aus diesen zwei Farben stattdessen gefüllt.  
  
##  <a name="getalwayslight"></a>CMFCToolBarImages::GetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetAlwaysLight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcount"></a>CMFCToolBarImages::GetCount  
 Gibt die Anzahl der Bilder in der Liste der Bilder Symbolleiste zurück.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bilder in der `CMFCToolBarImages` Objekt.  
  
##  <a name="getdisabledimagealpha"></a>CMFCToolBarImages::GetDisabledImageAlpha  
 Gibt den alpha-Kanal (Deckkraft)-Wert, der für deaktivierte Bilder verwendet wird.  
  
```  
static BYTE GetDisabledImageAlpha();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Wert der alpha-Kanal.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha) , den alpha-Kanal-Wert ändern.  
  
##  <a name="getfadedimagealpha"></a>CMFCToolBarImages::GetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BYTE __stdcall GetFadedImageAlpha();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getimagesize"></a>CMFCToolBarImages::GetImageSize  
 Ruft die Größe der Symbolleistenbilder, die im Arbeitsspeicher (Größe der Datenquelle) gespeichert werden oder die Größe der Symbolleistenbilder, die auf dem Bildschirm (Größe) gezeichnet werden.  
  
```  
SIZE GetImageSize(BOOL bDest=FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDest`  
 `TRUE`um die Größe abzurufen; `FALSE` um die Größe des Abbilds abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SIZE` -Struktur, die die Größe eines Bilds in Pixel angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe des Quellbilds ist die Größe der Bilder, die in gespeichert sind die [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) Objekt. Rufen Sie [CMFCToolBarImages::SetImageSize](#setimagesize) die Größe der Datenquelle festgelegt. Der Standardwert ist 16 x 15 Pixel.  
  
 Die Ziel-Bildgröße ist standardmäßig 0 x 0. Wenn Sie aufrufen, geben Sie die Zielgröße [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage). Die [CMFCToolBarImages::EndDrawImage](#enddrawimage) -Methode die Größe auf den Standardwert zurückgesetzt.  
  
##  <a name="getimagewell"></a>CMFCToolBarImages::GetImageWell  
 Gibt das Handle für die Bitmap, die alle Symbolleistenbilder enthält.  
  
```  
HBITMAP GetImageWell() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine Bitmap, die Symbolleistenbilder enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Symbolleistenbilder befinden sich in einer Zeile in einer einzelnen Bitmap, die als bezeichnet wird ein *Bildquelle*. Um eine Symbolleistenbild in den Image zu suchen, Multiplizieren Sie den Index des Bilds durch die Breite der Symbolleistenbilder (finden Sie unter [CMFCToolBarImages::GetImageSize](#getimagesize)) um den horizontalen Offset des Bilds in der Abbildung gut zu erhalten.  
  
##  <a name="getimagewelllight"></a>CMFCToolBarImages::GetImageWellLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetImageWellLight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlastimagerect"></a>CMFCToolBarImages::GetLastImageRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetLastImageRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlightpercentage"></a>CMFCToolBarImages::GetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetLightPercentage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmapto3dcolors"></a>CMFCToolBarImages::GetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetMapTo3DColors() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmask"></a>CMFCToolBarImages::GetMask  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetMask(int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iImage`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getresourceoffset"></a>CMFCToolBarImages::GetResourceOffset  
 Gibt den Index des Bildes für eine angegebene Ressource-ID.  
  
```  
int GetResourceOffset(UINT uiResId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiResId`  
 Ein Image-Ressourcen-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Eines Image-Index, wenn die Methode erfolgreich war;&1;, wenn das Bild mit der ID für die angegebene Ressource nicht vorhanden ist.  
  
##  <a name="gettransparentcolor"></a>CMFCToolBarImages::GetTransparentColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COLORREF GetTransparentColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="grayimages"></a>CMFCToolBarImages::GrayImages  
 Die Symbolleistenbilder, die für eine deaktivierte aussehen wird abgeblendet.  
  
```  
BOOL GrayImages(int nGrayImageLuminancePercentage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGrayImageLuminancePercentage`  
 Prozentsatz der Intensität.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Bilder in der Auflistung erfolgreich deaktiviert wurden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ändert die Symbolleistenbilder, die durch die roten, grünen und blauen Komponenten jedes Pixels Mittelwert und Multiplizieren des Ergebnisses von `nGrayImageLuminancePercentage` durch 100 dividiert. Wenn `nGrayImageLuminancePercentage` 0 (null) oder negativ ist, der Standardwert von 130 wird stattdessen verwendet.  
  
> [!NOTE]
>  Wenn Sie die Änderung rückgängig machen möchten, müssen Sie die Bilder aus der Quelle neu laden. Sie erreichen dies durch Aufrufen von [CMFCToolBarImages::Load](#load) oder [CMFCToolBarImages::UpdateImage](#updateimage) (nur für benutzerdefinierte Bilder), oder durch Aufrufen von [CMFCToolBarImages::Clear](#clear) und die Bilder erneut hinzufügen, durch Aufrufen [CMFCToolBarImages::AddIcon](#addicon) oder [CMFCToolBarImages::AddImage](#addimage).  
  
##  <a name="is32bittransparencysupported"></a>CMFCToolBarImages::Is32BitTransparencySupported  
 Gibt an, ob das Betriebssystem 32-Bit-alpha-blending unterstützt.  
  
```  
static BOOL Is32BitTransparencySupported();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn 32-Bit-alpha-blending unterstützt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese statische Methode, um zur Laufzeit zu bestimmen, ob das Betriebssystem 32-Bit-alpha-blending unterstützt. Diese Funktion wird in unterstützt [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] und höhere Versionen.  
  
##  <a name="ispremultiplyautocheck"></a>CMFCToolBarImages::IsPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPreMultiplyAutoCheck() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isreadonly"></a>CMFCToolBarImages::IsReadOnly  
 Gibt an, ob die Symbolleistenbilder, die schreibgeschützt sind.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Symbolleistenbilder, die schreibgeschützt sind `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCToolbarImages` Objekt ist schreibgeschützt, wenn die Bitmap mit Symbolleistenbilder, die aus einer schreibgeschützten Datei geladen wurde, oder wenn die Bitmap kopiert wurde, mit der `CMFCToolBarImages::CopyTemp` Methode.  
  
##  <a name="isrtl"></a>CMFCToolBarImages::IsRTL  
 Gibt an, ob Unterstützung für rechts-nach-links (RTL) aktiviert ist.  
  
```  
static BOOL IsRTL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn RTL-Unterstützung aktiviert ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 RTL-Unterstützung wird verwendet, wenn die Anwendung in einer Sprache lokalisiert ist, die von rechts nach links, wie z. B. Arabisch, Hebräisch, Persisch oder Urdu gelesen wird.  
  
##  <a name="isuserimageslist"></a>CMFCToolBarImages::IsUserImagesList  
 Gibt an, ob dieser Symbolleistenbilder, die benutzerdefinierte Bilder enthält.  
  
```  
BOOL IsUserImagesList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `CMFCToolBarImages` -Objekt enthält eine benutzerdefinierte Symbolleistenbilder andernfalls `FALSE`.  
  
##  <a name="isvalid"></a>CMFCToolBarImages::IsValid  
 Gibt an, ob dieser Symbolleistenbilder, die eine gültige Symbolleistenbild enthält.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein `CMFCToolBarImages` Objekt gültig ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCToolBarImages` -Objekt ist ungültig, wenn das Handle für eine Bitmap mit Symbolleistenbilder ist `NULL`.  
  
##  <a name="load"></a>CMFCToolBarImages::Load  
 Lädt Symbolleistenbilder, von Systemressourcen oder aus einer Datei.  
  
```  
BOOL Load(
    UINT uiResID,  
    HINSTANCE hinstRes=NULL,  
    BOOL bAdd=FALSE);

BOOL Load(
    LPCTSTR lpszBmpFileName,   
    DWORD nMaxFileSize = 819200);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiResID`  
 Die ID der Bitmap-Ressource.  
  
 [in] `hinstRes`  
 Eine Instanz des Ressourcen-DLL.  
  
 [in] `bAdd`  
 `TRUE`die vorhandenen Bitmap, die geladenen Bitmap hinzu oder `FALSE` vorhandenen Bitmap ersetzen.  
  
 [in] `lpszBmpFileName`  
 Ein Pfad in eine Datei aus dem Bitmap geladen werden soll.  
  
 [in] `nMaxFileSize`  
 Maximale Anzahl von Bytes in der Bitmapdatei; oder Laden Sie die Bitmap unabhängig von der Größe 0. Wenn die Größe der Datei diese maximale Größe überschreitet, gibt die Methode `FALSE` und die Bitmap wird nicht geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Bitmap erfolgreich geladen wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Datei, die nur-Lese Attribut aufweist, ist die Bildliste als schreibgeschützt markiert.  
  
##  <a name="loadstr"></a>CMFCToolBarImages::LoadStr  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL LoadStr(
    LPCTSTR lpszResourceName,  
    HINSTANCE hinstRes = NULL,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszResourceName`  
 [in] `hinstRes`  
 [in] `bAdd`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="mapfromsyscolor"></a>CMFCToolBarImages::MapFromSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapFromSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="mapto3dcolors"></a>CMFCToolBarImages::MapTo3dColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MapTo3dColors(
    BOOL bUseRGBQUAD = TRUE,  
    COLORREF clrSrc = (COLORREF)-1,  
    COLORREF clrDest = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bUseRGBQUAD`  
 [in] `clrSrc`  
 [in] `clrDest`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="maptosyscolor"></a>CMFCToolBarImages::MapToSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="maptosyscoloralpha"></a>CMFCToolBarImages::MapToSysColorAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColorAlpha(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="mirror"></a>CMFCToolBarImages::Mirror  
 Ersetzt die Symbolleistenbilder, die mit ihren horizontal gespiegelt.  
  
```  
BOOL Mirror();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Bilder erfolgreich gespiegelt wurden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist zur Unterstützung von rechts-nach-links-Schreibsysteme verwendet.  
  
##  <a name="mirrorbitmap"></a>CMFCToolBarImages::MirrorBitmap  
 Ersetzt eine Bitmap mit horizontalen Spiegelbild.  
  
```  
static BOOL MirrorBitmap(
    HBITMAP& hbmp,  
    int cxImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `hbmp`  
 Ein Handle für die Bitmap für die Spiegelung.  
  
 [in] `cxImage`  
 Die Breite des Bilds in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Bild erfolgreich gespiegelt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient zur Schreibsysteme von rechts-nach-links-Unterstützung.  
  
##  <a name="mirrorbitmapvert"></a>CMFCToolBarImages::MirrorBitmapVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall MirrorBitmapVert(
    HBITMAP& hbmp,  
    int cyImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hbmp`  
 [in] `cyImage`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="mirrorvert"></a>CMFCToolBarImages::MirrorVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MirrorVert();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsyscolorchange"></a>CMFCToolBarImages::OnSysColorChange  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="premultiplyalpha"></a>CMFCToolBarImages::PreMultiplyAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall PreMultiplyAlpha(
    HBITMAP hbmp,  
    BOOL bAutoCheckPremlt);

BOOL PreMultiplyAlpha(HBITMAP hbmp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hbmp`  
 [in] `bAutoCheckPremlt`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bdisabletruecoloralpha"></a>CMFCToolBarImages::m_bDisableTrueColorAlpha  
 `TRUE`Falls angegeben, Alphablending (32-Bit-Farbe) deaktiviert ist.  
  
```  
static BOOL m_bDisableTrueColorAlpha;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diese Membervariable auf `FALSE` angegeben, die für die Symbolleistenbilder, die Alpha-blending aktivieren.  
  
 Der Standardwert ist `TRUE` um Abwärtskompatibilität zu gewährleisten.  
  
##  <a name="preparedrawimage"></a>CMFCToolBarImages::PrepareDrawImage  
 Ordnet die Ressourcen, die erforderlich sind, um ein Symbolleistenbild in einer angegebenen Größe zu zeichnen.  
  
```  
BOOL PrepareDrawImage(
    CAfxDrawState& ds,  
    CSize sizeImageDest=CSize(0,
    0)  
    BOOL bFadeInactive=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ds`  
 Ein Verweis auf `CAfxDrawState` -Struktur, die die zugeordneten Ressourcen zwischen Phasen der Image-Rendering speichert.  
  
 [in] `sizeImageDest`  
 Gibt die Größe eines Bilds Ziel.  
  
 [in] `bFadeInactive`  
 `TRUE`Fehler bei Bilder gezeichnet werden, wenn deaktiviert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Ressourcen, die zum Zeichnen des Bilds Symbolleiste erfolgreich, andernfalls belegten `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf dieser Methode können Sie aufrufen [CMFCToolBarImages::Draw](#draw) oft. Wenn Sie Zeichnung abgeschlossen haben, müssen Sie aufrufen [CMFCToolBarImages::EndDrawImage](#enddrawimage) , vom reservierten Ressourcen freizugeben `PrepareDrawImage`.  
  
##  <a name="save"></a>CMFCToolBarImages::Save  
 Die Symbolleistenbilder in einer Datei gespeichert, wenn dieser Symbolleistenbilder, die benutzerdefinierte Bilder enthält.  
  
```  
BOOL Save(LPCTSTR lpszBmpFileName=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszBmpFileName`  
 Ein Pfad zu einer Datenträgerdatei.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Symbolleistenbilder erfolgreich gespeichert wurden. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die benutzerdefinierte Bilder in eine Datei zu speichern. Wenn `lpszBmpFileName` ist `NULL`, die-Methode speichert die Bitmap in die Datei aus dem Bitmap, durch geladen wurde die [CMFCToolBarImages::Load](#load) Methode.  
  
##  <a name="setalwayslight"></a>CMFCToolBarImages::SetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetAlwaysLight(BOOL bAlwaysLight = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAlwaysLight`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdisabledimagealpha"></a>CMFCToolBarImages::SetDisabledImageAlpha  
 Legt den alpha-Kanal (Deckkraft)-Wert, der für deaktivierte Bilder verwendet wird.  
  
```  
static void SetDisabledImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nValue`  
 Der neue Wert des Alphakanals.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen benutzerdefinierten Alphawert für deaktivierte Bilder festzulegen. Der Standardwert ist 127, wodurch deaktivierte Schaltflächenbilder halbtransparent sein. Wenn Sie den Wert 0 festlegen, werden deaktiviert Bilder vollständig transparent. Wenn Sie einen Wert von 255 festlegen, werden deaktiviert Bilder transparent.  
  
##  <a name="setfadedimagealpha"></a>CMFCToolBarImages::SetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall SetFadedImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nValue`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setimagesize"></a>CMFCToolBarImages::SetImageSize  
 Legt die Größe jedes Bilds Symbolleiste (Größe der Datenquelle).  
  
```  
void SetImageSize(
    SIZE sizeImage,  
    BOOL bUpdateCount=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `sizeImage`  
 Die neue Größe der Symbolleistenbilder.  
  
### <a name="remarks"></a>Hinweise  
 Ist Sie standardmäßig die Größe des Bilds Symbolleiste 16 x 15 Pixel. Aufgerufen Sie diese Methode wird, wenn Sie Symbolleistenbilder, die mit einer anderen Größe verwenden möchten.  
  
##  <a name="setlightpercentage"></a>CMFCToolBarImages::SetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetLightPercentage(int nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nValue`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setmapto3dcolors"></a>CMFCToolBarImages::SetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMapTo3DColors(BOOL bMapTo3DColors);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMapTo3DColors`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpremultiplyautocheck"></a>CMFCToolBarImages::SetPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPreMultiplyAutoCheck(BOOL bAuto = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAuto`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setsingleimage"></a>CMFCToolBarImages::SetSingleImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetSingleImage();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settransparentcolor"></a>CMFCToolBarImages::SetTransparentColor  
 Legt die transparente Farbe der Symbolleistenbilder fest.  
  
```  
COLORREF SetTransparentColor(COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrTransparent`  
 RGB-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen transparente Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie oder das Framework Aufrufen [CMFCToolBarImages::Draw](#draw), zeichnet die Methode keine Pixel, die der angegebenen Farbe entspricht `clrTransparent`.  
  
##  <a name="updateimage"></a>CMFCToolBarImages::UpdateImage  
 Aktualisiert eine benutzerdefinierte Symbolleiste-Image aus einer Bitmap.  
  
```  
BOOL UpdateImage(
    int iImage,  
    HBITMAP hbmp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iImage`  
 Der nullbasierte Index des Bilds zu aktualisieren.  
  
 [in] `hbmp`  
 Ein Handle für die Bitmap aus dem das Abbild zu aktualisieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Image erfolgreich aktualisiert wurde; `FALSE` ist die Bildliste nicht benutzerdefiniert oder temporäre.  
  
##  <a name="convertto32bits"></a>CMFCToolBarImages::ConvertTo32Bits  
 Konvertiert unterstrichen Bitmaps 32 Bpp-Bilder.  
  
```  
BOOL ConvertTo32Bits(COLORREF clrTransparent = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 `clrTransparent`  
 Gibt die transparente Farbe des unterstrichenen Bitmaps.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getbitsperpixel"></a>CMFCToolBarImages::GetBitsPerPixel  
 Aktuelle Auflösung des unterstrichenen Images zurückgegeben.  
  
```  
int GetBitsPerPixel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die aktuelle Auflösung des unterstrichenen Bilder in Bits pro Pixel (Bpp) darstellt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getscale"></a>CMFCToolBarImages::GetScale  
 Gibt den aktuellen Skalierung unterstrichenen Images.  
  
```  
double GetScale() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der die aktuelle Skalierung.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isscaled"></a>CMFCToolBarImages::IsScaled  
 Erfahren Sie, ob die unterstrichenen Bilder oder nicht skaliert werden.  
  
```  
BOOL IsScaled () const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn unterstrichenen Bilder skaliert werden. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="smoothresize"></a>CMFCToolBarImages::SmoothResize  
 Ändert die reibungslos unterstrichen Bilder Größe.  
  
```  
BOOL SmoothResize(double dblImageScale);
```  
  
### <a name="parameters"></a>Parameter  
 `dblImageScale`  
 Skalierung.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Größe erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)

