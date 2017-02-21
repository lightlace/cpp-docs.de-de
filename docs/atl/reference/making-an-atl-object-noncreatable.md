---
title: "Konfigurieren eines ATL-Objekts als nicht erstellbares Objekt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Nicht erstellbare Objekte"
  - "Nicht erstellbare ATL-Objekte"
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Konfigurieren eines ATL-Objekts als nicht erstellbares Objekt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können die Attribute eines ATL\-basierten COM\-Objekts ändern, sodass das Objekt nicht direkt von einem Client erstellt werden kann.  Das Objekt würde in diesem Fall durch einen Methodenaufruf eines anderen Objekts zurückgegeben, aber nicht direkt erstellt werden.  
  
### So konfigurieren Sie ein Objekt als nicht erstellbares Objekt  
  
1.  Entfernen Sie das [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md)\-Makro für das Objekt.  Wenn das Objekt nicht erstellbar sein, das Steuerelement jedoch registriert werden soll, ersetzen Sie `OBJECT_ENTRY_AUTO` durch [OBJECT\_ENTRY\_NON\_CREATEABLE\_EX\_AUTO](../Topic/OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO.md).  
  
2.  Fügen Sie der in der IDL\-Datei enthaltenen Co\-Klasse das [noncreatable](../../windows/noncreatable.md)\-Attribut hinzu.  Beispiel:  
  
    ```  
    [  
       uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),  
       helpstring("MyObject"),  
      noncreatable  
    ]  
    coclass MyObject  
    {  
       [default] interface IMyInterface;  
    }  
    ```  
  
## Siehe auch  
 [ATL\-Projekt\-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+\-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL\- und C\-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Standardmäßige ATL\-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)