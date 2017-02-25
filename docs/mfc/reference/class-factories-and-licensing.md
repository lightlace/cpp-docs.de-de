---
title: "Klassenfabriken und Lizenzierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassenfactorys, und Lizenzieren"
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Klassenfabriken und Lizenzierung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um eine Instanz des OLE\-Steuerelements zu erstellen, ruft eine Containeranwendung eine Memberfunktion der Klassenfactorys des Steuerelements auf.  Da das Steuerelement ein tatsächliches OLE\-Objekt handelt, ist die ClassFactory zum Erstellen von Instanzen eines Steuerelements verantwortlich.  Jede OLE\-Steuerelement\-Klasse muss eine Klassenfactory haben.  
  
 Eine weitere wichtige Funktion von OLE\-Steuerelementen ist die Fähigkeit, eine Lizenz zu erzwingen.  ControlWizard ermöglicht es Ihnen, der Lizenzierung während der Erstellung des Steuerelementprojekts zu enthalten.  Weitere Informationen über Steuerlizenzierung, finden Sie im Artikel [ActiveX\-Steuerelemente: Lizenzieren eines ActiveX\-Steuerelements](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 Die folgende Tabelle zeigt mehrere Makros und Funktionen auf, die verwendet werden, um der Klassenfactory des Steuerelements und der Lizenz des Steuerelements zu deklarieren und zu implementieren.  
  
### Klassenfactorys und Lizenzieren  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE\_EX](../Topic/DECLARE_OLECREATE_EX.md)|Deklariert die Klassenfactory für ein OLE\-Steuerelement oder eine Eigenschaftenseite.|  
|[IMPLEMENT\_OLECREATE\_EX](../Topic/IMPLEMENT_OLECREATE_EX.md)|Implementiert die Funktion des `GetClassID`\-Steuerelements deklariert und eine Instanz der Klassenfactorys.|  
|[BEGIN\_OLEFACTORY](../Topic/BEGIN_OLEFACTORY.md)|Startet die Deklaration aller Lizenzierungsfunktionen.|  
|[END\_OLEFACTORY](../Topic/END_OLEFACTORY.md)|Beendet die Deklaration aller Lizenzierungsfunktionen.|  
|[AfxVerifyLicFile](../Topic/AfxVerifyLicFile.md)|Überprüft, ob ein Steuerelement zur Verwendung auf einem bestimmten Computer lizenziert wird.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)