---
title: "Erstellen einer COM-Schnittstelle (Visual C++)"
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
  - "vc.codewiz.com.creating.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM-Schnittstellen, Erstellen"
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen einer COM-Schnittstelle (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ bietet Assistenten und Vorlagen zur Projekterstellung, die Ihnen beim Definieren von COM\-Schnittstellen und Dispatchschnittstellen für COM\-Objekte und Automatisierungsklassen behilflich sind.  
  
 Mit diesen Assistenten können Sie die folgenden drei häufigen Tasks durchführen:  
  
-   [Hinzufügen von ATL\-Unterstützung zu einem MFC\-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     Fügen Sie einer MFC\-Anwendung ATL\-Unterstützung hinzu, nachdem Sie mit dem [MFC\-Anwendungs\-Assistenten](../mfc/reference/mfc-application-wizard.md) ein MFC\-Projekt erstellt haben, und führen Sie dann den Code\-Assistenten **ATL\-Unterstützung zu MFC hinzufügen** aus.  Die Unterstützung wirkt sich nur auf einfache COM\-Objekte aus, die einer MFC\-Anwendung oder einem DLL\-Projekt hinzugefügt wurden.  Diese ATL\-Objekte können über mehrere Schnittstellen verfügen.  
  
-   [Erstellen eines MFC\-ActiveX\-Steuerelements](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Öffnen Sie den [MFC\-ActiveX\-Steuerelement\-Assistenten](../mfc/reference/mfc-activex-control-wizard.md), um ein ActiveX\-Steuerelement zu erstellen, für das eine Dispatchschnittstelle und eine Ereigniszuordnung in der IDL\-Datei bzw. Steuerelementklasse definiert wurde.  
  
-   [Hinzufügen eines ATL\-Steuerelements](../atl/reference/adding-an-atl-control.md)  
  
     Um ein ATL\-ActiveX\-Steuerelement zu erstellen, kombinieren Sie den [ATL\-Projekt\-Assistenten](../atl/reference/atl-project-wizard.md) mit dem [ATL\-Steuerelement\-Assistenten](../atl/reference/atl-control-wizard.md).  
  
     Sie können einem MFC\-Projekt, dem Sie entsprechend der vorangehenden Beschreibung ATL\-Unterstützung hinzugefügt haben, auch ein ATL\-Steuerelement hinzufügen.  Wenn Sie im Dialogfeld **Klasse hinzufügen** die Option **ATL\-Steuerelement** auswählen und dem MFC\-Projekt noch keine ATL\-Unterstützung hinzugefügt haben, zeigt Visual Studio ein zusätzliches Dialogfeld an, in dem bestätigt wird, dass dem MFC\-Projekt ATL\-Unterstützung hinzugefügt wird.  
  
     Dieser Assistent erstellt eine IDL\-Quelle und eine COM\-Zuordnung in den Projektklassen.  
  
 Nachdem Sie ein ATL\-Projekt geöffnet haben, werden im Dialogfeld [Klasse hinzufügen](../ide/add-class-dialog-box.md) zusätzliche Assistenten und Vorlagen angeboten, mit denen Sie dem Projekt COM\-Schnittstellen hinzufügen können.  Mithilfe der folgenden Assistenten können Sie eine oder mehrere Schnittstellen für das Objekt einrichten:  
  
-   [ATL COM\+ 1.0 Komponenten\-Assistent](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL\-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL\-Assistent für Active Server Page\-Komponenten](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL\-Steuerelement\-Assistent](../atl/reference/atl-control-wizard.md)  
  
 Zusätzlich können Sie neue Schnittstellen für das COM\-Steuerelement implementieren, indem Sie mit der rechten Maustaste in der Klassenansicht auf die Steuerelementklasse des Objekts klicken und dann auf [Schnittstelle implementieren](../ide/implement-interface-wizard.md) klicken.  
  
> [!NOTE]
>  Visual Studio bietet keinen Assistenten zum Hinzufügen von Schnittstellen zu Projekten.  Sie können einem ATL\-Projekt eine Schnittstelle oder einem [MFC\-Projekt ATL\-Unterstützung hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), indem Sie mit dem [ATL\-Assistenten für einfache Objekte](../atl/reference/atl-simple-object-wizard.md) ein einfaches Objekt hinzufügen.  Alternativ können Sie die IDL\-Datei des Projekts öffnen und die Schnittstelle durch folgenden Code erstellen:  
  
```  
interface IMyInterface {  
};  
  
```  
  
 Weitere Informationen finden Sie unter [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md) und [Hinzufügen von Objekten und Steuerelementen zu einem ATL\-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
 Visual C\+\+ bietet mehrere Möglichkeiten zum Anzeigen und [Bearbeiten der COM\-Schnittstellen](../ide/editing-a-com-interface.md), die für Ihre Projekte definiert wurden.  Die [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) zeigt für jede Schnittstelle oder Dispatchschnittstelle, die im C\+\+\-Projekt in einer IDL\-Datei definiert ist, Symbole an.  
  
 Bei ATL\-basierten COM\-Objektklassen liest die Klassenansicht die in der ATL\-Klasse enthaltenen COM\-Zuordnungen, um die Beziehung zwischen der ATL\-Klasse und jeder von ihr implementierten Schnittstelle anzuzeigen.  
  
 In der Klassenansicht und den dazugehörigen Kontextmenüs können Sie folgende Tasks im Zusammenhang mit Schnittstellen ausführen:  
  
-   Hinzufügen von ATL\-Objekten zu einer MFC\-basierten Anwendung  
  
-   Hinzufügen von Methoden, Eigenschaften und Ereignissen  
  
-   Direktes Wechseln zum Schnittstellencode eines Elements, indem Sie auf das Element doppelklicken  
  
## Siehe auch  
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)