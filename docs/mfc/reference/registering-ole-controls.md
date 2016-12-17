---
title: "Registrieren des OLE-Steuerelements"
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
  - "OLE-Steuerelemente, Registrieren"
  - "Registrieren von OLE-Steuerelementen"
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
caps.latest.revision: 15
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Registrieren des OLE-Steuerelements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Klicken Sie OLE\-Steuerelemente, wie andere OLE\-Serverobjekte, können durch andere Anwendungen OLE\-bewusste zugegriffen werden.  Dies wird erreicht, indem die Typbibliothek und der Klasse des Steuerelements registriert.  
  
 Die folgenden Funktionen ermöglichen es Ihnen, von der Klasse des Steuerelements, die Eigenschaftenseiten und der Typbibliothek in der Windows\-Registrierungsdatenbank hinzuzufügen und zu entfernen:  
  
### Registrieren von OLE\-Steuerelementen  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](../Topic/AfxOleRegisterControlClass.md)|Fügt der Klasse des Steuerelements der Registrierungsdatenbank hinzu.|  
|[AfxOleRegisterPropertyPageClass](../Topic/AfxOleRegisterPropertyPageClass.md)|Fügt einer Steuerelementeigenschaftenseite der Registrierungsdatenbank hinzu.|  
|[AfxOleRegisterTypeLib](../Topic/AfxOleRegisterTypeLib.md)|Fügt der Typbibliothek des Steuerelements der Registrierungsdatenbank hinzu.|  
|[AfxOleUnregisterClass](../Topic/AfxOleUnregisterClass.md)|Entfernt eine Steuerelementklasse oder eine Eigenschaftenseitenklasse der Registrierungsdatenbank.|  
|[AfxOleUnregisterTypeLib](../Topic/AfxOleUnregisterTypeLib.md)|Entfernt die Typbibliothek des Steuerelements in der Registrierungsdatenbank.|  
  
 `AfxOleRegisterTypeLib` ist normalerweise in der Implementierung einer Steuer\-DLL von `DllRegisterServer` aufgerufen.  Entsprechend wird `AfxOleUnregisterTypeLib` von `DllUnregisterServer` aufgerufen.  `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass` und `AfxOleUnregisterClass` werden in der Regel durch die `UpdateRegistry`\-Memberfunktion der Klassenfactorys oder der Eigenschaftenseite eines Steuerelements aufgerufen.  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)