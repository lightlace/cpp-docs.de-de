---
title: CMFCToolBarImages Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarImages [MFC], CMFCToolBarImages
- CMFCToolBarImages [MFC], AdaptColors
- CMFCToolBarImages [MFC], AddIcon
- CMFCToolBarImages [MFC], AddImage
- CMFCToolBarImages [MFC], CleanUp
- CMFCToolBarImages [MFC], Clear
- CMFCToolBarImages [MFC], ConvertTo32Bits
- CMFCToolBarImages [MFC], CopyImageToClipboard
- CMFCToolBarImages [MFC], CopyTo
- CMFCToolBarImages [MFC], CreateFromImageList
- CMFCToolBarImages [MFC], CreateRegionFromImage
- CMFCToolBarImages [MFC], DeleteImage
- CMFCToolBarImages [MFC], Draw
- CMFCToolBarImages [MFC], DrawEx
- CMFCToolBarImages [MFC], EnableRTL
- CMFCToolBarImages [MFC], EndDrawImage
- CMFCToolBarImages [MFC], ExtractIcon
- CMFCToolBarImages [MFC], FillDitheredRect
- CMFCToolBarImages [MFC], GetAlwaysLight
- CMFCToolBarImages [MFC], GetBitsPerPixel
- CMFCToolBarImages [MFC], GetCount
- CMFCToolBarImages [MFC], GetDisabledImageAlpha
- CMFCToolBarImages [MFC], GetFadedImageAlpha
- CMFCToolBarImages [MFC], GetImageSize
- CMFCToolBarImages [MFC], GetImageWell
- CMFCToolBarImages [MFC], GetImageWellLight
- CMFCToolBarImages [MFC], GetLastImageRect
- CMFCToolBarImages [MFC], GetLightPercentage
- CMFCToolBarImages [MFC], GetMapTo3DColors
- CMFCToolBarImages [MFC], GetMask
- CMFCToolBarImages [MFC], GetResourceOffset
- CMFCToolBarImages [MFC], GetScale
- CMFCToolBarImages [MFC], GetTransparentColor
- CMFCToolBarImages [MFC], GrayImages
- CMFCToolBarImages [MFC], Is32BitTransparencySupported
- CMFCToolBarImages [MFC], IsPreMultiplyAutoCheck
- CMFCToolBarImages [MFC], IsRTL
- CMFCToolBarImages [MFC], IsReadOnly
- CMFCToolBarImages [MFC], IsScaled
- CMFCToolBarImages [MFC], IsUserImagesList
- CMFCToolBarImages [MFC], IsValid
- CMFCToolBarImages [MFC], Load
- CMFCToolBarImages [MFC], LoadStr
- CMFCToolBarImages [MFC], MapFromSysColor
- CMFCToolBarImages [MFC], MapTo3dColors
- CMFCToolBarImages [MFC], MapToSysColor
- CMFCToolBarImages [MFC], MapToSysColorAlpha
- CMFCToolBarImages [MFC], Mirror
- CMFCToolBarImages [MFC], MirrorBitmap
- CMFCToolBarImages [MFC], MirrorBitmapVert
- CMFCToolBarImages [MFC], MirrorVert
- CMFCToolBarImages [MFC], OnSysColorChange
- CMFCToolBarImages [MFC], PrepareDrawImage
- CMFCToolBarImages [MFC], Save
- CMFCToolBarImages [MFC], SetAlwaysLight
- CMFCToolBarImages [MFC], SetDisabledImageAlpha
- CMFCToolBarImages [MFC], SetFadedImageAlpha
- CMFCToolBarImages [MFC], SetImageSize
- CMFCToolBarImages [MFC], SetLightPercentage
- CMFCToolBarImages [MFC], SetMapTo3DColors
- CMFCToolBarImages [MFC], SetPreMultiplyAutoCheck
- CMFCToolBarImages [MFC], SetSingleImage
- CMFCToolBarImages [MFC], SetTransparentColor
- CMFCToolBarImages [MFC], SmoothResize
- CMFCToolBarImages [MFC], UpdateImage
- CMFCToolBarImages [MFC], PreMultiplyAlpha
- CMFCToolBarImages [MFC], m_bDisableTrueColorAlpha
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b557a56b1d525941c96b9a6a96fd367b64afcaf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbarimages-class"></a>CMFCToolBarImages-Klasse
Die Bilder auf einer Symbolleiste. Die `CMFCToolBarImages` Klasse verwaltet die Symbolleistenbilder aus Anwendungsressourcen oder aus Dateien geladen.  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::CMFCToolBarImages](#cmfctoolbarimages)|Erstellt ein `CMFCToolBarImages`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::AdaptColors](#adaptcolors)||  
|[CMFCToolBarImages::AddIcon](#addicon)|Ein Symbol und die Symbolleistenbilder hinzugefügt.|  
|[CMFCToolBarImages::AddImage](#addimage)|Die Symbolleistenbilder hinzugefügt eine Bitmap.|  
|[CMFCToolBarImages::CleanUp](#cleanup)||  
|[CMFCToolBarImages::Clear](#clear)|Gibt die Systemressourcen, die diesem Objekt zugewiesen wurden.|  
|[CMFCToolBarImages::ConvertTo32Bits](#convertto32bits)|Konvertiert unterstrichen Bitmaps auf 32 Bpp Bilder.|  
|[CMFCToolBarImages::CopyImageToClipboard](#copyimagetoclipboard)||  
|[CMFCToolBarImages::CopyTo](#copyto)||  
|[CMFCToolBarImages::CreateFromImageList](#createfromimagelist)|Initialisiert die Symbolleistenbilder aus einer Bildliste ( [CImageList-Klasse](../../mfc/reference/cimagelist-class.md)).|  
|[CMFCToolBarImages::CreateRegionFromImage](#createregionfromimage)||  
|[CMFCToolBarImages::DeleteImage](#deleteimage)|Löscht das Bild, das einen angegebenen Index aus der Symbolleistenbilder hat, wenn dieser Satz von symbolleistenbildern benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::Draw](#draw)|Zeichnet ein einzelnes Symbolleistenbild (Schaltfläche).|  
|[CMFCToolBarImages::DrawEx](#drawex)||  
|[CMFCToolBarImages::EnableRTL](#enablertl)||  
|[CMFCToolBarImages::EndDrawImage](#enddrawimage)|Ressourcen werden freigegeben, nachdem ein Symbolleistenbild gezeichnet wird.|  
|[CMFCToolBarImages::ExtractIcon](#extracticon)|Gibt das Symbol zurück, das eine angegebene Abbildindex aus die Symbolleistenbilder verfügt.|  
|[CMFCToolBarImages::FillDitheredRect](#fillditheredrect)|Füllt ein Rechteck durch Verwenden eines Pinsels, das über die Symbolleiste Hintergrundfarben verfügt.|  
|[CMFCToolBarImages::GetAlwaysLight](#getalwayslight)||  
|[CMFCToolBarImages::GetBitsPerPixel](#getbitsperpixel)|Aktuelle Auflösung der unterstrichenen Images zurückgegeben.|  
|[CMFCToolBarImages::GetCount](#getcount)|Gibt die Anzahl von Images auf der Symbolleiste.|  
|[CMFCToolBarImages::GetDisabledImageAlpha](#getdisabledimagealpha)|Gibt den alpha-Kanal-Wert, der für deaktivierte Images verwendet wird.|  
|[CMFCToolBarImages::GetFadedImageAlpha](#getfadedimagealpha)||  
|[CMFCToolBarImages::GetImageSize](#getimagesize)|Ruft die Größe der die Symbolleistenbilder, die im Arbeitsspeicher (Quellvolume) gespeichert sind, oder die Größe der die Symbolleistenbilder, die auf dem Bildschirm (Zielgröße) gezeichnet werden.|  
|[CMFCToolBarImages::GetImageWell](#getimagewell)|Gibt das Handle für die Bitmap, die die Symbolleistenbilder enthält.|  
|[CMFCToolBarImages::GetImageWellLight](#getimagewelllight)||  
|[CMFCToolBarImages::GetLastImageRect](#getlastimagerect)||  
|[CMFCToolBarImages::GetLightPercentage](#getlightpercentage)||  
|[CMFCToolBarImages::GetMapTo3DColors](#getmapto3dcolors)||  
|[CMFCToolBarImages::GetMask](#getmask)||  
|[CMFCToolBarImages::GetResourceOffset](#getresourceoffset)|Gibt den Index des Bildes für eine angegebene Ressource-ID.|  
|[CMFCToolBarImages::GetScale](#getscale)|Gibt die aktuelle Skalierung unterstrichenen Bilder zurück.|  
|[CMFCToolBarImages::GetTransparentColor](#gettransparentcolor)||  
|[CMFCToolBarImages::GrayImages](#grayimages)|Abgeblendet die Symbolleistenbilder, um sie deaktivierte aussehen zu lassen.|  
|[CMFCToolBarImages::Is32BitTransparencySupported](#is32bittransparencysupported)|Bestimmt, ob das Betriebssystem Alphablending 32-Bit unterstützt.|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](#ispremultiplyautocheck)||  
|[CMFCToolBarImages::IsRTL](#isrtl)|Bestimmt, ob die Unterstützung für rechts-nach-links (RTL) aktiviert ist.|  
|[CMFCToolBarImages::IsReadOnly](#isreadonly)|Bestimmt, ob die Symbolleistenbilder schreibgeschützt sind.|  
|[CMFCToolBarImages::IsScaled](#isscaled)|Erfahren Sie, ob die unterstrichenen Bilder oder nicht skaliert werden.|  
|[CMFCToolBarImages::IsUserImagesList](#isuserimageslist)|Bestimmt, ob dieser Satz von symbolleistenbildern benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::IsValid](#isvalid)|Bestimmt, ob dieser Satz von symbolleistenbildern eine gültige Symbolleistenbild enthält.|  
|[CMFCToolBarImages::Load](#load)|Lädt Symbolleistenbilder aus, von Systemressourcen oder aus einer Datei.|  
|[CMFCToolBarImages::LoadStr](#loadstr)||  
|[CMFCToolBarImages::MapFromSysColor](#mapfromsyscolor)||  
|[CMFCToolBarImages::MapTo3dColors](#mapto3dcolors)||  
|[CMFCToolBarImages::MapToSysColor](#maptosyscolor)||  
|[CMFCToolBarImages::MapToSysColorAlpha](#maptosyscoloralpha)||  
|[CMFCToolBarImages::Mirror](#mirror)|Spiegelt horizontal aller die Symbolleistenbilder aus.|  
|[CMFCToolBarImages::MirrorBitmap](#mirrorbitmap)|Horizontal spiegelt eine Bitmap.|  
|[CMFCToolBarImages::MirrorBitmapVert](#mirrorbitmapvert)||  
|[CMFCToolBarImages::MirrorVert](#mirrorvert)||  
|[CMFCToolBarImages::OnSysColorChange](#onsyscolorchange)||  
|[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)|Ordnet die Ressourcen, die erforderlich sind, um ein Symbolleistenbild bei einer angegebenen Größe zu zeichnen.|  
|[CMFCToolBarImages::Save](#save)|Speichert die Symbolleistenbilder in einer Datei an, wenn dieser Satz von symbolleistenbildern benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::SetAlwaysLight](#setalwayslight)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha)|Legt den alpha-Kanal-Wert, der für deaktivierte Images verwendet wird.|  
|[CMFCToolBarImages::SetFadedImageAlpha](#setfadedimagealpha)||  
|[CMFCToolBarImages::SetImageSize](#setimagesize)|Legt die Größe des ein Symbolleistenbild (Größe der Datenquelle).|  
|[CMFCToolBarImages::SetLightPercentage](#setlightpercentage)||  
|[CMFCToolBarImages::SetMapTo3DColors](#setmapto3dcolors)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](#setpremultiplyautocheck)||  
|[CMFCToolBarImages::SetSingleImage](#setsingleimage)||  
|[CMFCToolBarImages::SetTransparentColor](#settransparentcolor)|Legt die transparente Farbe des die Symbolleistenbilder fest.|  
|[CMFCToolBarImages::SmoothResize](#smoothresize)|Ändert die unterstrichenen Bilder reibungslos Größe.|  
|[CMFCToolBarImages::UpdateImage](#updateimage)|Aktualisiert eine benutzerdefinierte Symbolleiste-Image aus einer Bitmap.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](#premultiplyalpha)||  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarImages::m_bDisableTrueColorAlpha](#m_bdisabletruecoloralpha)|`TRUE`Wenn angegeben, Alphablending (32-Bit-Farbe) deaktiviert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Das vollständige Bitmuster der Symbolleistenbilder, die von verwalteten `CMFCToolbarImages` besteht aus einer oder mehreren kleinen Symbolleistenbilder (Schaltflächen) eine feste Größe.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Konfigurieren einer `CMFCToolBarImages` -Objekt mithilfe verschiedener Methoden in der `CMFCToolBarImages` Klasse. Das Beispiel zeigt, wie legen Sie die Größe des Bilds Symbolleiste, ein Bild laden, und legen Sie die transparente Farbe des Bilds. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#32](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#33](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCToolBarImages`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarimages.h  
  
##  <a name="adaptcolors"></a>CMFCToolBarImages::AdaptColors  

  
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
 Die Liste der Symbolleistenbilder hinzugefügt ein Symbol.  
  
```  
int AddIcon(
    HICON hIcon,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hIcon`  
 Ein Handle für das Symbol "hinzugefügt werden.  
  
 [in] `bAlphaBlend`  
 `TRUE`Wenn dieses Symbol mit Alphablending verwendet wird. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Bilds Symbolleiste, die hinzugefügt wurde, wenn die Methode erfolgreich ist; andernfalls -1.  
  
##  <a name="addimage"></a>CMFCToolBarImages::AddImage  
 Die Symbolleistenbilder hinzugefügt eine Bitmap.  
  
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
 Das Handle für die Bitmap um hinzuzufügen.  
  
 [in] `bSetBitPerPixel`  
 `TRUE`Wenn die `CMFCToolBarImages` Objekt verwendet, die Farbtiefe (Bits pro Pixel) des neuen Images; `FALSE` Wenn die `CMFCToolbarImages` -Objekt hält den aktuellen Farbtiefe.  
  
 [in] `imageList`  
 Ein Verweis auf eine `CMFCToolbarImages` Objekt mit dem Bild hinzufügen.  
  
 [in] `nIndex`  
 Der Index in der Quelle `CMFCToolbarImages` des Bilds hinzuzufügende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Symbolleiste Bilder, die die `CMFCToolBarImages` -Objekt verwaltet wird, nachdem die neue Bitmap erfolgreich hinzugefügt wurde 1, wenn der Vorgang ist fehlgeschlagen.  
  
##  <a name="cleanup"></a>CMFCToolBarImages::CleanUp  

  
```  
static void __stdcall CleanUp();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="clear"></a>CMFCToolBarImages::Clear  
 Gibt die Systemressourcen frei, die die [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) Objekt zugeordnet.  
  
```  
void Clear();
```  
  
##  <a name="cmfctoolbarimages"></a>CMFCToolBarImages::CMFCToolBarImages  
 Erstellt ein `CMFCToolBarImages`-Objekt.  
  
```  
CMFCToolBarImages();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein `CMFCToolBarImages` Objekt, dessen Renderingmodul initialisiert und legt die Bildgröße auf seinen Standardwert 16 x 15 Pixel. Verwendung [CMFCToolBarImages::SetImageSize](#setimagesize) um die Bildgröße zu ändern, bevor Sie Bilder hinzufügen.  
  
##  <a name="copyimagetoclipboard"></a>CMFCToolBarImages::CopyImageToClipboard  

  
```  
BOOL CopyImageToClipboard(int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iImage`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copyto"></a>CMFCToolBarImages::CopyTo  

  
```  
BOOL CopyTo(CMFCToolBarImages& imageList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `imageList`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="createfromimagelist"></a>CMFCToolBarImages::CreateFromImageList  
 Initialisiert die Symbolleistenbilder aus einem [CImageList-Klasse](../../mfc/reference/cimagelist-class.md) Objekt.  
  
```  
BOOL CreateFromImageList(const CImageList& imageList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `imageList`  
 Die Bildliste für Symbolleistenbilder als Quelle verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Bilder für Symbolleisten aus einer externen Bildliste schnell zu initialisieren.  
  
##  <a name="createregionfromimage"></a>CMFCToolBarImages::CreateRegionFromImage  

  
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
 Löscht den benutzerdefinierten Image mit einem angegebenen Index aus der Symbolleistenbilder an.  
  
```  
BOOL DeleteImage(int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iImage`  
 Gibt den nullbasierten Index des Bilds zu löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Abbild wurde erfolgreich gelöscht wurde. `FALSE` ist die Abbildindex ungültig, wird die `CMFCToolbarImages` Objekt ist temporär und die `CMFCToolbarImages` Objekt enthält keine benutzerdefinierten Images, oder wenn ein anderer Fehler aufgetreten ist.  
  
##  <a name="draw"></a>CMFCToolBarImages::Draw  
 Zeichnet ein Bild in einzelne Symbolleiste an.  
  
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
 `TRUE`Wenn das Bild ist, im deaktivierten Stile gezeichnet werden soll; andernfalls `FALSE`.  
  
 [in] `bIndeterminate`  
 `TRUE`Wenn das Bild in den unbestimmten Zustand Stil gezeichnet werden soll ist. andernfalls `FALSE`.  
  
 [in] `bShadow`  
 `TRUE`Wenn das Bild ist, mit einem Schatten gezeichnet werden soll; andernfalls `FALSE`.  
  
 [in] `bInactive`  
 `TRUE`Wenn das Bild in den inaktiven Status Stil gezeichnet werden soll ist. andernfalls `FALSE`.  
  
 [in] `alphaSrc`  
 Der Wert alpha-Kanal (Deckkraft). Ein Wert von 255 bedeutet das Bild gezeichnet deckend ist. Der Wert 0 bedeutet, dass das Bild gezeichnet wird transparent. Dieser Wert wird verwendet, nur für 32-Bit-Farbe Bilder und Bilder, die ein Windows Vista-Glass-Format angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das angegebene Image erfolgreich angezeigt wurde. `FALSE` Bildindex war ungültig, oder ein anderer Fehler aufgetreten ist.  
  
##  <a name="drawex"></a>CMFCToolBarImages::DrawEx  

  
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

  
```  
static void __stdcall EnableRTL(BOOL bIsRTL = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enddrawimage"></a>CMFCToolBarImages::EndDrawImage  
 Systemressourcen frei, [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage) zugewiesen, nachdem Sie ein Symbolleistenbild durch Aufrufen von zeichnen [CMFCToolBarImages::Draw](#draw).  
  
```  
void EndDrawImage(CAfxDrawState& ds);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ds`  
 Ein Verweis auf die `CAfxDrawState` -Objekt, das übergeben wurde die `PrepareDrawImage` Methode.  
  
##  <a name="extracticon"></a>CMFCToolBarImages::ExtractIcon  
 Gibt das Symbol zurück, das eine angegebene Abbildindex aus die Symbolleistenbilder verfügt.  
  
```  
HICON ExtractIcon(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der nullbasierte Index in der Bildliste, an der sich das Bild, das als Symbol extrahiert werden befindet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das extrahierte Symbol oder `NULL` Wenn `nIndex` liegt außerhalb des gültigen Bereichs.  
  
##  <a name="fillditheredrect"></a>CMFCToolBarImages::FillDitheredRect  
 Füllt ein Rechteck mit den Hintergrundfarben Symbolleiste an.  
  
```  
static void FillDitheredRect(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Die Koordinaten eines Rechtecks, das zum ausfüllen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um ein Rechteck mit Farbe gefüllt, die den Durchschnitt der Systemfarben COLOR_BTNFACE und COLOR_BTNHIGHLIGHT ist. Wenn das System maximal 256 Farben verwendet wird, wird das Rechteck stattdessen mit ein gedithertes Muster von diese zwei Farben gefüllt werden soll.  
  
##  <a name="getalwayslight"></a>CMFCToolBarImages::GetAlwaysLight  

  
```  
BOOL GetAlwaysLight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcount"></a>CMFCToolBarImages::GetCount  
 Gibt die Anzahl der Bilder in der Liste der Images Symbolleiste zurück.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Bildern in das `CMFCToolBarImages` Objekt.  
  
##  <a name="getdisabledimagealpha"></a>CMFCToolBarImages::GetDisabledImageAlpha  
 Gibt den alpha-Kanal (Deckkraft)-Wert, der für deaktivierte Images verwendet wird.  
  
```  
static BYTE GetDisabledImageAlpha();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Wert der alpha-Kanal.  
  
### <a name="remarks"></a>Hinweise  
 Sie können Aufrufen [CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha) zum Ändern des Werts alpha-Kanal.  
  
##  <a name="getfadedimagealpha"></a>CMFCToolBarImages::GetFadedImageAlpha  

  
```  
static BYTE __stdcall GetFadedImageAlpha();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getimagesize"></a>CMFCToolBarImages::GetImageSize  
 Ruft die Größe der die Symbolleistenbilder, die im Arbeitsspeicher (Quellvolume) gespeichert sind, oder die Größe der die Symbolleistenbilder, die auf dem Bildschirm (Zielgröße) gezeichnet werden.  
  
```  
SIZE GetImageSize(BOOL bDest=FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDest`  
 `TRUE`um die Größe abzurufen; `FALSE` die Bildgröße Quelle abrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SIZE` -Struktur, die die Größe eines Bilds in Pixel angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe des Quellbilds ist die Größe der Bilder, die im rowsetcache der [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) Objekt. Sie können Aufrufen [CMFCToolBarImages::SetImageSize](#setimagesize) die Größe der Datenquelle festgelegt. Der Standardwert ist 16 x 15 Pixel.  
  
 Standardmäßig ist die Destination Imagegröße 0 x 0. Wenn Sie aufrufen, geben Sie die Zielgröße [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage). Die [CMFCToolBarImages::EndDrawImage](#enddrawimage) Methode wird die Größe auf den Standardwert zurückgesetzt.  
  
##  <a name="getimagewell"></a>CMFCToolBarImages::GetImageWell  
 Gibt das Handle für die Bitmap, die die Symbolleistenbilder enthält.  
  
```  
HBITMAP GetImageWell() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine Bitmap, die Symbolleistenbilder enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Symbolleistenbilder befinden sich in einer Zeile in eine einzelne Bitmap, die als bekannt ist ein *Image gut*. Multiplizieren Sie den Index des Bilds ein Symbolleistenbild in das Image gut feststellen, von der Breite der die Symbolleistenbilder (finden Sie unter [CMFCToolBarImages::GetImageSize](#getimagesize)) um den horizontalen Offset des Bilds in der Abbildung gut zu erhalten.  
  
##  <a name="getimagewelllight"></a>CMFCToolBarImages::GetImageWellLight  

  
```  
HBITMAP GetImageWellLight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlastimagerect"></a>CMFCToolBarImages::GetLastImageRect  

  
```  
CRect GetLastImageRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlightpercentage"></a>CMFCToolBarImages::GetLightPercentage  

  
```  
int GetLightPercentage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmapto3dcolors"></a>CMFCToolBarImages::GetMapTo3DColors  

  
```  
BOOL GetMapTo3DColors() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmask"></a>CMFCToolBarImages::GetMask  

  
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
 Einen Abbildindex, wenn die Methode erfolgreich ausgeführt wurde; -1, wenn das Image mit der ID für die angegebene Ressource nicht vorhanden ist.  
  
##  <a name="gettransparentcolor"></a>CMFCToolBarImages::GetTransparentColor  

  
```  
COLORREF GetTransparentColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="grayimages"></a>CMFCToolBarImages::GrayImages  
 Abgeblendet die Symbolleistenbilder, um sie deaktivierte aussehen zu lassen.  
  
```  
BOOL GrayImages(int nGrayImageLuminancePercentage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGrayImageLuminancePercentage`  
 Intensität Prozentsatz.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Bilder in der Auflistung erfolgreich deaktiviert wurden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ändert die Symbolleistenbilder durch Ermitteln des Durchschnitts der Rot-, Grün- und blauen-Komponenten von jedem Pixel und Multiplizieren des Ergebnisses durch `nGrayImageLuminancePercentage` durch 100 dividiert. Wenn `nGrayImageLuminancePercentage` 0 (null) oder negativ ist, der Standardwert von 130 wird stattdessen verwendet.  
  
> [!NOTE]
>  Wenn Sie die Änderung rückgängig machen möchten, müssen Sie die Bilder aus der Quelle neu laden. Hierzu können Sie durch Aufrufen von [CMFCToolBarImages::Load](#load) oder [CMFCToolBarImages::UpdateImage](#updateimage) (nur für benutzerdefinierte Bilder), oder durch Aufrufen von [CMFCToolBarImages::Clear](#clear)und die Bilder erneut hinzufügen, durch Aufrufen [CMFCToolBarImages::AddIcon](#addicon) oder [CMFCToolBarImages::AddImage](#addimage).  
  
##  <a name="is32bittransparencysupported"></a>CMFCToolBarImages::Is32BitTransparencySupported  
 Gibt an, ob das Betriebssystem Alphablending 32-Bit unterstützt.  
  
```  
static BOOL Is32BitTransparencySupported();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn es sich bei 32-Bit-Alphablending unterstützt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese statische Methode, um zur Laufzeit zu bestimmen, ob das Betriebssystem Alphablending 32-Bit unterstützt. Diese Funktion wird auf unterstützt [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] und höheren Versionen.  
  
##  <a name="ispremultiplyautocheck"></a>CMFCToolBarImages::IsPreMultiplyAutoCheck  

  
```  
BOOL IsPreMultiplyAutoCheck() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isreadonly"></a>CMFCToolBarImages::IsReadOnly  
 Gibt an, ob die Symbolleistenbilder schreibgeschützt sind.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Symbolleistenbilder schreibgeschützt sind `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCToolbarImages` Objekt ist schreibgeschützt, wenn die Bitmap mit Symbolleistenbilder aus einer schreibgeschützten Datei geladen wurde oder wenn die Bitmap kopiert wurde, sich mit den `CMFCToolBarImages::CopyTemp` Methode.  
  
##  <a name="isrtl"></a>CMFCToolBarImages::IsRTL  
 Gibt an, ob die Unterstützung für rechts-nach-links (RTL) aktiviert ist.  
  
```  
static BOOL IsRTL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn RTL-Unterstützung aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 RTL-Unterstützung wird verwendet, wenn die Anwendung in eine Sprache übertragen werden, die von rechts nach links, z. B. Arabisch, Hebräisch, Persisch oder Urdu gelesen wird.  
  
##  <a name="isuserimageslist"></a>CMFCToolBarImages::IsUserImagesList  
 Gibt an, ob dieser Satz von symbolleistenbildern benutzerdefinierte Bilder enthält.  
  
```  
BOOL IsUserImagesList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `CMFCToolBarImages` Objekt enthält eine benutzerdefinierte Symbolleistenbilder andernfalls `FALSE`.  
  
##  <a name="isvalid"></a>CMFCToolBarImages::IsValid  
 Gibt an, ob dieser Satz von symbolleistenbildern eine gültige Symbolleistenbild enthält.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine `CMFCToolBarImages` -Objekt gültig ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCToolBarImages` -Objekt ist ungültig, wenn sein Handle an eine Bitmap mit Symbolleistenbilder ist `NULL`.  
  
##  <a name="load"></a>CMFCToolBarImages::Load  
 Lädt Symbolleistenbilder aus, von Systemressourcen oder aus einer Datei.  
  
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
 `TRUE`die vorhandenen Bitmap, die geladenen Bitmap hinzu oder `FALSE` vorhandene Bitmap ersetzen.  
  
 [in] `lpszBmpFileName`  
 Ein Pfad zu einer Datenträgerdatei aus der Bitmap geladen werden soll.  
  
 [in] `nMaxFileSize`  
 Maximale Anzahl von Bytes in der Bitmapdatei; oder bei 0 für die Bitmap unabhängig von der Dateigröße zu laden. Wenn die Größe der Datei diese maximale Größe überschreitet, gibt die Methode `FALSE` und die Bitmap wird nicht geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Bitmap erfolgreich geladen wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Datei, die nur-Lese Attribut hat, wird die Bildliste als schreibgeschützt markiert.  
  
##  <a name="loadstr"></a>CMFCToolBarImages::LoadStr  

  
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

  
```  
static COLORREF __stdcall MapToSysColorAlpha(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="mirror"></a>CMFCToolBarImages::Mirror  
 Ersetzt die Symbolleistenbilder mit ihren horizontale Spiegelbild an.  
  
```  
BOOL Mirror();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Images erfolgreich gespiegelte wurden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird verwendet, um Schriftsystem von rechts nach Links zu unterstützen.  
  
##  <a name="mirrorbitmap"></a>CMFCToolBarImages::MirrorBitmap  
 Ersetzt eine Bitmap mit horizontalen Spiegelbild an.  
  
```  
static BOOL MirrorBitmap(
    HBITMAP& hbmp,  
    int cxImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `hbmp`  
 Ein Handle für die Bitmap zu spiegeln.  
  
 [in] `cxImage`  
 Die Breite des Bilds in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Bild erfolgreich gespiegelt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient zur Unterstützung von Schriftsystem von rechts nach links.  
  
##  <a name="mirrorbitmapvert"></a>CMFCToolBarImages::MirrorBitmapVert  

  
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

  
```  
BOOL MirrorVert();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsyscolorchange"></a>CMFCToolBarImages::OnSysColorChange  

  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="premultiplyalpha"></a>CMFCToolBarImages::PreMultiplyAlpha  

  
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
 `TRUE`Wenn angegeben, Alphablending (32-Bit-Farbe) deaktiviert ist.  
  
```  
static BOOL m_bDisableTrueColorAlpha;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie auf diese Membervariable `FALSE` angegeben, die für Symbolleistenbilder Alphablending zu aktivieren.  
  
 Der Standardwert ist `TRUE` für die Abwärtskompatibilität.  
  
##  <a name="preparedrawimage"></a>CMFCToolBarImages::PrepareDrawImage  
 Ordnet die Ressourcen, die erforderlich sind, um ein Symbolleistenbild bei einer angegebenen Größe zu zeichnen.  
  
```  
BOOL PrepareDrawImage(
    CAfxDrawState& ds,  
    CSize sizeImageDest=CSize(0,
    0)  
    BOOL bFadeInactive=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ds`  
 Ein Verweis auf `CAfxDrawState` -Struktur, die zugeordneten Ressourcen, die zwischen Phasen der Image-Rendering speichert.  
  
 [in] `sizeImageDest`  
 Gibt die Größe eines Bilds Ziel.  
  
 [in] `bFadeInactive`  
 `TRUE`gegebenenfalls inaktiv insgesamt Bilder gezeichnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn zum Zeichnen der Symbolleistenbild erforderlichen Ressourcen nicht erfolgreich, andernfalls belegt wurden `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem Sie diese Methode aufrufen, können Sie aufrufen [CMFCToolBarImages::Draw](#draw) oft. Nachdem die Zeichnung abgeschlossen ist, rufen Sie [CMFCToolBarImages::EndDrawImage](#enddrawimage) freigeben die Ressourcen, die vom zugeordneten `PrepareDrawImage`.  
  
##  <a name="save"></a>CMFCToolBarImages::Save  
 Speichert die Symbolleistenbilder in einer Datei an, wenn dieser Satz von symbolleistenbildern benutzerdefinierte Bilder enthält.  
  
```  
BOOL Save(LPCTSTR lpszBmpFileName=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszBmpFileName`  
 Ein Pfad zu einer Datenträgerdatei.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie die Symbolleistenbilder erfolgreich gespeichert wurden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die benutzerdefinierte Images in eine Datei zu speichern. Wenn `lpszBmpFileName` ist `NULL`, speichert die-Methode die Bitmap in die Datei aus dem die Bitmap, durch geladen wurde die [CMFCToolBarImages::Load](#load) Methode.  
  
##  <a name="setalwayslight"></a>CMFCToolBarImages::SetAlwaysLight  

  
```  
void SetAlwaysLight(BOOL bAlwaysLight = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAlwaysLight`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdisabledimagealpha"></a>CMFCToolBarImages::SetDisabledImageAlpha  
 Legt den alpha-Kanal (Deckkraft)-Wert, der für deaktivierte Images verwendet wird.  
  
```  
static void SetDisabledImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nValue`  
 Der neue Wert, der den alpha-Kanal.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine benutzerdefinierte Alphawert für deaktivierte Bilder festzulegen. Der Standardwert ist 127, wodurch deaktivierte Schaltflächenbilder halb transparent sein. Wenn Sie den Wert 0 festlegen, werden deaktiviert Bilder vollständig transparent sein. Wenn Sie einen Wert von 255 festlegen, werden deaktiviert Bilder vollständig deckend sein.  
  
##  <a name="setfadedimagealpha"></a>CMFCToolBarImages::SetFadedImageAlpha  

  
```  
static void __stdcall SetFadedImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nValue`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setimagesize"></a>CMFCToolBarImages::SetImageSize  
 Legt die Größe der einzelnen Symbolleistenbild (Größe der Datenquelle).  
  
```  
void SetImageSize(
    SIZE sizeImage,  
    BOOL bUpdateCount=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `sizeImage`  
 Die neue Größe von symbolleistenbildern.  
  
### <a name="remarks"></a>Hinweise  
 Ist Sie standardmäßig die Größe des Bilds Symbolleiste 16 x 15 Pixel. Rufen Sie diese Methode, wenn Sie mit einer anderen Größe Symbolleistenbilder verwenden möchten.  
  
##  <a name="setlightpercentage"></a>CMFCToolBarImages::SetLightPercentage  

  
```  
void SetLightPercentage(int nValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nValue`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setmapto3dcolors"></a>CMFCToolBarImages::SetMapTo3DColors  

  
```  
void SetMapTo3DColors(BOOL bMapTo3DColors);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMapTo3DColors`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpremultiplyautocheck"></a>CMFCToolBarImages::SetPreMultiplyAutoCheck  

  
```  
void SetPreMultiplyAutoCheck(BOOL bAuto = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAuto`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setsingleimage"></a>CMFCToolBarImages::SetSingleImage  

  
```  
void SetSingleImage();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settransparentcolor"></a>CMFCToolBarImages::SetTransparentColor  
 Legt die transparente Farbe des die Symbolleistenbilder fest.  
  
```  
COLORREF SetTransparentColor(COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrTransparent`  
 RGB-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen transparente Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie oder das Framework Aufrufen [CMFCToolBarImages::Draw](#draw), zeichnet die Methode alle Pixel, die die Farbe gemäß entspricht keine `clrTransparent`.  
  
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
 Ein Handle für die Bitmap aus der das Bild aktualisieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Abbild wurde erfolgreich aktualisiert wurde; `FALSE` Wenn die Bildliste nicht benutzerdefiniert oder temporär ist.  
  
##  <a name="convertto32bits"></a>CMFCToolBarImages::ConvertTo32Bits  
 Konvertiert unterstrichen Bitmaps auf 32 Bpp Bilder.  
  
```  
BOOL ConvertTo32Bits(COLORREF clrTransparent = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 `clrTransparent`  
 Gibt die transparente Farbe des unterstrichenen Bitmaps.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getbitsperpixel"></a>CMFCToolBarImages::GetBitsPerPixel  
 Aktuelle Auflösung der unterstrichenen Images zurückgegeben.  
  
```  
int GetBitsPerPixel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ganzzahlwert, die aktuelle Auflösung des unterstrichenen Bilder in Bits pro Pixel (Bpp) darstellt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getscale"></a>CMFCToolBarImages::GetScale  
 Gibt die aktuelle Skalierung unterstrichenen Bilder zurück.  
  
```  
double GetScale() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der die aktuelle Skalierung darstellt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isscaled"></a>CMFCToolBarImages::IsScaled  
 Erfahren Sie, ob die unterstrichenen Bilder oder nicht skaliert werden.  
  
```  
BOOL IsScaled () const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die unterstrichenen Bilder skaliert werden. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="smoothresize"></a>CMFCToolBarImages::SmoothResize  
 Ändert die unterstrichenen Bilder reibungslos Größe.  
  
```  
BOOL SmoothResize(double dblImageScale);
```  
  
### <a name="parameters"></a>Parameter  
 `dblImageScale`  
 Skalierung.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Resize erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)
