---
title: "Hinzuf&#252;gen einer neuen Schnittstelle in einem ATL-Projekt"
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
  - "vc.appwiz.ATL.interface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Schnittstellen"
  - "Steuerelemente [ATL], Schnittstellen"
  - "ATL-Assistent zum Implementieren von Schnittstellen"
  - "Schnittstellen, Hinzufügen zu ATL-Objekten"
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer neuen Schnittstelle in einem ATL-Projekt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einem Objekt oder Steuerelement eine Schnittstelle hinzufügen, erstellen Sie für jede Methode in dieser Schnittstelle Stub\-out\-Funktionen.  Dem Objekt oder Steuerelement können nur Schnittstellen hinzugefügt werden, die sich derzeit in einer vorhandenen Typbibliothek befinden.  Darüber hinaus muss durch die Klasse, in der Sie die Schnittstelle hinzufügen, das [BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md)\-Makro implementiert werden, bzw. das Projekt muss über das `coclass`\-Attribut verfügen, falls es attributiert ist.  
  
 Sie können unter zwei Verfahrensweisen wählen, um dem Steuerelement eine neue Schnittstelle hinzuzufügen: manuell oder unter Verwendung der Code\-Assistenten in der Klassenansicht.  
  
### So verwenden Sie Code\-Assistenten in der Klassenansicht, um einem vorhandenen Objekt bzw. Steuerelement eine Schnittstelle hinzuzufügen  
  
1.  Klicken Sie in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Klassennamen eines Steuerelements.  Hierbei kann es sich um ein standardmäßiges oder ein zusammengesetztes Steuerelement bzw. um eine beliebige andere Steuerelementklasse handeln, die ein `BEGIN_COM_MAP`\-Makro in ihrer Headerdatei implementiert.  
  
2.  Klicken Sie im Kontextmenü zunächst auf **Hinzufügen** und dann auf **Schnittstelle implementieren**.  
  
3.  Wählen Sie die zu implementierenden Schnittstellen im [Assistenten zum Implementieren von Schnittstellen](../../ide/implement-interface-wizard.md) aus.  Wenn die Schnittstelle in keiner verfügbaren `typelib` enthalten ist, müssen Sie sie der IDL\-Datei manuell hinzufügen.  
  
### So fügen Sie eine neue Schnittstelle manuell hinzu  
  
1.  Fügen Sie der IDL\-Datei die Definition der neuen Schnittstelle hinzu.  
  
2.  Leiten Sie das Objekt oder Steuerelement von der Schnittstelle ab.  
  
3.  Erstellen Sie ein neues [COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20\(ATL\).md)\-Makro für die Schnittstelle, oder fügen Sie, falls das Projekt attributiert ist, das `coclass`\-Attribut hinzu.  
  
4.  Implementieren Sie die Methoden für die Schnittstelle.  
  
## Siehe auch  
 [ATL\-Projekt\-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+\-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL\- und C\-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Standardmäßige ATL\-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)