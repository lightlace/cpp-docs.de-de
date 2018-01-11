---
title: Ereignishandler-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.eventhandler.overview
dev_langs: C++
helpviewer_keywords: Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ccb80add8a98b9251a7ccbb5c85bf98b610a22e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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