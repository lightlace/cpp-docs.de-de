---
title: COLORADJUSTMENT-Struktur | Microsoft Docs
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
ms.openlocfilehash: 1bb4cba5ef2eafa27a26c945f8754eb1a0ab0315
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37077954"
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT-Struktur
Die `COLORADJUSTMENT` Struktur definiert die Anpassung-Farbwerte, die von Windows verwendete `StretchBlt` und `StretchDIBits` Funktionen bei der `StretchBlt` Modus ist **RASTERBILD**.  
  
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
 Gibt an, wie die Ausgabebilds vorbereitet werden soll. Bei diesem Member festgelegt werden kann, um **NULL** oder eine beliebige Kombination der folgenden Werte:  
  
- **CA_NEGATIVE** gibt an, dass der negativen Wert, der das ursprüngliche Bild angezeigt werden soll.  
  
- **CA_LOG_FILTER** gibt an, dass eine logarithmische Funktion auf die endgültige Dichte der Ausgabefarben angewendet werden soll. Dadurch wird die Farbenkontrast erhöhen, wenn die Intensität mit niedriger ist.  
  
 *caIlluminantIndex*  
 Gibt die Intensität der Lichtquelle unter der das Image-Objekt angezeigt wird. Dieser Member kann auf einen der folgenden Werte festgelegt werden:  
  
- **ILLUMINANT_EQUAL_ENERGY**  
  
- **ILLUMINANT_A**  
  
- **ILLUMINANT_B**  
  
- **ILLUMINANT_C**  
  
- **ILLUMINANT_D50**  
  
- **ILLUMINANT_D55**  
  
- **ILLUMINANT_D65**  
  
- **ILLUMINANT_D75**  
  
- **ILLUMINANT_F2**  
  
- **ILLUMINANT_TURNGSTEN**  
  
- **ILLUMINANT_DAYLIGHT**  
  
- **ILLUMINANT_FLUORESCENT**  
  
- **ILLUMINANT_NTSC**  
  
 *caRedGamma*  
 Gibt den n-ten Power Gammakorrektur Wert für den roten primären der Quellfarben. Der Wert muss im Bereich von 2.500 65.000 sein. Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caGreenGamma*  
 Gibt den n-ten Power Gammakorrektur Wert für den grünen primären der Quellfarben. Der Wert muss im Bereich von 2.500 65.000 sein. Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caBlueGamma*  
 Gibt den n-ten Power Gammakorrektur Wert für den blauen primären der Quellfarben. Der Wert muss im Bereich von 2.500 65.000 sein. Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caReferenceBlack*  
 Gibt die schwarze Referenz für die Quellfarben an. Alle Farben aus, die als dunklere werden als schwarzer behandelt. Der Wert muss im Bereich von 0 bis 4.000 sein.  
  
 *caReferenceWhite*  
 Gibt den weißen Verweis für die Quellfarben an. Alle Farben, die heller als dieser werden als Leerzeichen behandelt. Der Wert muss im Bereich von 6.000 bis 10.000.  
  
 *caContrast*  
 Gibt den Umfang der Kontrast auf das Quellobjekt, das angewendet werden soll. Der Wert muss im Bereich von -100 bis 100. Der Wert 0 bedeutet keine Anpassung Kontrast.  
  
 *caBrightness*  
 Gibt den Umfang der Helligkeit auf das Quellobjekt, das angewendet werden soll. Der Wert muss im Bereich von -100 bis 100. Der Wert 0 bedeutet keine Helligkeit.  
  
 *caColorfulness*  
 Gibt den Umfang der Colorfulness auf das Quellobjekt, das angewendet werden soll. Der Wert muss im Bereich von -100 bis 100. Der Wert 0 bedeutet keine Colorfulness Anpassung.  
  
 *caRedGreenTint*  
 Gibt den Umfang der roter oder grüner Farbton Anpassung auf das Quellobjekt, das angewendet werden soll. Der Wert muss im Bereich von -100 bis 100. Positive Zahlen auf Rot passen würde, und passen Sie negative Zahlen zu Grün. Eine "0" bedeutet keine Anpassung Farbton.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


