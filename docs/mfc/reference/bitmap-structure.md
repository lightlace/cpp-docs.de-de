---
title: "BITMAP-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAP-Struktur"
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# BITMAP-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **BITMAP**\-Struktur definiert die Höhe, die Breite, das Farbenformat und die Bitwerte einer logischen Bitmap**.**  
  
## Syntax  
  
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
  
#### Parameter  
 *bmType*  
 Gibt den Bitmaptyp an.  Für logische Bitmaps muss dieser Member 0 sein.  
  
 *bmWidth*  
 Gibt die Breite der Bitmap in Pixeln an.  Die Breite muss größer als 0 sein.  
  
 *bmHeight*  
 Gibt die Höhe der Bitmap in Rasterzeilen an.  Die Höhe muss größer als 0 sein.  
  
 *bmWidthBytes*  
 Gibt die Anzahl von Bytes in jeder Rasterzeile an.  Dieser Wert muss eine gerade Zahl sein, da die Graphics Device Interface \(GDI\) davon ausgeht, dass die Bitwerte einer Bitmap ein Array von ganzzahligen \(2\-Byte\-\)Werten bilden.  Das heißt, **bmWidthBytes** \* 8 muss das nächste Vielfache von 16 größer oder gleich dem Wert sein, den man erhält, wenn der **bmWidth**\-Member mit dem **bmBitsPixel**\-Member multipliziert wird.  
  
 *bmPlanes*  
 Gibt die Anzahl von Farbebenen in der Bitmap an.  
  
 *bmBitsPixel*  
 Gibt die Anzahl der benachbarten Farbbits auf jeder Ebene an, die zur Definition eines Pixels erforderlich sind.  
  
 *bmBits*  
 Zeigt auf den Speicherort der Bitwerte für die Bitmap.  Der **bmBits**\-Member muss ein long\-Zeiger auf ein Array von 1\-Byte\-Werten sein.  
  
## Hinweise  
 Die aktuell verwendeten Bitmapformate sind monochrom und Farbe.  Die monochrome Bitmap verwendet ein 1\-Bit\-\/1\-Plane\-Format.  Jeder Scan ist ein Vielfaches von 16 Bits.  
  
 Scans werden für eine monochrome Bitmap der Höhe *n* wie folgt organisiert:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Die Pixel auf einem monochromen Gerät sind entweder schwarz oder weiß.  Wenn das entsprechende Bit in der Bitmap 1 ist, wird das Pixel aktiviert \(weiß\).  Wenn das entsprechende Bit in der Bitmap 0 ist, wird das Pixel deaktiviert \(schwarz\).  
  
 Alle Geräte unterstützen Bitmaps, für die das **RC\_BITBLT**\-Bit im **RASTERCAPS**\-Index der [CDC::GetDeviceCaps](../Topic/CDC::GetDeviceCaps.md)\-Memberfunktion festgelegt ist.  
  
 Jedes Gerät hat ein eigenes eindeutiges Farbformat.  Um eine Bitmap von einem Gerät zu einem anderen zu übertragen, verwenden Sie die Windows\-Funktionen [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) und [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973).  
  
## Anforderungen  
 **Header:** wingdi.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)