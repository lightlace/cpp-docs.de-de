---
title: Bitmapfunktionen zu ausgrauen und Dithern | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de887cdbe80642925bc935eb48726a59850f6f96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375173"
---
# <a name="gray-and-dithered-bitmap-functions"></a>Bitmap-Funktionen zu Ausgrauen und Dithering
**Ausgegraute Bitmap-Funktionen**  
  
 MFC enthält zwei Funktionen, die verwendet werden können, um einer Bitmap das Aussehen eines deaktivierten Steuerelements zu verleihen.  
  
 ![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Zeichnet eine graue Version einer Bitmap.|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Kopiert eine graue Version einer Bitmap.|  
  
 **Bitmap-Funktionen mit Dithering**  
  
 MFC enthält außerdem zwei Funktionen, mit denen der Hintergrund einer Bitmap durch ein gedithertes Muster ersetzt werden kann.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
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
 `pDC`  
 Zeigt auf den Ziel-DC.  
  
 *w*  
 Die X-Koordinate des Ziels.  
  
 *y*  
 Die Y-Koordinate des Ziels.  
  
 `rSrc`  
 Die Quellbitmap.  
  
 `crBackground`  
 Die neue Hintergrundfarbe (normalerweise grau, wie etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Eine mit `AfxDrawGrayBitmap` gezeichnete Bitmap hat das Aussehen eines deaktivierten Steuerelements.  
  
 ![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vcgraybitmap")  
  
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
 `rSrc`  
 Die Quellbitmap.  
  
 `pDest`  
 Die Zielbitmap.  
  
 `crBackground`  
 Die neue Hintergrundfarbe (normalerweise grau, wie etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Eine mit `AfxGetGrayBitmap` kopierte Bitmap hat das Aussehen eines deaktivierten Steuerelements.  
  
 ![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vcgraybitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap  
 Zeichnet eine Bitmap, ersetzen den Hintergrund mit einem Muster Dithern (aus).  
  
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
 `pDC`  
 Zeigt auf den Ziel-DC.  
  
 *w*  
 Die X-Koordinate des Ziels.  
  
 *y*  
 Die Y-Koordinate des Ziels.  
  
 `rSrc`  
 Die Quellbitmap.  
  
 `cr1`  
 Einer der beiden Dithering Farben ab, in der Regel weiß.  
  
 `cr2`  
 Die anderen Dithering Farbe, in der Regel hellgrau (etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Die Quellbitmap auf den Zieldomänencontroller mit zwei Farben gezeichnet wird ( `cr1` und `cr2`) Karomuster der Bitmap-Hintergrund ersetzt. Der Hintergrund des Quellbitmaps ist als seine weißen Pixel und alle Pixel, die die Farbe des Pixels in der linken oberen Ecke der Bitmap für die Übereinstimmung definiert.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  


##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap  
 Kopiert eine Bitmap, ersetzen den Hintergrund mit einem Muster Dithern (aus).  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Die Quellbitmap.  
  
 `pDest`  
 Die Zielbitmap.  
  
 `cr1`  
 Einer der beiden Dithering Farben ab, in der Regel weiß.  
  
 `cr2`  
 Die anderen Dithering Farbe, in der Regel hellgrau (etwa COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Die Quellbitmap in das Zielbitmap mit zwei Farben kopiert ( `cr1` und `cr2`) Karomuster die Quellbitmap im Hintergrund ersetzt. Der Hintergrund des Quellbitmaps ist als seine weißen Pixel und alle Pixel, die die Farbe des Pixels in der linken oberen Ecke der Bitmap für die Übereinstimmung definiert.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
