---
title: Implementieren eines Verbindungspunktes (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab065c78d8ea5d2de105abdc2fa651e05f9d1875
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-connection-point-visual-c"></a>Implementieren eines Verbindungspunktes (Visual C++)
Um einen Verbindungspunkt mit dem Assistenten für zeigen der implementieren Verbindung zu implementieren, müssen Sie erstellt haben ein Projekt als ATL COM-Anwendung oder als eine MFC-Anwendung, die ATL-Unterstützung enthält. Können Sie die [ATL-Projektassistenten](../atl/reference/atl-project-wizard.md) zum Erstellen einer Anwendung ATL oder [Hinzufügen eines ATL-Objekts zu der MFC-Anwendung](../mfc/reference/adding-atl-support-to-your-mfc-project.md) ATL-Unterstützung für eine MFC-Anwendung zu implementieren.  
  
> [!NOTE]
>  Informationen zum Implementieren von Verbindungspunkten für ein MFC-Projekt finden Sie unter [Verbindungspunkte](../mfc/connection-points.md).  
  
 Nach des Projekts erstellen, um einen Verbindungspunkt zu implementieren, müssen Sie zuerst ein ATL-Objekt hinzufügen. Finden Sie unter [Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) eine Liste der Assistenten, mit denen Objekte ATL-Projekt hinzu.  
  
> [!NOTE]
>  Der Assistent unterstützt keine ATL-Dialogfelder, XML-Webdienste mit ATL-Server, Leistungsobjekte und Leistungsindikatoren erstellt.  
  
 Ein verbindungsfähiges Objekt (d. h. eine Quelle) kann für jede seiner Ausgangsschnittstellen einen Verbindungspunkt verfügbar machen. Jede Ausgangsschnittstelle kann von einem Client auf ein Objekt (d. h. eine Senke) implementiert werden. Weitere Informationen finden Sie unter [ATL-Verbindungspunkte](../atl/atl-connection-points.md).  
  
### <a name="to-implement-a-connection-point"></a>Um einen Verbindungspunkt zu implementieren.  
  
1.  In der Klassenansicht mit der rechten Maustaste des Klassennamen für das ATL-Objekt.  
  
2.  Klicken Sie auf **hinzufügen** aus dem Kontextmenü, und klicken Sie dann auf **Verbindungspunkt hinzufügen** zum Anzeigen der [Assistent zum Implementieren von Verbindungspunkten](../ide/implement-connection-point-wizard.md).  
  
3.  Wählen Sie aus den entsprechenden Typbibliotheken implementiert, und klicken Sie auf die Verbindungsschnittstellen **Fertig stellen**.  
  
4.  Überprüfen Sie in der Klassenansicht den Webdienstproxy-Klassen, die für jeden Verbindungspunkt erstellt. Die Klassen werden als CProxy*Schnittstellenname*\<T > und abgeleitet sind [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md).  
  
5.  Doppelklicken Sie auf Connection Point-Klasse zum Anzeigen der Definition der Verbindungspunkt-Klasse.  
  
    -   Wenn Sie einen Verbindungspunkt für Ihr eigenes Projekt Schnittstelle implementieren, wird die folgende Definition angezeigt.  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         Wenn Sie eine lokale Schnittstelle implementieren, werden in die Klassendefinition der Methoden und Eigenschaften angezeigt.  
  
    -   Wenn Sie einen Verbindungspunkt für eine andere Schnittstelle implementieren, die Definition enthält die Methoden der Schnittstelle, denen vorangestellt wurde `Fire_`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen von Verbindungspunkten zu einem Objekt](../atl/adding-connection-points-to-an-object.md)