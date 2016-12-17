---
title: "COLORADJUSTMENT-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "COLORADJUSTMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLORADJUSTMENT-Struktur"
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# COLORADJUSTMENT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `COLORADJUSTMENT` definiert die Farbenanpassungswerte Struktur, die die Funktionen von Windows `StretchBlt` und **StretchDIBits** verwendet werden, wenn der `StretchBlt` \- Modus **HALFTONE** ist.  
  
## Syntax  
  
```  
  
      typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD  caSize;  
    WORD  caFlags;  
    WORD  caIlluminantIndex;  
    WORD  caRedGamma;  
    WORD  caGreenGamma;  
    WORD  caBlueGamma;  
    WORD  caReferenceBlack;  
    WORD  caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### Parameter  
 *caSize*  
 Gibt die Größe der Struktur in Bytes an.  
  
 *caFlags*  
 Gibt an, wie das Ausgabebild vorbereitet werden soll.  Dieser Member kann auf **NULL** oder eine beliebige Kombination der folgenden Werte festgelegt werden:  
  
-   **CA\_NEGATIVE** gibt an, dass das negative des Originalbilds angezeigt werden soll.  
  
-   **CA\_LOG\_FILTER** gibt an, dass eine logarithmische Funktion zur endgültigen denen die Ausgabefarben angewendet werden soll.  Dies erhöht den Farbenkontrast, wenn die Leuchtdichte niedrig ist.  
  
 *caIlluminantIndex*  
 Gibt die Leuchtdichte der Lichtquelle an, unter der das Bildobjekt angezeigt wird.  Dieser Member kann auf einen der folgenden Werte festgelegt werden:  
  
-   **ILLUMINANT\_EQUAL\_ENERGY**  
  
-   **ILLUMINANT\_A**  
  
-   **ILLUMINANT\_B**  
  
-   **ILLUMINANT\_C**  
  
-   **ILLUMINANT\_D50**  
  
-   **ILLUMINANT\_D55**  
  
-   **ILLUMINANT\_D65**  
  
-   **ILLUMINANT\_D75**  
  
-   **ILLUMINANT\_F2**  
  
-   **ILLUMINANT\_TURNGSTEN**  
  
-   **ILLUMINANT\_DAYLIGHT**  
  
-   **ILLUMINANT\_FLUORESCENT**  
  
-   **ILLUMINANT\_NTSC**  
  
 *caRedGamma*  
 Gibt den Energiengammakorrekturwert zum N\-ten Rot angezeigt, das von den Quellfarben primär ist.  Der Wert muss im Bereich von 2.500 bis 65.000 liegen.  Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caGreenGamma*  
 Gibt den Energiengammakorrekturwert zum N\-ten grün dargestellt, das von den Quellfarben primär ist.  Der Wert muss im Bereich von 2.500 bis 65.000 liegen.  Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caBlueGamma*  
 Gibt den Energiengammakorrekturwert zum N\-ten Blau angezeigt, das von den Quellfarben primär ist.  Der Wert muss im Bereich von 2.500 bis 65.000 liegen.  Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caReferenceBlack*  
 Gibt dem schwarzen Verweis für die Quellfarben an.  Alle Farben, die dunkler sind, als dieses werden als schwarz behandelt.  Der Wert muss im Bereich von 0 bis 4.000 liegen.  
  
 *caReferenceWhite*  
 Gibt dem weißen Verweis für die Quellfarben an.  Alle Farben, die heller sind, als dieses werden als weiß behandelt.  Der Wert muss im Bereich von 6.000 bis 10.000 liegen.  
  
 *caContrast*  
 Gibt die Menge an die angewendet werden Kontrastes.  Der Wert muss im Bereich von \-100 bis 100 liegen.  Ein Wert von 0 bedeutet keine Kontrastregulierung.  
  
 *caBrightness*  
 Gibt die Menge der an die angewendet werden, Helligkeit.  Der Wert muss im Bereich von \-100 bis 100 liegen.  Ein Wert von 0 bedeutet keine Helligkeitsanpassung.  
  
 *caColorfulness*  
 Gibt die Menge an die angewendet werden, colorfulness.  Der Wert muss im Bereich von \-100 bis 100 liegen.  Ein Wert von 0 bedeutet keine colorfulness Anpassung.  
  
 *caRedGreenTint*  
 Gibt die Menge der dem Quellobjekt angewendet werden Rot\- an oder Grünfarbtonanpassung.  Der Wert muss im Bereich von \-100 bis 100 liegen.  Positive Zahlen werden in Bezug zu Rot anpassen und negative Zahlen anpassen in Richtung in Grün.  0 Bedeutet keine Farbtonanpassung.  
  
## Anforderungen  
 **Header:** wingdi.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../Topic/CDC::GetColorAdjustment.md)