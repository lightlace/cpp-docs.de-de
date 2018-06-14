---
title: Erstellen einer COM-Schnittstelle (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.creating.interfaces
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2844e9051c5e6adf14085bcd7bfcd8096c6f8f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332581"
---
# <a name="creating-a-com-interface-visual-c"></a>Erstellen einer COM-Schnittstelle (Visual C++)
Visual C++ stellt Assistenten und Vorlagen zum Erstellen von Projekten bereit, die definierende COM-Schnittstellen und Disp-Schnittstellen für Ihre COM-Objekte und Automatisierungsklassen verwenden.  
  
 Sie können diese Assistenten zum Ausführen der folgenden allgemeinen Aufgaben verwenden:  
  
-   [Hinzufügen von ATL-Unterstützung zu einem MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     Hinzufügen von ATL-Unterstützung zu einer MFC-Anwendung, nachdem Sie ein MFC-Projekt mithilfe des [MFC-Anwendungs-Assistenten](../mfc/reference/mfc-application-wizard.md) erstellt haben, und Ausführen des Code-Assistenten zum **Hinzufügen von ATL-Unterstützung zu MFC**. Diese Unterstützung gilt nur für einfache COM-Objekte, die einer MFC-Anwendung oder einem DLL-Projekt hinzugefügt werden. Diese ATL-Objekte können über mehrere Schnittstellen verfügen.  
  
-   [Erstellen eines MFC-ActiveX-Steuerelements](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Öffnen Sie den [MFC-ActiveX-Steuerelement-Assistenten](../mfc/reference/mfc-activex-control-wizard.md), um ein ActiveX-Steuerelement mit einer Disp-Schnittstelle und einer Ereigniszuordnung zu erstellen, die jeweils in der IDL-Datei und der Steuerelementklasse definiert werden.  
  
-   [Hinzufügen eines ATL-Steuerelements](../atl/reference/adding-an-atl-control.md)  
  
     Verwenden Sie eine Kombination aus dem [ATL-Projekt-Assistenten](../atl/reference/atl-project-wizard.md) und dem [ATL-Steuerelement-Assistenten](../atl/reference/atl-control-wizard.md), um ein ATL-ActiveX-Steuerelement zu erstellen.  
  
     Sie können auch einem MFC-Projekt, dem Sie wie oben beschrieben ATL-Unterstützung hinzugefügt haben, ein ATL-Steuerelement hinzufügen. Darüber hinaus zeigt Visual Studio ein Dialogfeld zur Bestätigung des Hinzufügens von ATL-Unterstützung zu dem MFC-Projekt an, wenn Sie **ATL-Steuerelement** im Dialogfeld **Klasse hinzufügen** ausgewählt und dem MFC-Projekt noch keine ATL-Unterstützung hinzugefügt haben.  
  
     Dieser Assistent generiert die IDL-Quelle und eine COM-Zuordnung in den Projektklassen.  
  
 Sobald Sie ein ATL-Projekt geöffnet haben, erhalten Sie im Dialogfeld [Klasse hinzufügen](../ide/add-class-dialog-box.md) eine Auswahl zusätzlicher Assistenten und Vorlagen zum Hinzufügen von COM-Schnittstellen zum Projekt. Mithilfe der folgenden Assistenten können Sie mehrere Schnittstellen für das Objekt erstellen:  
  
-   [ATL COM+ 1.0 Komponenten-Assistent](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL-Assistent für Active Server Page-Komponenten](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md)  
  
 Darüber hinaus können Sie neue Schnittstellen in Ihrem COM-Steuerelement implementieren, indem Sie in der Klassenansicht mit der rechten Maustaste auf die Steuerelementklasse des Objekts klicken, klicken Sie dann auf [Schnittstelle implementieren](../ide/implement-interface-wizard.md).  
  
> [!NOTE]
>  Visual Studio stellt keinen Assistenten dafür bereit, Schnittstellen zu einem Projekt hinzuzufügen. Sie können Schnittstellen zu einem ATL-Projekt oder zu einem [MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md) hinzufügen, indem Sie mithilfe des [ATL-Assistenten für einfache Objekte](../atl/reference/atl-simple-object-wizard.md) ein einfaches Objekt hinzufügen. Öffnen Sie alternativ die IDL-Datei des Projekts, und erstellen Sie die Schnittstelle, indem Sie Folgendes eingeben:  
  
```  
interface IMyInterface {  
};  
  
```  
  
 Weitere Informationen finden Sie unter [Implementing an Interface (Implementieren einer Schnittstelle)](../ide/implementing-an-interface-visual-cpp.md) und [Adding Objects and Controls to an ATL Project (Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt)](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
 Visual C++ bietet mehrere Möglichkeiten zum Anzeigen und [Bearbeiten der COM-Schnittstellen](../ide/editing-a-com-interface.md), die für Ihre Projekte definiert sind. Die [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) zeigt Symbole für Schnittstellen oder Disp-Schnittstellen an, die in einer IDL-Datei in Ihrem Projekt definiert sind.  
  
 Bei ATL-basierten COM-Objektklassen liest die Klassenansicht die COM-Zuordnung in der ATL-Klasse zum Anzeigen der Beziehung zwischen der ATL-Klasse und allen Schnittstellen, die sie implementiert.  
  
 In der Klassenansicht und den zugehörigen Kontextmenüs können Sie wie folgt mit Schnittstellen arbeiten:  
  
-   Fügen Sie ATL-Objekte zu einer MFC-basierten Anwendung hinzu.  
  
-   Fügen Sie Methoden, Eigenschaften und Ereignisse hinzu.  
  
-   Navigieren Sie direkt zum Schnittstellencode eines Elements, indem Sie auf das Element doppelklicken.  
  
## <a name="see-also"></a>Siehe auch  
 [Creating Desktop Projects By Using Application Wizards (Erstellen von Desktopprojekten mit Anwendungs-Assistenten)](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)