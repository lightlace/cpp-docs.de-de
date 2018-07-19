---
title: COLORADJUSTMENT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure [MFC]
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03c5346a59ea52ca6b2428652d5da69aacf6ea5b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849089"
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT-Struktur
Die `COLORADJUSTMENT` Struktur definiert die Anpassung-Farbwerte, die verwendet werden, indem Sie die Windows `StretchBlt` und `StretchDIBits` Funktionen bei der `StretchBlt` HALBTON ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD caSize;  
    WORD caFlags;  
    WORD caIlluminantIndex;  
    WORD caRedGamma;  
    WORD caGreenGamma;  
    WORD caBlueGamma;  
    WORD caReferenceBlack;  
    WORD caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *caSize*  
 Gibt die Größe der Struktur in Bytes an.  
  
 *caFlags*  
 Gibt an, wie die Abbildung zur Ausgabe vorbereitet werden soll. Dieses Element kann auf NULL oder eine beliebige Kombination der folgenden Werte festgelegt werden:  
  
- CA_NEGATIVE gibt an, dass es sich bei der negativen Wert des ursprünglichen Bilds angezeigt werden soll.  
  
- CA_LOG_FILTER gibt an, dass eine logarithmische-Funktion auf die endgültige Dichte der Ausgabefarben angewendet werden soll. Dies erhöht den Farbkontrast, wenn der leuchtdichtenebene, Gleiches gering ist.  
  
 *caIlluminantIndex*  
 Gibt an, der Intensität der Lichtquelle unter der das Image-Objekt angezeigt wird. Dieses Element kann auf einen der folgenden Werte festgelegt werden:  
  
- ILLUMINANT_EQUAL_ENERGY  
  
- ILLUMINANT_A  
  
- ILLUMINANT_B  
  
- ILLUMINANT_C  
  
- ILLUMINANT_D50  
  
- ILLUMINANT_D55  
  
- ILLUMINANT_D65  
  
- ILLUMINANT_D75  
  
- ILLUMINANT_F2  
  
- ILLUMINANT_TURNGSTEN  
  
- ILLUMINANT_DAYLIGHT  
  
- ILLUMINANT_FLUORESCENT  
  
- ILLUMINANT_NTSC  
  
 *caRedGamma*  
 Gibt den n-ten Power Gammakorrektur Wert für das rote primäre Replikat, der die Farben einer Quelle. Der Wert muss im Bereich von 2.500 65.000 sein. Der Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caGreenGamma*  
 Gibt den n-ten Power Gammakorrektur Wert für das grüne primäre Replikat, der die Farben einer Quelle. Der Wert muss im Bereich von 2.500 65.000 sein. Der Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caBlueGamma*  
 Gibt den n-ten Power Gammakorrektur Wert für die Grundfarbe Blau, der die Farben einer Quelle. Der Wert muss im Bereich von 2.500 65.000 sein. Der Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caReferenceBlack*  
 Gibt die schwarzen Referenz für die Farben einer Quelle an. Alle Farben, die als dieser dunkler sind, werden als schwarze behandelt. Der Wert muss im Bereich von 0 bis 4.000 sein.  
  
 *caReferenceWhite*  
 Gibt die weißen Referenz für die Farben einer Quelle an. Alle Farben, die heller als diese werden als Whitepaper behandelt. Der Wert muss im Bereich von 6.000 bis 10.000 sein.  
  
 *caContrast*  
 Gibt die Kontrastbetrag auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Der Wert 0 bedeutet keine Anpassung Kontrast.  
  
 *caBrightness*  
 Gibt den Umfang der Helligkeit auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Der Wert 0 bedeutet keine Anpassung der Helligkeit an.  
  
 *caColorfulness*  
 Gibt den Umfang der Colorfulness auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Der Wert 0 bedeutet keine Colorfulness Anpassung.  
  
 *caRedGreenTint*  
 Gibt den Grad der Anpassung von Rot oder Grün Farbton auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Positive Zahlen auf Rot passen würde aus, und passen Sie negative Zahlen auf Grün. 0 bedeutet keine Anpassung Farbton.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


