---
title: "Dialogdatenaustausch-Funktionen f&#252;r OLE-Steuerelemente"
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
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), OLE-Unterstützung"
  - "OLE-Steuerelemente, DDX-Funktionen"
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
caps.latest.revision: 13
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Dialogdatenaustausch-Funktionen f&#252;r OLE-Steuerelemente
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema führt die DDX\_OC\-Funktionen auf, die für den Datenaustausch zwischen einer Eigenschaft eines OLE\-Steuerelements in einem Dialogfeld, Formularansicht oder Steuerelementansichtsobjekt und ein Datenmember des Dialogfelds, der Formularansicht oder des Steuerelementansichtsobjekts verwendet werden.  
  
### DDX\_OC\-Funktionen  
  
|||  
|-|-|  
|[DDX\_OCBool](../Topic/DDX_OCBool.md)|**BOOL** Verwaltet die Übertragung von Daten zwischen einer Eigenschaft eines OLE\-Steuerelements und einem **BOOL** Datenmember.|  
|[DDX\_OCBoolRO](../Topic/DDX_OCBoolRO.md)|**BOOL** Verwaltet die Übertragung von Daten zwischen einer schreibgeschützten Eigenschaft eines OLE\-Steuerelements und einem **BOOL** Datenmember.|  
|[DDX\_OCColor](../Topic/DDX_OCColor.md)|**OLE\_COLOR** Verwaltet die Übertragung von Daten zwischen einer Eigenschaft eines OLE\-Steuerelements und einem **OLE\_COLOR** Datenmember.|  
|[DDX\_OCColorRO](../Topic/DDX_OCColorRO.md)|**OLE\_COLOR** Verwaltet die Übertragung von Daten zwischen einer schreibgeschützten Eigenschaft eines OLE\-Steuerelements und einem **OLE\_COLOR** Datenmember.|  
|[DDX\_OCFloat](../Topic/DDX_OCFloat.md)|Verwaltet die Übertragung von Daten \( **float** oder **double**\) zwischen einer Eigenschaft eines OLE\-Steuerelements und einem Datenmember **float** \(oder **double**\).|  
|[DDX\_OCFloatRO](../Topic/DDX_OCFloatRO.md)|Verwaltet die Übertragung von Daten \( **float** oder **double**\) zwischen einer schreibgeschützten Eigenschaft eines OLE\-Steuerelements und einem Datenmember **float** \(oder **double**\).|  
|[DDX\_OCInt](../Topic/DDX_OCInt.md)|Verwaltet die Übertragung von Daten \( `int` oder **long**\) zwischen einer Eigenschaft eines OLE\-Steuerelements und einem Datenmember \( `int` oder **long**\).|  
|[DDX\_OCIntRO](../Topic/DDX_OCIntRO.md)|Verwaltet die Übertragung von Daten \( `int` oder **long**\) zwischen einer schreibgeschützten Eigenschaft eines OLE\-Steuerelements und einem Datenmember \( `int` oder **long**\).|  
|[DDX\_OCShort](../Topic/DDX_OCShort.md)|**short** Verwaltet die Übertragung von Daten zwischen einer Eigenschaft eines OLE\-Steuerelements und einem **short** Datenmember.|  
|[DDX\_OCShortRO](../Topic/DDX_OCShortRO.md)|**short** Verwaltet die Übertragung von Daten zwischen einer schreibgeschützten Eigenschaft eines OLE\-Steuerelements und einem **short** Datenmember.|  
|[DDX\_OCText](../Topic/DDX_OCText.md)|**CString**  Verwaltet die Übertragung von Daten zwischen einer Eigenschaft eines OLE\-Steuerelements und einem **CString**  Datenmember.|  
|[DDX\_OCTextRO](../Topic/DDX_OCTextRO.md)|**CString**  Verwaltet die Übertragung von Daten zwischen einer schreibgeschützten Eigenschaft eines OLE\-Steuerelements und einem **CString**  Datenmember.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)