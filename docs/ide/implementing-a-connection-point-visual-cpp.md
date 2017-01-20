---
title: "Implementieren eines Verbindungspunktes (Visual C++)"
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
  - "Verbindungspunkte [C++], Implementieren"
  - "Assistent zum Implementieren von Verbindungspunkten [C++]"
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Implementieren eines Verbindungspunktes (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Damit Sie einen Verbindungspunkt mit dem Assistenten zum Implementieren von Verbindungspunkten implementieren können, ist es erforderlich, dass das Projekt als ATL COM\-Anwendung oder als MFC\-Anwendung mit integrierter ATL\-Unterstützung erstellt wurde.  Sie können den [ATL\-Projekt\-Assistenten](../atl/reference/atl-project-wizard.md) verwenden, um eine ATL\-Anwendung zu erstellen, oder der [MFC\-Anwendung ein ATL\-Objekt hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL\-Unterstützung in eine MFC\-Anwendung zu implementieren.  
  
> [!NOTE]
>  Weitere Informationen zum Implementieren von Verbindungspunkten für ein MFC\-Projekt finden Sie unter [Verbindungspunkte](../mfc/connection-points.md).  
  
 Nachdem Sie das Projekt erstellt haben, müssen Sie zuerst ein ATL\-Objekt hinzufügen, bevor Sie einen Verbindungspunkt implementieren können.  Eine Liste der Assistenten, mit denen Sie dem ATL\-Projekt Objekte hinzufügen können, finden Sie unter [Hinzufügen von Objekten und Steuerelementen zu einem ATL\-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
> [!NOTE]
>  Der Assistent unterstützt keine ATL\-Dialogfelder, mit ATL Server erstellte XML\-Webdienste, Leistungsobjekte oder Leistungsindikatoren.  
  
 Ein verbindungsfähiges Objekt \(d. h. eine Quelle\) kann für jede seiner Ausgangsschnittstellen einen Verbindungspunkt zur Verfügung stellen.  Jede Ausgangsschnittstelle kann von einem Client für ein Objekt \(d. h. eine Senke\) implementiert werden.  Weitere Informationen finden Sie unter [ATL\-Verbindungspunkte](../atl/atl-connection-points.md).  
  
### So implementieren Sie einen Verbindungspunkt  
  
1.  Klicken Sie in der Klassenansicht mit der rechten Maustaste auf den Klassennamen des ATL\-Objekts.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Verbindungspunkt hinzufügen**, um den [Assistenten zum Implementieren von Verbindungspunkten](../ide/implement-connection-point-wizard.md) aufzurufen.  
  
3.  Wählen Sie die zu implementierenden Verbindungspunkt\-Schnittstellen aus den entsprechenden Typbibliotheken aus, und klicken Sie auf **Fertig stellen**.  
  
4.  Prüfen Sie in der Klassenansicht die Proxyklassen, die für die einzelnen Verbindungspunkte erstellt wurden.  Die Klassen werden als CProxy*InterfaceName*\<T\> angezeigt und sind von [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) abgeleitet.  
  
5.  Doppelklicken Sie auf die Verbindungspunktklasse, um die Definition der Verbindungspunktklasse anzuzeigen.  
  
    -   Wenn Sie einen Verbindungspunkt für die Schnittstelle Ihres eigenen Projekts implementieren, wird die folgende Definition angezeigt:  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         Wenn Sie eine lokale Schnittstelle implementieren, werden Methoden und Eigenschaften in der Klassendefinition angezeigt.  
  
    -   Wenn Sie einen Verbindungspunkt für eine andere Schnittstelle implementieren, enthält die Definition die Schnittstellenmethoden, denen jeweils `Fire_` vorangestellt ist.  
  
## Siehe auch  
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adding Connection Points to an Object](../atl/adding-connection-points-to-an-object.md)