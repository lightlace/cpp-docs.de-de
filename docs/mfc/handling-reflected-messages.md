---
title: "Behandeln von reflektierten Meldungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Meldungsbehandlung, Reflektierte Meldungen"
  - "Reflektierte Meldungen, Behandlung"
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Behandeln von reflektierten Meldungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Meldungsreflektion können Sie Meldungen für ein Steuerelement, z `WM_CTLCOLOR`, **WM\_COMMAND** und **WM\_NOTIFY**, selbst im Steuerelement bearbeiten.  Dadurch wird das Steuerelement in sich geschlossene portabel und erstellt.  Die Mechanismusarbeiten mit allgemeinen Windows\-Steuerelemente sowie mit ActiveX\-Steuerelementen \(zuvor aufgerufen OLE\-Steuerelemente\).  
  
 Meldungsreflektion können Sie das `CWnd` diese wiederverwenden abgeleitete Klassen.  Meldungsreflektionsarbeiten über [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md), Sie mit speziellen **ON\_XXX\_REFLECT** Meldungszuordnungseinträge: beispielsweise **ON\_CTLCOLOR\_REFLECT** und **ON\_CONTROL\_REFLECT**.  [Technischer Hinweis 62](../mfc/tn062-message-reflection-for-windows-controls.md) erläutert Meldungsreflektion ausführlicher beschrieben.  
  
## Was möchten Sie tun?  
  
-   [Vertrautmachen Meldungsreflektion](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implementieren Sie Meldungsreflektion für eine sehr häufig vorkommende Steuerelement](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implementieren Sie Meldungsreflektion eines ActiveX\-Steuerelements](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)