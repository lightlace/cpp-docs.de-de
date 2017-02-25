---
title: "Erstellen eines MFC-ActiveX-Steuerelementcontainers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.activex.container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelementcontainer [C++], Erstellen"
  - "Container [C++], Erstellen"
  - "MFC ActiveX-Steuerelemente [C++], Container"
  - "OLE-Steuerelemente [C++], Container"
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Erstellen eines MFC-ActiveX-Steuerelementcontainers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein ActiveX\-Steuerelementcontainer ist ein übergeordnetes Programm, das die Umgebung zur Verfügung stellt, in der ein ActiveX\-Steuerelement \(früher OLE\) ausgeführt werden kann.  Sie können eine Anwendung, die ActiveX\-Steuerelemente unterstützt, mit oder ohne MFC erstellen; mit MFC ist es allerdings einfacher.  
  
 Wenn Sie ein MFC\-Containerprogramm mithilfe des [MFC\-Anwendungs\-Assistenten](../../mfc/reference/mfc-application-wizard.md) erstellen, haben Sie Zugriff auf die zahlreichen Features der ActiveX\-Steuerelemente und der Automatisierung, die durch die MFC\- und ActiveX\-Klassen implementiert werden.  Zu diesen Features gehören die visuelle Bearbeitung, die Automatisierung, das Erstellen von Verbunddateien sowie die Unterstützung von Steuerelementen.  Zu den visuellen Bearbeitungsoptionen des MFC\-Anwendungs\-Assistenten, die vom übergeordneten Programm unterstützt werden, gehören das Erstellen eines Containers, eines Miniservers, eines Vollservers sowie eines Programms, das sowohl Container als auch Server ist.  
  
-   **Neue MFC\-Anwendung**.  Um ein neues MFC\-Programm zu erstellen, das Automatisierung, visuelle Bearbeitung, Verbunddateien oder Steuerelementunterstützung umfasst, verwenden Sie den MFC\-Anwendungs\-Assistenten und wählen die geeigneten Automatisierungsoptionen aus.  
  
-   **Vorhandene MFC\-Anwendung**.  Wenn Sie einer bereits vorhandenen MFC\-Anwendung die Unterstützung von Steuerelementcontainern hinzufügen möchten, finden Sie weitere Informationen unter [OLE\-Steuerelementcontainer: Manuelles Aktivieren der OLE\-Steuerelementkapselung](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).  
  
### So erstellen Sie einen ActiveX\-Container für beliebige der folgenden Anwendungstypen  
  
1.  [Container](../../mfc/containers.md)  
  
2.  [Visuelle Bearbeitung](../../mfc/ole-mfc.md)  
  
3.  [MFC\-ActiveX\-Steuerelemente](../../mfc/mfc-activex-controls.md)  
  
## Siehe auch  
 [Visual C\+\+\-Projekttypen](../../ide/visual-cpp-project-types.md)