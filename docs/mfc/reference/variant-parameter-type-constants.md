---
title: Variant-Parametertypkonstanten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
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
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: cc8daf0853a97e8903b47d29f70e190430931fd5
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="variant-parameter-type-constants"></a>Variant-Parametertypkonstanten
Dieses Thema enthält neue Konstanten, die angeben, variant Parametertypen für die Verwendung mit der OLE-Steuerelementklassen von den Microsoft Foundation Class-Bibliothek konzipiert.  
  
 Im folgenden finden eine Liste von Klasse-Konstanten:  
  
##  <a name="_mfc_variant_data_constants"></a>Variant-Datenkonstanten  
  
-   **VTS_COLOR** eine 32-Bit-Ganzzahl, die verwendet, um einen RGB-Farbwert darzustellen.  
  
-   **VTS_FONT** ein Zeiger auf die **IFontDisp** Schnittstelle einer Schriftart OLE-Objekts.  
  
-   **VTS_HANDLE** ein Fensterhandle-Wert.  
  
-   **VTS_PICTURE** ein Zeiger auf die `IPictureDisp` Schnittstelle ein Bild OLE-Objekts.  
  
-   **VTS_OPTEXCLUSIVE** ein 16-Bit-Wert für ein Steuerelement, das in einer Gruppe von Steuerelementen, wie z. B. Optionsfelder verwendet werden soll. Dieser Typ weist dem Container, wenn eine, in steuern eine Gruppe verfügt über eine **"true"** Wert ist, müssen alle anderen enthalten **"false"**.  
  
-   **VTS_TRISTATE** ein 16-Bit-Ganzzahl mit Vorzeichen verwendet für Eigenschaften, die einen von drei möglichen Werten (ausgewählte, deaktiviert, nicht verfügbar), z. B. haben, können Sie das Kontrollkästchen.  
  
-   **VTS_XPOS_HIMETRIC** eine 32-Bit-Ganzzahl ohne Vorzeichen zur Darstellung von einer Position entlang der x-Achse in **HIMETRIC** Einheiten.  
  
-   **VTS_YPOS_HIMETRIC** eine 32-Bit-Ganzzahl ohne Vorzeichen zur Darstellung von einer Position entlang der y-Achse in **HIMETRIC** Einheiten.  
  
-   **VTS_XPOS_PIXELS** eine 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der x-Achse in Pixel darstellen.  
  
-   **VTS_YPOS_PIXELS** eine 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der y-Achse in Pixel darstellen.  
  
-   **VTS_XSIZE_PIXELS** eine 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um die Breite eines Objekts Bildschirm in Pixel darstellen.  
  
-   **VTS_YSIZE_PIXELS** eine 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um die Höhe eines Objekts Bildschirm in Pixel darstellen.  
  
-   **VTS_XSIZE_HIMETRIC** eine 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um die Breite eines Objekts im Bildschirm darzustellen **HIMETRIC** Einheiten.  
  
-   **VTS_YSIZE_HIMETRIC** eine 32-Bit-Ganzzahl ohne Vorzeichen verwendet, um die Höhe eines Objekts im Bildschirm darzustellen **HIMETRIC** Einheiten.  
  
    > [!NOTE]
    >  Zusätzliche Variante Konstanten für alle variant-Typen, mit Ausnahme von definiert wurden **VTS_FONT** und **VTS_PICTURE**, die einen Zeiger auf das co variant-Daten bereitstellen Nstant. Diese Konstanten sind benannt der **VTS_P** `constantname` Konvention. Beispielsweise **VTS_PCOLOR** ist ein Zeiger auf eine **VTS_COLOR** konstant.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

