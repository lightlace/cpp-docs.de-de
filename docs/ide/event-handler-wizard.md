---
title: Ereignishandler-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 544ce4cd0f4ed9a7f3592e5ec1691fb3734b8772
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="event-handler-wizard"></a>Ereignishandler-Assistent
Dieser Assistent fügt einen Ereignishandler für ein Dialogfeld-Steuerelement auf die Klasse Ihrer Wahl. Wenn Sie einen Ereignishandler hinzufügen der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), Sie können nur für das Dialogfeld zu implementierenden Klasse hinzufügen. Finden Sie unter [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md) für Weitere Informationen.  
  
 **Befehlsname**  
 Bezeichnet das ausgewählte Steuerelement, für das der Ereignishandler hinzugefügt wird. Dieses Feld ist nicht verfügbar.  
  
 **Nachrichtentyp**  
 Zeigt die Liste der aktuellen möglich Meldungshandler für das ausgewählte Steuerelement.  
  
 **Handler-Funktionsnamen**  
 Zeigt den Namen der Funktion, die hinzugefügt wird, für die Ereignisbehandlung. Wird standardmäßig der Name des Nachrichtentyps und der Befehl, durch "On" vorangestellt basiert. Angenommen, für die Schaltfläche namens `IDC_BUTTON1`, den Nachrichtentyp `BN_CLICKED` zeigt den Namen der Funktion Handler `OnBnClickedButton1`.  
  
 **Klassenliste**  
 Zeigt die verfügbare Klassen, die Sie einen Ereignishandler hinzufügen können. Die Klasse für das ausgewählte Dialogfeld wird rot angezeigt.  
  
 **Handler-Beschreibung**  
 Enthält eine Beschreibung für das ausgewählte Element im die **Nachrichtentyp** Feld. Dieses Feld ist nicht verfügbar.  
  
 **Hinzufügen und bearbeiten**  
 Die ausgewählte Klasse oder das Objekt den Message-Handler hinzugefügt, und öffnet dann die Text-Editor an die neue Funktion, damit Sie das Steuerelement Benachrichtigung Ereignishandler Code hinzufügen können.  
  
 **Bearbeiten von code**  
 Öffnet den Text-Editor der ausgewählten vorhandenen Funktion hinzufügen oder Code des Steuerelements Benachrichtigung bearbeiten zu können.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md)