---
title: "Eigenschaftenseite f&#252;r benutzerdefinierten Buildschritt: Allgemein | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCustomBuildStep.AdditionalInputs"
  - "VC.Project.VCCustomBuildStep.CustomBuildAfterTargets"
  - "VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets"
  - "VC.Project.VCCustomBuildStep.Outputs"
  - "VC.Project.VCCustomBuildStep.Message"
  - "VC.Project.VCCustomBuildStep.Command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Projekteigenschaften, benutzerdefinierte Buildschritt"
  - "Benutzerdefinierter Buildschritt (allgemein)"
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Eigenschaftenseite f&#252;r benutzerdefinierten Buildschritt: Allgemein
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für jede Kombination von Projektkonfiguration und Zielplattform im Projekt können Sie einen benutzerdefinierten Schritt angeben, der ausgeführt werden muss, wenn das Projekt erstellt wird.  
  
## UIElement-Liste  
 **Befehlszeile**  
 Der vom benutzerdefinierten Buildschritt auszuführende Befehl.  
  
 **Beschreibung**  
 Eine Meldung, die anzeigt, wann der benutzerdefinierte Buildschritt läuft.  
  
 **Outputs**  
 Die Ausgabedatei, die der benutzerdefinierte Buildschritt generiert.  Diese Einstellung ist erforderlich, damit inkrementelle Builds ordnungsgemäß funktionieren.  
  
 **Zusätzliche Abhängigkeiten**  
 Eine durch Semikolons getrennte Liste von zusätzlichen Eingabedateien, die für den benutzerdefinierten Buildschritt verwendet werden soll.  
  
 **Im Anschluss ausführen und vorher ausführen**  
 Diese Optionen definieren, wann ein benutzerdefinierter Buildschritt im Buildprozess relativ zu den aufgelisteten Zielen ausgeführt wird.  Die am häufigste aufgelisteten Ziele sind BuildGenerateSources, BuildCompile und BuildLink, da sie die Hauptschritte im Buildprozess darstellen.  Andere oft aufgelisteten Ziele sind Midl, CLCompile und Link.  
  
 Ausgabe als Inhalt behandeln  
 Diese Option ist nur bei Windows Store oder Windows Phone\-Apps von Bedeutung, bei denen alle Inhaltsdateien im APPX\-Paket enthalten sind.  
  
### So legen Sie einen benutzerdefinierten Buildschritt fest  
  
1.  Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md).  
  
2.  Navigieren Sie im Dialogfeld **Eigenschaftenseiten** zur Seite **Konfigurationseigenschaften**, **Benutzerdefinierter Buildschritt**, **Allgemein**.  
  
3.  Ändern Sie die Einstellungen.  
  
## Siehe auch  
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)