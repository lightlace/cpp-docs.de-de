---
title: COLORADJUSTMENT-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
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
ms.openlocfilehash: 7f88877fa009abf4e811ba0a99b7e0e1683f998a
ms.lasthandoff: 02/24/2017

---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT-Struktur
Die `COLORADJUSTMENT` Struktur definiert die Farbwerte für die Anpassung von Windows verwendet `StretchBlt` und **StretchDIBits** Funktionen bei der `StretchBlt` Modus ist **HALBTON**.  
  
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
 Gibt die Größe der Struktur in Bytes.  
  
 *caFlags*  
 Gibt an, wie das Ausgabe-Abbild vorbereitet werden soll. Dieses Element festgelegt werden kann, um **NULL** oder eine beliebige Kombination der folgenden Werte:  
  
- **CA_NEGATIVE** gibt an, dass der negativen Wert des ursprünglichen Bilds angezeigt werden soll.  
  
- **CA_LOG_FILTER** gibt an, dass eine logarithmische Funktion auf die endgültige Dichte der Ausgabefarben angewendet werden soll. Dies erhöht den Farbkontrast, wenn die Intensität gering ist.  
  
 *caIlluminantIndex*  
 Gibt die Intensität der Lichtquelle, unter der das Image-Objekt angezeigt wird. Dieser Member kann auf einen der folgenden Werte festgelegt werden:  
  
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
 Gibt den n-ten Power Gammakorrektur Wert für die Rot primären Datenquelle Farben. Der Wert muss im Bereich von 2.500 65.000 sein. Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caGreenGamma*  
 Gibt den n-ten Power Gammakorrektur Wert für die grünen primären Datenquelle Farben. Der Wert muss im Bereich von 2.500 65.000 sein. Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caBlueGamma*  
 Gibt die n-te Power Gammakorrektur Wert der Quellfarben Grundfarbe Blau. Der Wert muss im Bereich von 2.500 65.000 sein. Ein Wert von 10.000 bedeutet keine Gammakorrektur.  
  
 *caReferenceBlack*  
 Gibt den schwarzen Verweis für die Quellfarben. Die als dunklere Farben werden als schwarze behandelt. Der Wert muss im Bereich von 0 bis 4.000 sein.  
  
 *caReferenceWhite*  
 Gibt den weißen Verweis für die Quellfarben. Farben, die heller als Weiß behandelt. Der Wert muss im Bereich von 6.000 bis 10.000 sein.  
  
 *caContrast*  
 Gibt den Kontrast auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Der Wert 0 bedeutet keine Anpassung Kontrast.  
  
 *caBrightness*  
 Gibt die Helligkeit auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Der Wert 0 bedeutet keine Anpassung der Helligkeit.  
  
 *caColorfulness*  
 Gibt die Menge des Colorfulness auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Der Wert 0 bedeutet keine Colorfulness Anpassung.  
  
 *caRedGreenTint*  
 Gibt den Grad der Anpassung von Rot oder Grün Farbton auf das Quellobjekt angewendet werden. Der Wert muss im Bereich zwischen-100 und 100 sein. Positive Zahlen für Rot passen würde, und passen Sie negative Zahlen für Grün. 0 bedeutet keine Anpassung Farbton.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)



