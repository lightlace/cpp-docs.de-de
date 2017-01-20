---
title: "VSPackage-Status"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Status, VSPackages"
  - "VSPackages, Anwendungszustand verwalten"
  - "Statuspersistenz"
ms.assetid: 6056a9ea-e7a8-481c-9fc8-340229fa12d9
caps.latest.revision: 25
caps.handback.revision: "25"
manager: "douge"
---
# VSPackage-Status
Viele Faktoren bestimmen den Satz von Werten oder beibehaltenen Zustand einer [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Anwendung.  
  
-   Projekte und Projekte Konfigurationseigenschaften.  
  
-   Projektmappen haben Eigenschaften.  
  
-   Benutzereinstellungen bestimmen die Größe und die Position von Dokumentfenstern, von Toolfenstern, angedocktem Zustand und Tastenkombinationen.  
  
-   Anwendungen können Optionen verfügen über dieses Benutzers eines legt diesen fest.  
  
-   Objekte, die eine Anwendung erstellt wird, können die Eigenschaften von ihren eigenen haben.  
  
 Im Folgenden sind einige der Methoden, die einem [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Anwendungszustand verwaltet werden kann:  
  
-   Die Eigenschaftenseiten Projekte und Projektmappen.  
  
-   Durch **Assistent zum Importieren und Exportieren von Einstellungen**, das dem Benutzer ermöglicht, Einstellungen von einem Computer zu einem anderen zu verschieben.  
  
-   Durch das **Optionen** das Dialogfeld Optionen einschließt, die für Anwendungen verknüpft sind.  
  
-   Durch das **Eigenschaften** das Fenster Eigenschaften von Objekten verfügbar macht.  
  
-   Die Automatisierung.  Eine Anwendung kann einem VSPackage und Objekteigenschaften zugreifen, die sich auf die Automatisierung verfügbar gemacht wurden.  
  
 Zugrund zugrunde liegenden der Anwendungszustand verschiedene Mechanismen, die den permanenten Speicher gespeichert und wiederhergestellt worden Anwendungszustand kann.  
  
## In diesem Abschnitt  
 [Unterstützung von Statuspersistenz](../misc/support-for-state-persistence.md)  
 Führt allgemeine Strategien zum Speichern und Wiederherstellen, das Zurücksetzen des Zustands von VSPackages auf.  
  
 [Optionen und Optionen \(Seiten\)](../Topic/Options%20and%20Options%20Pages.md)  
 Stellt die allgemeinen und benutzerdefinierten Optionsseiten vor und erläutert, wie sie implementiert.  
  
 [Erstellen eine Optionsseite](../Topic/Creating%20an%20Options%20Page.md)  
 Erklärt, wie zwei Optionsseiten eine einfache Seite und eine benutzerdefinierte Seite erstellt.  
  
 [Unterstützung für Einstellungskategorien](../misc/support-for-settings-categories.md)  
 Erläutert die Benutzereinstellungen und wie sie erstellt und erhalten bleiben.  
  
 [Erstellen einer Einstellungskategorie](../Topic/Creating%20a%20Settings%20Category.md)  
 Erläutert, wie eine [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Einstellungskategorie erstellt und verwendet, um Werte zu speichern und Werte aus einer Einstellungsdatei wiederherzustellen.  
  
 [Erweitern von Eigenschaften und das Eigenschaftenfenster](../Topic/Extending%20Properties%20and%20the%20Property%20Window.md)  
 Erläutert, wie Sie den Wert eines Objekts im **Eigenschaften** Fenster angezeigt und geändert werden.  
  
 [Verfügbarmachen von Eigenschaften im Eigenschaftenfenster](../Topic/Exposing%20Properties%20to%20the%20Properties%20Window.md)  
 Erläutert, wie die öffentlichen Eigenschaften eines Objekts in den **Eigenschaften** Fenster verfügbar macht.  
  
 [Unterstützung für Projekt\- und Konfigurationseigenschaften](../Topic/Support%20for%20Project%20and%20Configuration%20Properties.md)  
 Erklärt, wie Projekt\- und Konfigurationseigenschaften angezeigt und geändert werden.  
  
 [Abrufen von Projekteigenschaften](../Topic/Getting%20Project%20Properties.md)  
 Führt Sie durch die Schritte zum Erstellen eines verwalteten VSPackages, die Projekteigenschaften in einem Toolfenster angezeigt wird.  
  
 [Verwenden die Einstellungen speichern](../Topic/Using%20the%20Settings%20Store.md)  
 Beschreibt den Mechanismus zur Einstellungs\-Speicher Dauerhaftigkeit und wie sie verwendet.  
  
## Verwandte Abschnitte  
 [VSPackages](../Topic/VSPackages.md)  
 Stellt ein Leitbild zu Themen, in denen erläutert wird, wie VSPackages erstellt und verwendet.