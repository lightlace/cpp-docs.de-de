---
title: "Implementierungsstrategien"
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
  - "VSPackages, Implementierungsstrategien"
ms.assetid: f5512d4e-666d-4934-bd42-9718fd7e4c06
caps.latest.revision: 23
caps.handback.revision: "23"
manager: "douge"
---
# Implementierungsstrategien
Sie können Visual Studio mit Automatisierungs\-Add\-Ins, VSPackages, MEF\-Komponenten \(Managed Extensibility Framework\) oder mit einer Kombination der drei Optionen erweitern. Add\-Ins sind im Allgemeinen einfacher zu entwickeln, aber weniger leistungsfähig als VSPackages oder MEF\-Komponenten. Add\-Ins können Erweiterungsschnittstellen aufrufen, während VSPackages und MEF\-Komponenten auf das Visual Studio\-Automatisierungsmodell zugreifen können. Sie können verschiedene unterschiedliche Ansätze zum Erstellen einer effektiven Lösung kombinieren.  
  
 VSPackages können in nicht verwaltetem oder verwaltetem Code geschrieben werden. Es wird empfohlen, dass Sie neue VSPackages mithilfe des Managed Package Framework \(MPF\) in verwaltetem Code schreiben. Fast alles, das in nicht verwaltetem Code geschrieben werden kann, kann einfacher und sicherer in verwaltetem Code implementiert werden. In nicht verwaltetem Code geschriebene Legacyanwendungen können jedoch weiterhin in Visual Studio ausgeführt werden.  
  
 Einfache Erweiterungen können Toolfenster hinzufügen oder Informationen an UI\-Elemente von Visual Studio senden, z. B. an die Statusleiste oder das Ausgabefenster. Komplexere Anwendungen können als Visual Studio\-Hierarchien geschrieben werden, z. B. der Server\-Explorer. Wenn Sie ein Projekt, einen Editor oder einen Designer implementieren, erhalten Sie noch mehr Leistung.[!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] und [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] wurden z. B. selbst als Sprachdienste implementiert.  
  
## Verwandte Abschnitte  
 [Visual Studio SDK und Automatisierung](../Topic/Visual%20Studio%20SDK%20and%20Automation.md)  
 Erläutert die Verwendung von Automatisierung, VSPackages oder einer Kombination aus beidem zum Erstellen von Visual Studio\-Erweiterbarkeitsanwendungen.  
  
 [Visual Studio SDK und verwalteter Code](../misc/visual-studio-sdk-and-managed-code.md)  
 Vergleicht die verschiedenen Möglichkeiten, wie Sie ein VSPackage in verwaltetem Code schreiben können.  
  
 [Visual Studio\-IDE\-Konzepte](../misc/visual-studio-ide-concepts.md)  
 Erläutert die Grundlagen von VSPackages sowie die Verwendung eines Diensts.  
  
 [Erweitern von anderen Teilen von Visual Studio](../Topic/Extending%20Other%20Parts%20of%20Visual%20Studio.md)  
 Erläutert allgemeine Anwendungselemente der Benutzeroberfläche in Visual Studio, z. B. Status\- und Ausgabefenster.  
  
 [Hierarchien in Visual Studio](../Topic/Hierarchies%20in%20Visual%20Studio.md)  
 Bietet eine Übersicht über Visual Studio\-Hierarchien, die in der integrierten Entwicklungsumgebung \(IDE\) als Strukturen von Knoten angezeigt werden.  
  
 [Projekte](../Topic/Projects.md)  
 Bietet eine Übersicht über Projekt\- und Projektmappenklassen.  
  
 [\-Editor, und Language Service Extensions](../Topic/Editor%20and%20Language%20Service%20Extensions.md)  
 Veranschaulicht die Erweiterung von Code\- und Text\-Editor sowie die Erstellung benutzerdefinierter Editoren und Designer.  
  
 [Ältere Sprache Service\-Erweiterbarkeit](../Topic/Legacy%20Language%20Service%20Extensibility.md)  
 Veranschaulicht die Erstellung von Sprachdiensten.  
  
 [Visual Studio SDK\-Referenz](../Topic/Visual%20Studio%20SDK%20Reference.md)  
 Die Referenzdokumentation für VSSDK.  
  
## Siehe auch  
 [Starten Visual Studio\-Erweiterungen entwickeln](../Topic/Starting%20to%20Develop%20Visual%20Studio%20Extensions.md)