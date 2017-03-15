---
title: "ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern | Microsoft Docs"
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
  - "ActiveX-Steuerelementcontainer [C++], Aktivieren"
  - "ActiveX-Steuerelemente [C++], Aktivieren von Containern"
  - "AfxEnableControlContainer-Methode"
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ActiveX-Steuerelementcontainer: Manuelles Aktivieren von ActiveX-Steuerelementcontainern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie nicht ActiveX\-Steuerelement\-Unterstützung haben, als Sie den MFC\-Anwendungs\-Assistenten verwenden, um die Anwendung zu generieren, müssen Sie diese Unterstützung manuell hinzufügen.  Dieser Artikel beschreibt den Prozess für ActiveX\-Steuerelement\-Kapselung zu einer vorhandenen OLE\-Containeranwendung manuell hinzufügen.  Wenn Sie bereits im Voraus wissen, dass Sie ActiveX\-Steuerelement\-Unterstützung im OLE\-Container möchten, finden Sie im Artikel [Erstellen eines MFC\-ActiveX\-Steuerelement\-Containers](../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
> [!NOTE]
>  Dieser Artikel wird ein auf Dialogfeldern basierenden ActiveX\-Steuerelementcontainer Projekt benannten Container ein eingebettetes Steuerelement, das Circ als Beispiele in den Prozeduren und im Code ".  
  
 Um ActiveX\-Steuerelemente zu unterstützen, müssen Sie eine Codezeile zwei der Dateien des Projekts hinzufügen.  
  
-   Ändern Sie `InitInstance`\-Funktion des Hauptdialogfelds gefunden \(in CONTAINER.CPP\) durch den MFC\-Anwendungs\-Assistenten, der [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md), wie im folgenden Beispiel ein Aufruf ausführt:  
  
     [!CODE [NVC_MFCOleContainer#34](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOleContainer#34)]  
    [!CODE [NVC_MFCOleContainer#35](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOleContainer#35)]  
  
-   Fügen Sie das folgende STDAFX.H\-Headerdatei das des Projekts hinzu:  
  
     [!CODE [NVC_MFCOleContainer#36](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOleContainer#36)]  
  
 Nachdem Sie diese Schritte abgeschlossen haben, erstellen Sie das Projekt neu indem Sie im Menü **Erstellen** auf **Erstellen** klicken.  
  
## Siehe auch  
 [ActiveX\-Steuerelementcontainer](../mfc/activex-control-containers.md)