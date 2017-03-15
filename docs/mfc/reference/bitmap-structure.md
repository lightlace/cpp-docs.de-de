---
title: Bitmapstruktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BITMAP
dev_langs:
- C++
helpviewer_keywords:
- BITMAP structure
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: 12
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd7e63cfe9e7a0f2305ca5c3cd7c2571a080a718
ms.lasthandoff: 02/24/2017

---
# <a name="bitmap-structure"></a>BITMAP-Struktur
Die **BITMAP** Struktur definiert die Höhe, Breite, Farbformat und die Bitwerte einer logischen Bitmap**.**  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagBITMAP {  /* bm */  
    int bmType;  
    int bmWidth;  
    int bmHeight;  
    int bmWidthBytes;  
    BYTE bmPlanes;  
    BYTE bmBitsPixel;  
    LPVOID bmBits;  
} BITMAP;  
```  
  
#### <a name="parameters"></a>Parameter  
 *bmType*  
 Gibt den Bitmaptyp an. Für logische Bitmaps muss dieser Member 0 sein.  
  
 *bmWidth*  
 Gibt die Breite der Bitmap in Pixeln an. Die Breite muss größer als 0 sein.  
  
 *bmHeight*  
 Gibt die Höhe der Bitmap in Rasterzeilen an. Die Höhe muss größer als 0 sein.  
  
 *bmWidthBytes*  
 Gibt die Anzahl von Bytes in jeder Rasterzeile an. Dieser Wert muss eine gerade Zahl sein, da die Graphics Device Interface (GDI) davon ausgeht, dass die Bitwerte einer Bitmap ein Array von ganzzahligen (2-Byte-)Werten bilden. Das heißt, **BmWidthBytes** \* 8 muss das nächste Vielfache von 16 größer oder gleich dem Wert abgerufen, wenn die **BmWidth** Member multipliziert wird die **BmBitsPixel** Element.  
  
 *bmPlanes*  
 Gibt die Anzahl von Farbebenen in der Bitmap an.  
  
 *bmBitsPixel*  
 Gibt die Anzahl der benachbarten Farbbits auf jeder Ebene an, die zur Definition eines Pixels erforderlich sind.  
  
 *bmBits*  
 Zeigt auf den Speicherort der Bitwerte für die Bitmap. Die **BmBits** Element muss ein long-Zeiger auf ein Array von 1-Byte-Werte sein.  
  
## <a name="remarks"></a>Hinweise  
 Die aktuell verwendeten Bitmapformate sind monochrom und Farbe. Die monochrome Bitmap verwendet ein 1-Bit-/1-Plane-Format. Jeder Scan ist ein Vielfaches von 16 Bits.  
  
 Scans werden für eine monochrome Bitmap der Höhe wie folgt organisiert *n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Die Pixel auf einem monochromen Gerät sind entweder schwarz oder weiß. Wenn das entsprechende Bit in der Bitmap 1 ist, wird das Pixel aktiviert (weiß). Wenn das entsprechende Bit in der Bitmap 0 ist, wird das Pixel deaktiviert (schwarz).  
  
 Alle Geräte unterstützen Bitmaps, die **RC_BITBLT** Bit festgelegt, der **RASTERCAPS** Index des der [GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) Member-Funktion.  
  
 Jedes Gerät hat ein eigenes eindeutiges Farbformat. Um eine Bitmap von einem Gerät in einen anderen zu übertragen, verwenden die [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) und [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) Windows-Funktionen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)

