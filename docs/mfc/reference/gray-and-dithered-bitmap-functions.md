---
title: Grau dargestellte und gerasterte Bitmapfunktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: b8b6f43917dfe211f477b3dde0c94323015d18b2
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="gray-and-dithered-bitmap-functions"></a>Bitmap-Funktionen zu Ausgrauen und Dithern
**Graue Bitmap-Funktionen**  
  
 MFC enthält zwei Funktionen, die verwendet werden können, um einer Bitmap das Aussehen eines deaktivierten Steuerelements zu verleihen.  
  
 ![Vergleich von grauen und ursprünglichen Symbolversionen](../../mfc/reference/media/vcgraybitmap.gif "Vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Zeichnet eine graue Version einer Bitmap.|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Kopiert eine graue Version einer Bitmap.|  
  
 **Dithering Bitmap-Funktionen**  
  
 MFC enthält außerdem zwei Funktionen, mit denen der Hintergrund einer Bitmap durch ein gedithertes Muster ersetzt werden kann.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Zeichnet eine Bitmap mit gedithertem Hintergrund.|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Kopiert eine Bitmap mit gedithertem Hintergrund.|  
  
##  <a name="afxdrawgraybitmap"></a>AfxDrawGrayBitmap  
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
  
 *x*  
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
 [!code-cpp[NVC_MFCDocView&#191;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  

##  <a name="afxgetgraybitmap"></a>AfxGetGrayBitmap  
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
 [!code-cpp[NVC_MFCDocView&#193;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="afxdrawditheredbitmap"></a>AfxDrawDitheredBitmap  
 Zeichnet eine Bitmap, ersetzen den Hintergrund mit einem Muster Dithering (Prüfung).  
  
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
  
 *x*  
 Die X-Koordinate des Ziels.  
  
 *y*  
 Die Y-Koordinate des Ziels.  
  
 `rSrc`  
 Die Quellbitmap.  
  
 `cr1`  
 Eine der beiden Dithering-Farben in der Regel weiß.  
  
 `cr2`  
 Die anderen Dithering Farbe, in der Regel hellgrau (COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Die Quell-Bitmap gezeichnet wird, auf dem Zieldomänencontroller mit zwei Farben ( `cr1` und `cr2`) Karomuster der Bitmap-Hintergrund ersetzt. Der Hintergrund der Quellbitmap wird als seine Pixel weiß und alle Pixel, die die Farbe des Pixels in der linken oberen Ecke der Bitmap für die Übereinstimmung definiert.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#190;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  


##  <a name="afxgetditheredbitmap"></a>AfxGetDitheredBitmap  
 Kopiert eine Bitmap, ersetzen den Hintergrund mit einem Muster Dithering (Prüfung).  
  
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
 Eine der beiden Dithering-Farben in der Regel weiß.  
  
 `cr2`  
 Die anderen Dithering Farbe, in der Regel hellgrau (COLOR_MENU).  
  
### <a name="remarks"></a>Hinweise  
 Kopiert die Quellbitmap in die Zielbitmap mit zwei Farben ( `cr1` und `cr2`) Karomuster die Quell-Bitmap-Hintergrund ersetzt. Der Hintergrund der Quellbitmap wird als seine Pixel weiß und alle Pixel, die die Farbe des Pixels in der linken oberen Ecke der Bitmap für die Übereinstimmung definiert.  
  
 ![Vergleich von geditherten und ursprünglichen Symbolversionen](../../mfc/reference/media/vcditheredbitmap.gif "Vcditheredbitmap")  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#192;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

