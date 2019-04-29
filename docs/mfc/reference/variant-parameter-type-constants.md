---
title: Variant-Parametertypkonstanten
ms.date: 11/04/2016
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
ms.openlocfilehash: b15a303f69ce13cf3ba3b6c1c0739acdb8a33c7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309475"
---
# <a name="variant-parameter-type-constants"></a>Variant-Parametertypkonstanten

Dieses Thema enthält neue Konstanten, die angeben, variant Parametertypen, die für die Verwendung mit der OLE-Steuerelementklassen von den Microsoft Foundation Class-Bibliothek entwickelt.

Im folgenden finden eine Liste von Konstanten der Klasse:

##  <a name="_mfc_variant_data_constants"></a> Variant-Datenkonstanten

- VTS_COLOR ein 32-Bit-Ganzzahl, der einen RGB-Farbwert darstellt.

- VTS_FONT ein Zeiger auf die `IFontDisp` -Schnittstelle eines Objekts der OLE-Schriftart.

- VTS_HANDLE ein Windows-Handle-Wert.

- VTS_PICTURE ein Zeiger auf die `IPictureDisp` Schnittstelle eines Bild OLE-Objekts.

- VTS_OPTEXCLUSIVE-ein 16-Bit-Wert verwendet, die für ein Steuerelement, das in einer Gruppe von Steuerelementen, wie z. B. Optionsfelder verwendet werden soll. Dieser Typ weist den Container, dass alle anderen verfügt ein Steuerelement in einer Gruppe auf einen Wert "true", "false" sein müssen.

- VTS_TRISTATE ein 16-Bit-Ganzzahl mit Vorzeichen verwendet, die für Eigenschaften, die einen von drei möglichen Werten (ausgewählte, gelöscht, nicht verfügbar), z. B. ein Kontrollkästchen enthalten können.

- VTS_XPOS_HIMETRIC ein 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der x-Achse in HIMETRIC-Einheiten darstellen.

- VTS_YPOS_HIMETRIC ein 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der y-Achse in HIMETRIC-Einheiten darstellen.

- VTS_XPOS_PIXELS ein 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der x-Achse in Pixel darstellen.

- VTS_YPOS_PIXELS ein 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der y-Achse in Pixel darstellen.

- VTS_XSIZE_PIXELS ein 32-Bit-Ganzzahl ohne Vorzeichen, der die Breite eines Objekts Bildschirm in Pixel darstellt.

- VTS_YSIZE_PIXELS ein 32-Bit-Ganzzahl ohne Vorzeichen, der die Höhe eines Objekts Bildschirm in Pixel darstellt.

- VTS_XSIZE_HIMETRIC ein 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um die Breite des ein Bildschirmobjekt in HIMETRIC-Einheiten darstellen.

- VTS_YSIZE_HIMETRIC ein 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um die Höhe des ein Bildschirmobjekt in HIMETRIC-Einheiten darstellen.

    > [!NOTE]
    >  Für alle variant-Typen, mit Ausnahme von VTS_FONT und VTS_PICTURE, wurden zusätzliche variant Konstanten definiert, die einen Zeiger auf die Konstante variant-Daten bereitstellen. Diese Konstanten werden mit dem Namen mit den VTS_P`constantname` Konvention. VTS_PCOLOR ist z. B. ein Zeiger auf eine VTS_COLOR-Konstante.

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
