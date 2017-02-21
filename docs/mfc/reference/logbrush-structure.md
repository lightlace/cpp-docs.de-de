---
title: "LOGBRUSH-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LOGBRUSH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOGBRUSH-Struktur"
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# LOGBRUSH-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `LOGBRUSH`\-Struktur definiert den Stil, die Farbe und das Muster eines physischen Pinsels.  Es wird von Windows unter [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) und [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)\-Funktionen verwendet.  
  
## Syntax  
  
```  
  
      typedef struct tag LOGBRUSH { /* lb */  
   UINT lbStyle;  
   COLORREF lbColor;  
   LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### Parameter  
 `lbStyle`  
 Gibt den Pinselformat an.  Der `lbStyle`\-Member muss eines der folgenden Formate aufweisen:  
  
-   Musterpinsel **BS\_DIBPATTERN** Eine definiert durch \(DIB\)\- eine Spezifikation für geräteunabhängige Bitmaps.  Wenn `lbStyle`**BS\_DIBPATTERN** ist, enthält der **lbHatch**\-Member ein Handle zu einem gepackten DIB\-Datei.  
  
-   Musterpinsel **BS\_DIBPATTERNPT** Eine definiert durch \(DIB\)\- eine Spezifikation für geräteunabhängige Bitmaps.  Wenn `lbStyle`**BS\_DIBPATTERNPT** ist, enthält der **lbHatch**\-Member einen Zeiger auf ein gepackten DIB\-Datei.  
  
-   **BS\_HATCHED** schraffierte Pinsel.  
  
-   **BS\_HOLLOW** Höhlenpinsel.  
  
-   **BS\_NULL** entspricht der **BS\_HOLLOW**.  
  
-   **BS\_PATTERN** Musterpinsel definiert durch eine Speicherbitmap.  
  
-   **BS\_SOLID** Volltonpinsels.  
  
 `lbColor`  
 Gibt die Farbe an, in der der Pinsel gezeichnet werden soll.  Wenn `lbStyle` das **BS\_HOLLOW** oder **BS\_PATTERN** Format ist, wird **lbColor** ignoriert.  Wenn `lbStyle`**BS\_DIBPATTERN** oder **BS\_DIBPATTERNBT** aufweist, gibt das Wort niederwertige von **lbColor** an, ob die **bmiColors**\-Member der [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md)\-Struktur explizite roten, grünen, blauen \(RGB\)\- Werte oder die Indizes in die nur realisierte Logische Palette enthalten.  Der **lbColor**\-Member muss einer der folgenden Werte sein:  
  
-   **DIB\_PAL\_COLORS** die Farbtabelle besteht aus einem Array aus 16\-Bit\-Indizes in die nur realisierte Logische Palette.  
  
-   **DIB\_RGB\_COLORS** die Farbtabelle enthält Literale RGB\-Werte.  
  
 *lbHatch*  
 Gibt einen Schraffurstil an.  Die Bedeutung hängt vom Pinselformat ab, die von `lbStyle` definiert ist.  Wenn `lbStyle`**BS\_DIBPATTERN** ist, enthält der **lbHatch**\-Member ein Handle zu einem gepackten DIB\-Datei.  Wenn `lbStyle`**BS\_DIBPATTERNPT** ist, enthält der **lbHatch**\-Member einen Zeiger auf ein gepackten DIB\-Datei.  Wenn `lbStyle`**BS\_HATCHED** ist, gibt der Member der **lbHatch** Ausrichtung der Zeilen an, die verwendet werden, um der Schraffur zu erstellen.  Es kann einen der folgenden Werte sein:  
  
-   45\-Grad\-`HS_BDIAGONAL` Eine nach oben, Schraffur von links nach rechts  
  
-   horizontale und vertikale Kreuzschraffur `HS_CROSS`  
  
-   `HS_DIAGCROSS` 45\-Grad\-Kreuzschraffur  
  
-   45\-Grad\-`HS_FDIAGONAL` Eine nach unten, Schraffur von links nach rechts  
  
-   horizontale Schraffur `HS_HORIZONTAL`  
  
-   vertikale Schraffur `HS_VERTICAL`  
  
 Wenn `lbStyle` ist **BS\_PATTERN**, **lbHatch** ist ein Handle der Bitmap, die das Muster definiert.  Wenn `lbStyle`**BS\_SOLID** oder **BS\_HOLLOW**, wird **lbHatch** ignoriert.  
  
## Hinweise  
 Obwohl **lbColor** die Vordergrundfarbe eines Schraffurpinsels steuert, steuern die [CDC::SetBkMode](../Topic/CDC::SetBkMode.md) und [CDC::SetBkColor](../Topic/CDC::SetBkColor.md)\-Funktionen die Hintergrundfarbe.  
  
## Anforderungen  
 **Header:** wingdi.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)