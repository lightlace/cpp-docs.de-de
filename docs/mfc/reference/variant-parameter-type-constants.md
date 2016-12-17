---
title: "Variant-Parametertypkonstanten"
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
  - "VTS_YPOS_HIMETRIC"
  - "VTS_PICTURE"
  - "VTS_FONT"
  - "VTS_XPOS_HIMETRIC"
  - "VTS_XPOS_PIXELS"
  - "VTS_XSIZE_HIMETRIC"
  - "VTS_YPOS_PIXELS"
  - "VTS_TRISTATE"
  - "VTS_HANDLE"
  - "VTS_YSIZE_HIMETRIC"
  - "VTS_COLOR"
  - "VTS_OPTEXCLUSIVE"
  - "VTS_YSIZE_PIXELS"
  - "VTS_XSIZE_PIXELS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Variant-Datenkonstanten"
  - "Varianten"
  - "Varianten, Parametertypkonstanten"
  - "VTS_COLOR-Konstante"
  - "VTS_FONT-Konstante"
  - "VTS_HANDLE-Konstante"
  - "VTS_OPTEXCLUSIVE-Konstante"
  - "VTS_PICTURE-Konstante"
  - "VTS_TRISTATE-Konstante"
  - "VTS_XPOS_HIMETRIC-Konstante"
  - "VTS_XPOS_PIXELS-Konstante"
  - "VTS_XSIZE_HIMETRIC-Konstante"
  - "VTS_XSIZE_PIXELS-Konstante"
  - "VTS_YPOS_HIMETRIC-Konstante"
  - "VTS_YPOS_PIXELS-Konstante"
  - "VTS_YSIZE_HIMETRIC-Konstante"
  - "VTS_YSIZE_PIXELS-Konstante"
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
caps.latest.revision: 14
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Variant-Parametertypkonstanten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema führt neue Konstanten, die den varianten Parametertypen angeben, die in den OLE\-Steuerelement\-Klassen der Microsoft Foundation Class\-Bibliothek vorgesehen sind.  
  
 Die folgende Liste Klassenkonstanten:  
  
##  <a name="_mfc_variant_data_constants"></a> Variante Datenkonstanten  
  
-   **VTS\_COLOR** Eine 32\-Bit\-Ganzzahl verwendet, um einen RGB\-Farbwert darzustellen.  
  
-   Zeiger **VTS\_FONT** Eine zur **IFontDisp**\-Schnittstelle eines OLE\-Schriftartobjekts.  
  
-   **VTS\_HANDLE** ein Windows\-Handlewert.  
  
-   Zeiger **VTS\_PICTURE** Eine zur `IPictureDisp`\-Schnittstelle eines OLE\-Bildobjekts.  
  
-   16\-Bit\-Wert **VTS\_OPTEXCLUSIVE** A verwendet für ein Steuerelement, das bestimmt wird, in einer Gruppe von Steuerelementen verwendet werden, z Optionsfeldern.  Dieser Typ gibt dem Container mit, dass, wenn ein Steuerelement in einer Gruppe einen Wert **TRUE** hat, andere müssen alle **FALSE** sein.  
  
-   **VTS\_TRISTATE** Eine 16\-Bit\-Ganzzahl mit Vorzeichen verwendet für Eigenschaften, die einem von drei möglichen Werten \(ausgewählt, gelöscht, nicht verfügbar\) beispielsweise ein Kontrollkästchen verfügen können.  
  
-   **VTS\_XPOS\_HIMETRIC** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um eine Position auf der x\-Achse in **HIMETRIC** Einheiten darzustellen.  
  
-   **VTS\_YPOS\_HIMETRIC** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der y\-Achse in **HIMETRIC** Einheiten darzustellen.  
  
-   **VTS\_XPOS\_PIXELS** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um eine Position auf der x\-Achse in Pixel.  
  
-   **VTS\_YPOS\_PIXELS** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um eine Position entlang der y\-Achse in Pixel.  
  
-   **VTS\_XSIZE\_PIXELS** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um die Breite eines Bildschirmobjekts in Pixel.  
  
-   **VTS\_YSIZE\_PIXELS** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um die Höhe eines Bildschirmobjekts in Pixel.  
  
-   **VTS\_XSIZE\_HIMETRIC** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um die Breite eines Bildschirmobjekts in **HIMETRIC** Einheiten darzustellen.  
  
-   **VTS\_YSIZE\_HIMETRIC** Eine 32\-Bit\-Ganzzahl ohne Vorzeichen verwendet, um die Höhe eines Bildschirmobjekts in **HIMETRIC** Einheiten darzustellen.  
  
    > [!NOTE]
    >  Zusätzliche variante Konstanten sind für alle varianten Typen, mit Ausnahme von **VTS\_FONT** und **VTS\_PICTURE** definiert wurde, die einen Zeiger auf die Datenkonstante varianten bereitstellen.  Diese Konstanten werden mithilfe der Konvention **VTS\_P**`constantname`.  Beispielsweise ist **VTS\_PCOLOR** ein Zeiger auf eine **VTS\_COLOR** Konstante.  
  
## Voraussetzungen  
 **Header:** afxdisp.h  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)