---
title: Befehlsrouting | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- handlers [MFC]
- handlers, command [MFC]
- command routing
ms.assetid: 9393a956-bdd4-47c5-9013-dbd680433f93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecb836f8fee1efab7f5f925c6ec3ce0f470d666b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346281"
---
# <a name="command-routing"></a>Befehlsrouting
Ihre Verantwortung bei der Arbeit mit Befehlen beschränkt sich auf das Erstellen von Meldungszuordnungsverbindungen zwischen Befehlen und ihren jeweiligen Handlerfunktionen, eine Aufgabe, für die Sie das Eigenschaftenfenster verwenden. Sie müssen außerdem die meisten Befehlshandler schreiben.  
  
 Windows-Meldungen werden in der Regel an das Hauptrahmenfenster gesendet, aber Befehlsmeldungen werden dann an andere Objekte weitergeleitet. Das Framework leitet Befehle durch eine Standardsequenz von Befehlszielobjekten, wobei vorausgesetzt wird, dass eines von ihnen einen Handler für den Befehl besitzt. Jedes Befehlszielobjekt überprüft seine Meldungszuordnung, um festzustellen, ob es die eingehende Meldung verarbeiten kann.  
  
 Verschiedene Befehlszielklassen überprüfen ihre eigenen Meldungszuordnungen zu unterschiedlichen Zeitpunkten. In der Regel leitet eine Klasse den Befehl an bestimmte andere Objekte weiter, um ihnen die erste Chance mit dem Befehl zu geben. Wenn keines dieser Objekte den Befehl verarbeitet, überprüft die ursprüngliche Klasse ihre eigene Meldungszuordnung. Wenn sie dann keinen Handler bereitstellen kann, kann sie den Befehl noch an weitere Befehlsziele leiten. Die Tabelle [Standardmäßige Befehlsweiterleitung](#_core_standard_command_route) unten zeigt, wie die einzelnen Klassen diese Sequenz strukturieren. Die allgemeine Reihenfolge, in der ein Befehlsziel einen Befehl weiterleitet, ist:  
  
1.  An sein derzeit aktives untergeordnetes Befehlszielobjekt.  
  
2.  An sich selbst.  
  
3.  An andere Befehlsziele.  
  
 Wie aufwändig dieser Weiterleitungsmechanismus Vergleich wie der Ereignishandler als Antwort auf einen Befehl erfolgt ist, ist die Kosten für das routing gering. Beachten Sie, dass das Framework nur dann Befehle generiert, wenn der Benutzer mit einem Benutzeroberflächenobjekt interagiert.  
  
### <a name="_core_standard_command_route"></a> Standardmäßige Befehlsweiterleitung  
  
|Wenn ein Objekt dieses Typs einen Befehl empfängt. sein. sein.|Es gibt sich selbst und anderen Befehlszielobjekten in der folgenden Reihenfolge eine Chance, den Befehl zu verarbeiten:|  
|----------------------------------------------------------|-----------------------------------------------------------------------------------------------------|  
|MDI-Rahmenfenster (`CMDIFrameWnd`)|1.  Aktive `CMDIChildWnd`<br />2.  Dieses Rahmenfenster<br />3.  Anwendung (`CWinApp` Objekt)|  
|Dokumentrahmenfenster (`CFrameWnd`, `CMDIChildWnd`)|1.  Aktive Ansicht<br />2.  Dieses Rahmenfenster<br />3.  Anwendung (`CWinApp` Objekt)|  
|Ansicht|1.  Diese Ansicht<br />2.  Der Ansicht angefügtes Dokument|  
|Dokument|1.  Dieses Dokument<br />2.  Dem Dokument angefügte Dokumentvorlage|  
|Dialogfeld|1.  Dieses Dialogfeld<br />2.  Fenster, das das Dialogfeld besitzt<br />3.  Anwendung (`CWinApp` Objekt)|  
  
 Wo nummerierte Einträge in der zweiten Spalte der vorstehenden Tabelle andere Objekte erwähnen, z. B. ein Dokument, finden Sie das entsprechende Element in der ersten Spalte. Wenn Sie z. B. in der zweiten Spalte lesen, dass die Sicht einen Befehl an sein Dokument weiterleitet, können Sie in der ersten Spalte im Eintrag „Dokument“ dem Routing weiter folgen.  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

