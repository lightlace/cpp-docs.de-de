---
title: "Hinzuf&#252;gen eines einfachen ATL-Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.classes.adding.atl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Objekten"
  - "ATL, Einfache Objekte"
  - "Objekte [ATL]"
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Hinzuf&#252;gen eines einfachen ATL-Objekts
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Damit Sie dem Projekt ein ATL \(Active Template Library\)\-Objekt hinzufügen können, ist es erforderlich, dass das Projekt als ATL\-Anwendung oder als MFC\-Anwendung mit integrierter ATL\-Unterstützung erstellt wurde.  Sie können den [ATL\-Projekt\-Assistenten](../../atl/reference/atl-project-wizard.md) verwenden, um eine ATL\-Anwendung zu erstellen, oder der [MFC\-Anwendung ein ATL\-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL\-Unterstützung in eine MFC\-Anwendung zu implementieren.  
  
 Sie können COM\-Schnittstellen für das neue ATL\-Objekt definieren, wenn dieses neu erstellt wird, oder später hinzufügen, indem Sie den Befehl [Schnittstelle implementieren](../../ide/implement-interface-wizard.md) im Kontextmenü der Klassenansicht verwenden.  
  
### So fügen Sie einem ATL COM\-Projekt ein einfaches ATL\-Objekt hinzu  
  
1.  Klicken Sie entweder im **Projektmappen\-Explorer** oder in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Namen des Projekts, dem Sie das einfache ATL\-Objekt hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
3.  Klicken Sie im Bereich "Vorlagen" des Dialogfelds [Klasse hinzufügen](../../ide/add-class-dialog-box.md) zunächst auf **Einfaches ATL\-Objekt** und dann auf **Öffnen**, um den [ATL\-Assistenten für einfache Objekte](../../atl/reference/atl-simple-object-wizard.md) aufzurufen.  
  
4.  Legen Sie auf der Seite [Optionen](../../atl/reference/options-atl-simple-object-wizard.md) des ATL\-Assistenten für einfache Objekte zusätzliche Optionen für das Projekt fest.  
  
5.  Klicken Sie auf **Fertig stellen**, um dem Projekt das Objekt hinzuzufügen.  
  
## Siehe auch  
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer neuen Schnittstelle in einem ATL\-Projekt](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)   
 [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md)   
 [Hinzufügen einer Methode](../../ide/adding-a-method-visual-cpp.md)   
 [MFC\-Klasse](../../mfc/reference/adding-an-mfc-class.md)   
 [Hinzufügen einer generischen C\+\+\-Klasse](../../ide/adding-a-generic-cpp-class.md)