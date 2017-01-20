---
title: "Gewusst wie: Hinzuf&#252;gen von Vorlagen zum Dialogfeld „Neues Projekt“"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Dialogfelder, Vorlagen zum Projekt hinzufügen"
  - "Projekte [Visual Studio SDK], Vorlagen zum Dialogfeld hinzufügen"
  - "Vorlagen [Visual Studio], zum Projektdialogfeld hinzufügen"
ms.assetid: fd044681-e666-410d-815c-33db923ed888
caps.latest.revision: 26
caps.handback.revision: "26"
manager: "douge"
---
# Gewusst wie: Hinzuf&#252;gen von Vorlagen zum Dialogfeld „Neues Projekt“
Während der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Installation werden eine Reihe vordefinierter Projekt\- und Elementvorlagen installiert. Eine vollständige Liste der vordefinierten Projektvorlagen finden Sie unter [NIB Erstellen von Projekten aus Vorlagen](assetId:///7c36d86a-6b79-4480-8228-0f925f1204b2). Zusätzlich zu den Standardprojektvorlagen können Sie benutzerdefinierte oder untertypspezifische Projektvorlagen erstellen. Der Untertyp **Intelligentes Gerät** verfügt z. B. über eigene Vorlagen für [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)]\- und [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\-Projekte. Anweisungen zum Erstellen einer benutzerdefinierten Vorlage finden Sie unter [Gewusst wie: Erstellen von Projektvorlagen](../Topic/How%20to:%20Create%20Project%20Templates.md).  
  
## Hinzufügen von Vorlagen zum Dialogfeld „Neues Projekt“  
  
#### So fügen Sie eine Vorlage zum Dialogfeld „Neues Projekt“ hinzu  
  
1.  Erstellen Sie eine Vorlage einschließlich der Datei „MyTemplate.vstemplate“.  
  
2.  Wählen Sie die Dateien in der Vorlage aus \(einschließlich der VSTEMPLATE\-Datei\), klicken Sie mit der rechten Maustaste auf die Auswahl, klicken Sie auf **Senden an**, und klicken Sie dann auf **ZIP\-komprimierten Ordner**. Die zuvor extrahierten Dateien werden in einer ZIP\-Datei komprimiert.  
  
 Speichern Sie die ZIP\-Vorlagendatei in **%USERPROFILE%\\Documents\\Visual Studio 2015\\Templates\\ProjectTemplates**.  
  
## Siehe auch  
 [Project Subtypes](d235b47b-cf11-4d47-a63f-e33d9d16105d2044a030-0795-4940-bd65-a6e44de98a0f)   
 [NIB: Visual Studio\-Vorlagen](assetId:///141fccaa-d68f-4155-822b-27f35dd94041)   
 [Zu den im Dialogfeld Neues Element hinzufügen](../Topic/Contributing%20to%20the%20Add%20New%20Item%20Dialog%20Box.md)