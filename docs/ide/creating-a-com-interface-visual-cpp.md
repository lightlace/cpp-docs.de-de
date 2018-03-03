---
title: Erstellen einer COM-Schnittstelle (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.com.creating.interfaces
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7b5820686c3e6f01c37cbf527d0e631e5bcc25c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-com-interface-visual-c"></a>Erstellen einer COM-Schnittstelle (Visual C++)
Visual C++ stellt Assistenten und Vorlagen, um Projekte zu erstellen, die Definieren von COM-Schnittstellen und Disp-Schnittstellen für die COM-Objekte und Automatisierungsklassen verwenden.  
  
 Diese Assistenten können Sie die folgenden drei allgemeine Aufgaben ausführen:  
  
-   [Hinzufügen von ATL-Unterstützung zu einem MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     ATL-Unterstützung für eine MFC_Anwendung hinzufügen, nach dem Erstellen einer MFC-Projekt mit der [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md) und dann die **Hinzufügen von ATL-Unterstützung in MFC** Code-Assistenten. Diese Unterstützung gilt nur für einfache COM-Objekte, die zu einer MFC-Anwendung oder DLL-Projekt hinzugefügt. Diese ATL-Objekte über mehrere Schnittstellen verfügen.  
  
-   [Erstellen eines MFC-ActiveX-Steuerelements](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Öffnen der [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md) So erstellen Sie ein ActiveX-Steuerelement mit einer Dispinterface und ein ereigniszuordnung bzw. in der IDL-Datei und der Control-Klasse definiert.  
  
-   [Hinzufügen eines ATL-Steuerelements](../atl/reference/adding-an-atl-control.md)  
  
     Eine Kombination der [ATL-Projekt-Assistent](../atl/reference/atl-project-wizard.md) und [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md) zum Erstellen eines ATL-ActiveX-Steuerelements.  
  
     Sie können auch ein ATL-Steuerelement zu einem MFC-Projekt, dem Sie ATL-Unterstützung hinzugefügt haben, hinzufügen, wie oben beschrieben. Darüber hinaus bei Auswahl des **ATL-Steuerelement** in der **Klasse hinzufügen** (Dialogfeld), und Sie haben noch nicht hinzugefügt ATL-Unterstützung zu MFC-Projekt, zeigt ein Dialogfeld zur Bestätigung zum Hinzufügen von ATL-Unterstützung für Visual Studio Ihre MFC-Projekt.  
  
     Dieser Assistent generiert die IDL-Quelle und ein COM-Zuordnung in den Projektklassen.  
  
 Nachdem Sie eine ATL-Projekt zu öffnen, haben die [Klasse hinzufügen](../ide/add-class-dialog-box.md) Dialogfeld ermöglicht es Ihnen zusätzliche Assistenten und Vorlagen, COM-Schnittstellen zum Projekt hinzufügen. Die folgenden Assistenten können Sie eine oder mehrere Schnittstellen für das Objekt herzustellen:  
  
-   [ATL COM+ 1.0 Komponenten-Assistent](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL-Assistent für Active Server Page-Komponenten](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md)  
  
 Darüber hinaus können Sie neue Schnittstellen auch auf das COM-Steuerelement implementieren, indem Steuerelementklasse für das Objekt in der Klassenansicht mit der rechten Maustaste, und klicken Sie auf [Schnittstelle implementieren](../ide/implement-interface-wizard.md).  
  
> [!NOTE]
>  Visual Studio bietet keinen Assistenten, um eine Schnittstelle zu einem Projekt hinzufügen. Sie können eine Schnittstelle zu einem ATL-Projekt oder hinzufügen ein [Hinzufügen von ATL-Unterstützung auf MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md) ein einfaches Objekt mithilfe der [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md). Alternativ öffnen Sie das Projekt IDL-Datei, und erstellen Sie die Schnittstelle, indem Sie Folgendes eingeben:  
  
```  
interface IMyInterface {  
};  
  
```  
  
 Finden Sie unter [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md) und [Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) für Weitere Informationen.  
  
 Visual C++ bietet verschiedene Möglichkeiten zur Anzeige und [bearbeiten Sie die COM-Schnittstellen](../ide/editing-a-com-interface.md) für Ihre Projekte definiert. [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) zeigt Symbole für jede Schnittstelle oder Disp-Schnittstelle in einer IDL-Datei in Ihrem C++-Projekt.  
  
 ATL-basierten COM Objektklassen liest Klassenansicht die COM-Zuordnung in der ATL-Klasse zum Anzeigen der Beziehung zwischen der ATL-Klasse und einer Schnittstelle implementiert.  
  
 In der Klassenansicht und die Kontextmenüs können Sie wie folgt mit Schnittstellen arbeiten:  
  
-   ATL-Objekte zu einer MFC-basierten Anwendung hinzufügen.  
  
-   Fügen Sie Methoden, Eigenschaften und Ereignisse.  
  
-   Verweisen Sie direkt auf ein Element verknüpfen von Code, durch Doppelklicken auf das Element.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)