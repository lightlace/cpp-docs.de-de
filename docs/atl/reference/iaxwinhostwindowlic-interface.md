---
title: "IAxWinHostWindowLic Interface"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "IAxWinHostWindowLic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindowLic interface"
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindowLic Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Schnittstelle stellt Methoden zum Bearbeiten eines lizenzierten Steuerelements und seines Hostobjekts bereit.  
  
## Syntax  
  
```  
  
interface IAxWinHostWindowLic : IAxWinHostWindow  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[CreateControlLic](../Topic/IAxWinHostWindowLic::CreateControlLic.md)|Erstellt ein lizenziertes Steuerelement und fügt es dem Hostobjekt an.|  
|[CreateControlLicEx](../Topic/IAxWinHostWindowLic::CreateControlLicEx.md)|Erstellt ein lizenziertes Steuerelement, fügt es dem Hostobjekt an installiert und optional einen Ereignishandler.|  
  
## Hinweise  
 `IAxWinHostWindowLic` erbt von [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) und fügt Methoden hinzu, die die Erstellung von lizenzierten Steuerelemente unterstützen.  
  
 Siehe [Hosten von ActiveX\-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, das die Member dieser Schnittstelle verwendet.  
  
## Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL\-Datei oder C\+\+, wie unten verfügbar.  
  
|Definitionstyp|Datei|  
|--------------------|-----------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(auch enthaltene ATLBase.h\)|