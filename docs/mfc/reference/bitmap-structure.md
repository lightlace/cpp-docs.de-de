---
title: Bitmapstruktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BITMAP
dev_langs:
- C++
helpviewer_keywords:
- BITMAP structure [MFC]
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa8bb4ab914b4e05eb21cfc45a243328d32bb6d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351636"
---
# <a name="bitmap-structure"></a>BITMAP-Struktur
Die **BITMAP** Struktur definiert die Höhe, Breite, farbenformat und die Bitwerte einer logischen Bitmap **.**  
  
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
 Gibt die Anzahl von Bytes in jeder Rasterzeile an. Dieser Wert muss eine gerade Zahl sein, da die Graphics Device Interface (GDI) davon ausgeht, dass die Bitwerte einer Bitmap ein Array von ganzzahligen (2-Byte-)Werten bilden. Das heißt, **BmWidthBytes** \* 8 muss das nächste Vielfache von 16 größer oder gleich dem Wert, wenn die **BmWidth** Member multipliziert wird die **BmBitsPixel**  Member.  
  
 *bmPlanes*  
 Gibt die Anzahl von Farbebenen in der Bitmap an.  
  
 *bmBitsPixel*  
 Gibt die Anzahl der benachbarten Farbbits auf jeder Ebene an, die zur Definition eines Pixels erforderlich sind.  
  
 *bmBits*  
 Zeigt auf den Speicherort der Bitwerte für die Bitmap. Die **BmBits** angehören muss ein long-Zeiger auf ein Array von 1-Byte-Werten.  
  
## <a name="remarks"></a>Hinweise  
 Die aktuell verwendeten Bitmapformate sind monochrom und Farbe. Die monochrome Bitmap verwendet ein 1-Bit-/1-Plane-Format. Jeder Scan ist ein Vielfaches von 16 Bits.  
  
 Scans werden für eine monochrome Bitmap der Höhe wie folgt aufgebaut *n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Die Pixel auf einem monochromen Gerät sind entweder schwarz oder weiß. Wenn das entsprechende Bit in der Bitmap 1 ist, wird das Pixel aktiviert (weiß). Wenn das entsprechende Bit in der Bitmap 0 ist, wird das Pixel deaktiviert (schwarz).  
  
 Alle Geräte unterstützen Bitmaps, die **RC_BITBLT** -Bit im die **RASTERCAPS** Index, der die [GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) Memberfunktion.  
  
 Jedes Gerät hat ein eigenes eindeutiges Farbformat. Um eine Bitmap von einem Gerät in einen anderen zu übertragen, verwenden Sie die [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) und [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) Windows-Funktionen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap:: Createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)
