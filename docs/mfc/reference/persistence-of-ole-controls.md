---
title: "Persistenz der OLE-Steuerelemente"
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
  - "vc.mfc.macros.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE-Steuerelemente, Dauerhaftigkeit"
  - "Dauerhaftigkeit, OLE-Steuerelemente"
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Persistenz der OLE-Steuerelemente
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Funktion von OLE\-Steuerelementen ist Eigenschaftenpersistenz \(oder der Serialisierung\), die dem OLE\-Steuerelement ermöglicht, Eigenschaftswerte in und aus einer Datei zu lesen oder zu schreiben oder einem Stream.  Eine Containeranwendung kann Serialisierung verwenden, um die Eigenschaftswerte eines Steuerelements zu speichern, wenn die Anwendung das Steuerelement zerstört wurde.  Die Eigenschaftswerte des OLE\-Steuerelements können aus der Datei bzw. dem Stream dann gelesen werden, wenn eine neue Instanz des Steuerelements auf einen späteren Zeitpunkt erstellt wird.  
  
### Beibehaltung von OLE\-Steuerelementen  
  
|||  
|-|-|  
|[PX\_Blob](../Topic/PX_Blob.md)|Vertauscht eine Steuerelementeigenschaft aus, die Binary Large Object\-Daten \(BLOB\) speichert.|  
|[PX\_Bool](../Topic/PX_Bool.md)|Vertauscht eine Steuerelementeigenschaft des Typs **BOOL** aus.|  
|[PX\_Color](../Topic/PX_Color.md)|Vertauscht eine Farbeigenschaft eines Steuerelements aus.|  
|[PX\_Currency](../Topic/PX_Currency.md)|Vertauscht eine Steuerelementeigenschaft des Typs **CY** aus.|  
|[PX\_DataPath](../Topic/PX_DataPath.md)|Vertauscht eine Steuerelementeigenschaft des Typs `CDataPathProperty` aus.|  
|[PX\_Double](../Topic/PX_Double.md)|Vertauscht eine Steuerelementeigenschaft des Typs **double** aus.|  
|[PX\_Font](../Topic/PX_Font.md)|Vertauscht eine Schriftarteigenschaft eines Steuerelements aus.|  
|[PX\_Float](../Topic/PX_Float.md)|Vertauscht eine Steuerelementeigenschaft des Typs **float** aus.|  
|[PX\_IUnknown](../Topic/PX_IUnknown.md)|Vertauscht eine Steuerelementeigenschaft des undefinierten Typs aus.|  
|[PX\_Long](../Topic/PX_Long.md)|Vertauscht eine Steuerelementeigenschaft des Typs **long** aus.|  
|[PX\_Picture](../Topic/PX_Picture.md)|Vertauscht eine Bildeigenschaft eines Steuerelements aus.|  
|[PX\_Short](../Topic/PX_Short.md)|Vertauscht eine Steuerelementeigenschaft des Typs **short** aus.|  
|[PX\_ULong](../Topic/PX_ULong.md)|Vertauscht eine Steuerelementeigenschaft des Typs **ULONG** aus.|  
|[PX\_UShort](../Topic/PX_UShort.md)|Vertauscht eine Steuerelementeigenschaft des Typs **USHORT** aus.|  
|[PX\_String](../Topic/PX_String.md)|Vertauscht eine Zeichenfolgensteuerelementeigenschaft aus.|  
|[PX\_VBXFontConvert](../Topic/PX_VBXFontConvert.md)|Vertauscht die schriftartbezogenen Eigenschaften eines VBX\-Steuer in eine OLE\-Steuerelement\-Schriftarteigenschaft aus.|  
  
 Außerdem wird die globale `AfxOleTypeMatchGuid`\-Funktion auf den Test für eine Übereinstimmung zwischen `TYPEDESC` und einer angegebenen GUID bereitgestellt.  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)