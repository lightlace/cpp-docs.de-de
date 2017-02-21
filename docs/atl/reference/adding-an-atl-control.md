---
title: "Hinzuf&#252;gen eines ATL-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Steuerelementen"
  - "Steuerelemente [ATL], Hinzufügen zu Projekten"
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Hinzuf&#252;gen eines ATL-Steuerelements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mithilfe dieses Assistenten können Sie einem Projekt, das Schnittstellen für alle möglichen Container unterstützt, ein Benutzeroberflächenobjekt hinzufügen.  Damit diese Schnittstellen unterstützt werden, ist es erforderlich, dass das Projekt als ATL\-Anwendung oder als MFC\-Anwendung mit integrierter ATL\-Unterstützung erstellt wurde.  Sie können den [ATL\-Projekt\-Assistenten](../../atl/reference/atl-project-wizard.md) verwenden, um eine ATL\-Anwendung zu erstellen, oder der [MFC\-Anwendung ein ATL\-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL\-Unterstützung in eine MFC\-Anwendung zu implementieren.  
  
### So fügen Sie dem Projekt ein ATL\-Steuerelement hinzu  
  
1.  Klicken Sie entweder im **Projektmappen\-Explorer** oder in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Namen des Projekts, dem Sie das einfache ATL\-Objekt hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
3.  Klicken Sie im Dialogfeld [Klasse hinzufügen](../../ide/add-class-dialog-box.md) im Vorlagenbereich zunächst auf **ATL\-Steuerelement** und dann auf **Hinzufügen**, um den [ATL\-Steuerelement\-Assistenten](../../atl/reference/atl-control-wizard.md) aufzurufen.  
  
 Mithilfe des **ATL\-Steuerelement\-Assistenten** können drei Arten von Steuerelementen erstellt werden:  
  
-   Standardsteuerelemente  
  
-   Zusammengesetzte Steuerelemente  
  
-   DHTML\-Steuerelemente  
  
 Darüber hinaus können Sie die Größe des Steuerelements verringern und Schnittstellen entfernen, die von den meisten Containern nicht verwendet werden. Sie wählen dazu auf der Seite **Optionen** des Assistenten die Option **Minimal\-Steuerelement**.  
  
## Siehe auch  
 [Adding Functionality to the Composite Control](../../atl/adding-functionality-to-the-composite-control.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATLFire Sample](assetId:///5b2649f1-f45b-4cfb-9c4b-4d9459c26b09)