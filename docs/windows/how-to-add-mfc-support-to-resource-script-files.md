---
title: "How to: Add MFC Support to Resource Script Files | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.add.MFC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rc files, adding MFC support"
  - ".rc files, adding MFC support"
  - "MFC, adding support to resource scripts files"
  - "resource script files, adding MFC support"
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# How to: Add MFC Support to Resource Script Files
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine MFC\-Anwendung für Windows mit dem [MFC\-Anwendungs\-Assistenten](../mfc/reference/mfc-application-wizard.md) erstellen, generiert der Assistent normalerweise eine Reihe grundlegender Dateien \(einschließlich einer Ressourcenskriptdatei \(.rc\)\), die die Kernfeatures von MFC \(Microsoft Foundation Classes\) enthalten.  Wenn Sie jedoch eine RC\-Datei für eine Windows\-Anwendung bearbeiten, die nicht auf MFC basiert, sind die folgenden, für die MFC\-Grundstruktur spezifischen Features nicht verfügbar:  
  
-   MFC\-Code\-Assistenten \(zuvor "[MFC\-Klassen\-Assistenten](assetId:///98dc2434-ba93-4e0b-b084-1a4bc26cdf1e)" genannt\)  
  
-   Zeichenfolgen für Menüaufforderungen  
  
-   Auflisten der Inhalte von Kombinationsfeld\-Steuerelementen  
  
-   Hosting von ActiveX\-Steuerelementen  
  
 Vorhandenen RC\-Dateien, die noch nicht über MFC\-Unterstützung verfügen, kann diese jedoch hinzugefügt werden.  
  
### So fügen Sie RC\-Dateien MFC\-Unterstützung hinzu  
  
1.  Öffnen Sie die Ressourcenskriptdatei.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Markieren Sie in der [Ressourcenansicht](../windows/resource-view-window.md) den Ressourcenordner \(z. B. MFC.rc\).  
  
3.  Legen Sie die [MFC Mode](../Topic/Properties%20Window.md)\-Eigenschaft im **Eigenschaftenfenster** auf **True** fest.  
  
    > [!NOTE]
    >  Zusätzlich zum Festlegen dieses Flags muss auch gewährleistet sein, dass die RC\-Datei Teil eines MFC\-Projekts ist.  Wenn Sie **MFC Mode** für eine RC\-Datei in einem Win32\-Projekt lediglich auf **True** festlegen, sind keine MFC\-Features verfügbar.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 MFC  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)