---
title: "Implementieren einer Schnittstelle (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schnittstellen, Implementieren"
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Implementieren einer Schnittstelle (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zum Implementieren einer Schnittstelle ist es erforderlich, dass das Projekt als ATL\-Anwendung oder als MFC\-Anwendung mit integrierter ATL\-Unterstützung erstellt wurde.  Sie können den [ATL\-Projekt\-Assistenten](../atl/reference/atl-project-wizard.md) verwenden, um eine ATL\-Anwendung zu erstellen, oder der [MFC\-Anwendung ein ATL\-Objekt hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL\-Unterstützung in eine MFC\-Anwendung zu implementieren.  
  
 Nachdem Sie das Projekt erstellt haben, müssen Sie zuerst ein ATL\-Objekt hinzufügen, bevor Sie eine Schnittstelle implementieren können.  Eine Liste der Assistenten, mit denen Sie dem ATL\-Projekt Objekte hinzufügen können, finden Sie unter [Hinzufügen von Objekten und Steuerelementen zu einem ATL\-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
> [!NOTE]
>  Der Assistent unterstützt keine ATL\-Dialogfelder, XML\-Webdienste mit ATL, Leistungsobjekte oder Leistungsindikatoren.  
  
 Wenn Sie ein [ATL\-Steuerelement hinzufügen](../atl/reference/adding-an-atl-control.md), können Sie festlegen, ob Sie Standardschnittstellen implementieren möchten. Diese sind auf der Seite [Schnittstellen](../atl/reference/interfaces-atl-control-wizard.md) dieses Assistenten aufgeführt und in **atlcom.h** definiert.  
  
 Nachdem Sie das Objekt oder das Steuerelement hinzugefügt haben, können Sie mit dem Assistenten zum Implementieren von Schnittstellen weitere Schnittstellen aus einer beliebigen verfügbaren Typbibliothek implementieren.  
  
 Wenn Sie eine neue Schnittstelle hinzufügen, müssen Sie diese manuell in die IDL\-Datei des Projekts einfügen.  Weitere Informationen finden Sie unter [Hinzufügen einer neuen Schnittstelle in einem ATL\-Projekt](../atl/reference/adding-a-new-interface-in-an-atl-project.md).  
  
### So implementieren Sie eine Schnittstelle  
  
1.  Klicken Sie in der Klassenansicht mit der rechten Maustaste auf den Klassennamen des ATL\-Objekts.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Schnittstelle implementieren**, um den [Assistenten zum Implementieren von Schnittstellen](../ide/implement-interface-wizard.md) aufzurufen.  
  
3.  Wählen Sie die zu implementierenden Schnittstellen aus den geeigneten Typbibliotheken aus, und klicken Sie auf **Fertig stellen**.  
  
4.  Erweitern Sie in der Klassenansicht den Knoten **Basen und Schnittstellen** des Objekts, um die implementierte Schnittstelle anzuzeigen. Anschließend erweitern Sie den Schnittstellenknoten, um die verfügbaren Eigenschaften, Methoden und Ereignisse einzublenden.  
  
    > [!NOTE]
    >  Sie können die Schnittstellenmember auch mit dem [Objektkatalog](assetId:///f89acfc5-1152-413d-9f56-3dc16e3f0470) überprüfen.  
  
## Siehe auch  
 [Erstellen einer COM\-Schnittstelle](../ide/creating-a-com-interface-visual-cpp.md)   
 [Bearbeiten einer COM\-Schnittstelle](../ide/editing-a-com-interface.md)