---
title: "Befehlsrouting | Microsoft Docs"
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
  - "MFC, Befehlsrouting"
  - "Behandlung von Befehlen, Routing von Befehlen"
  - "Handler"
  - "Handler, Befehl"
  - "Befehlsrouting"
ms.assetid: 9393a956-bdd4-47c5-9013-dbd680433f93
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Befehlsrouting
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ihre Verantwortung bei der Arbeit mit Befehlen beschränkt sich auf das Erstellen von Meldungszuordnungsverbindungen zwischen Befehlen und ihren jeweiligen Handlerfunktionen, eine Aufgabe, für die Sie das Eigenschaftenfenster verwenden. Sie müssen außerdem die meisten Befehlshandler schreiben.  
  
 Windows\-Meldungen werden in der Regel an das Hauptrahmenfenster gesendet, aber Befehlsmeldungen werden dann an andere Objekte weitergeleitet. Das Framework leitet Befehle durch eine Standardsequenz von Befehlszielobjekten, wobei vorausgesetzt wird, dass eines von ihnen einen Handler für den Befehl besitzt. Jedes Befehlszielobjekt überprüft seine Meldungszuordnung, um festzustellen, ob es die eingehende Meldung verarbeiten kann.  
  
 Verschiedene Befehlszielklassen überprüfen ihre eigenen Meldungszuordnungen zu unterschiedlichen Zeitpunkten. In der Regel leitet eine Klasse den Befehl an bestimmte andere Objekte weiter, um ihnen die erste Chance mit dem Befehl zu geben. Wenn keines dieser Objekte den Befehl verarbeitet, überprüft die ursprüngliche Klasse ihre eigene Meldungszuordnung. Wenn sie dann keinen Handler bereitstellen kann, kann sie den Befehl noch an weitere Befehlsziele leiten. Die Tabelle [Standardmäßige Befehlsweiterleitung](#_core_standard_command_route) unten zeigt, wie die einzelnen Klassen diese Sequenz strukturieren. Die allgemeine Reihenfolge, in der ein Befehlsziel einen Befehl weiterleitet, ist:  
  
1.  An sein derzeit aktives untergeordnetes Befehlszielobjekt.  
  
2.  An sich selbst.  
  
3.  An andere Befehlsziele.  
  
 Wie aufwändig ist dieser Weiterleitungsmechanismus? Im Vergleich zu dem, was der Handler als Reaktion auf einen Befehl ausführt, ist der Aufwand für das Routing gering. Beachten Sie, dass das Framework nur dann Befehle generiert, wenn der Benutzer mit einem Benutzeroberflächenobjekt interagiert.  
  
### Standardmäßige Befehlsweiterleitung  
  
|Wenn ein Objekt dieses Typs einen Befehl empfängt. . .|Es gibt sich selbst und anderen Befehlszielobjekten in der folgenden Reihenfolge eine Chance, den Befehl zu verarbeiten:|  
|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|  
|MDI\-Rahmenfenster \(`CMDIFrameWnd`\)|1.  Aktiver `CMDIChildWnd`<br />2.  Dieses Rahmenfenster<br />3.  Anwendung \(`CWinApp`\-Objekt\)|  
|Dokumentrahmenfenster \(`CFrameWnd`, `CMDIChildWnd`\)|1.  Aktive Ansicht<br />2.  Dieses Rahmenfenster<br />3.  Anwendung \(`CWinApp`\-Objekt\)|  
|Ansicht|1.  Diese Ansicht<br />2.  Der Ansicht angefügtes Dokument|  
|Dokument|1.  Dieses Dokument<br />2.  Dem Dokument angefügte Dokumentvorlage|  
|Dialogfeld|1.  Dieses Dialogfeld<br />2.  Fenster, das das Dialogfeld besitzt<br />3.  Anwendung \(`CWinApp`\-Objekt\)|  
  
 Wo nummerierte Einträge in der zweiten Spalte der vorstehenden Tabelle andere Objekte erwähnen, z. B. ein Dokument, finden Sie das entsprechende Element in der ersten Spalte. Wenn Sie z. B. in der zweiten Spalte lesen, dass die Sicht einen Befehl an sein Dokument weiterleitet, können Sie in der ersten Spalte im Eintrag „Dokument“ dem Routing weiter folgen.  
  
## Siehe auch  
 [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)