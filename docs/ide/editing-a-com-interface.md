---
title: "Bearbeiten einer COM-Schnittstelle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.com.editing.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM-Schnittstellen, Bearbeiten"
  - "Methoden [C++], Hinzufügen zu COM-Schnittstellen"
  - "Eigenschaften [C++], Hinzufügen zu COM-Schnittstellen"
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bearbeiten einer COM-Schnittstelle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit den Befehlen im Kontextmenü der Klassenansicht können Sie neue Methoden und Eigenschaften für die COM\-Schnittstellen in Visual C\+\+\-Projekten definieren.  Darüber hinaus können Sie mithilfe der Toolbox Ereignisse für ActiveX\-Steuerelemente definieren.  
  
 Bei COM\-Objektklassen, die auf ATL oder MFC basieren, können Sie die Klassenimplementierung und die Schnittstelle gleichzeitig bearbeiten.  
  
> [!NOTE]
>  Wurden Schnittstellen nicht im Dialogfeld **Klasse hinzufügen** definiert, fügt Visual C\+\+ der IDL\-Datei Methoden oder Eigenschaften und den Klassen, durch die Methoden implementiert werden, Stubs hinzu. Dies trifft auch zu, wenn Schnittstellen manuell hinzugefügt werden.  
  
 Mit den folgenden drei Assistenten können Sie vorhandene Schnittstellen anpassen.  Diese Assistenten können Sie in der Klassenansicht auswählen:  
  
|Assistent|Projekttyp|  
|---------------|----------------|  
|[Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md)|ATL\- oder MFC\-Projekte, die ATL unterstützen.  Klicken Sie mit der rechten Maustaste auf die Schnittstelle, der die Eigenschaft hinzugefügt werden soll.<br /><br /> Visual C\+\+ erkennt den Projekttyp und ändert die Optionen im Assistenten zum Hinzufügen von Eigenschaften entsprechend:<br /><br /> -   Für Dispatchschnittstellen in Projekten, die mit dem [MFC\-Anwendungs\-Assistenten](../mfc/reference/mfc-application-wizard.md) erstellt wurden, zeigt der Assistent zum Hinzufügen von Eigenschaften MFC\-spezifische Optionen an.<br />-   Bei MFC\-ActiveX\-Steuerelementschnittstellen bietet der Assistent zum Hinzufügen von Eigenschaften eine Liste von vordefinierten Methoden und Basiseigenschaften, die wie angegeben verwendet oder für das Steuerelement angepasst werden können.<br />-   Bei allen übrigen Schnittstellen bieten die Assistenten zum Hinzufügen von Eigenschaften Optionen an, die in den meisten Situationen nützlich sind.|  
|[Assistent zum Hinzufügen von Methoden](../ide/add-method-wizard.md)|ATL\- oder MFC\-Projekte, die ATL unterstützen.  Klicken Sie mit der rechten Maustaste auf die Schnittstelle, der die Methode hinzugefügt werden soll.<br /><br /> Visual C\+\+ erkennt den Projekttyp und ändert die Optionen im Assistenten zum Hinzufügen von Methoden entsprechend:<br /><br /> -   Für Dispatchschnittstellen in Projekten, die mit dem [MFC\-Anwendungs\-Assistenten](../mfc/reference/mfc-application-wizard.md) erstellt wurden, zeigt der Assistent zum Hinzufügen von Methoden MFC\-spezifische Optionen an.<br />-   Bei MFC\-ActiveX\-Steuerelementschnittstellen bietet der Assistent zum Hinzufügen von Methoden eine Liste von vordefinierten Methoden und Basiseigenschaften, die wie angegeben verwendet oder für das Steuerelement angepasst werden können.<br />-   Bei allen übrigen Schnittstellen bieten die Assistenten zum **Hinzufügen von Methoden** Optionen an, die in den meisten Situationen nützlich sind.|  
  
 Zusätzlich können Sie neue Schnittstellen für das COM\-Steuerelement implementieren, indem Sie mit der rechten Maustaste in der Klassenansicht auf die Steuerelementklasse des Objekts klicken und dann auf [Schnittstelle implementieren](../ide/implement-interface-wizard.md) klicken.  
  
## Siehe auch  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C\+\+\-Projekttypen](../ide/visual-cpp-project-types.md)