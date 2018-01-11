---
title: 'Vorgehensweise: Anzeigen von Befehlsinformationen in der Statusleiste | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da836f48592d97b3526c568eb9d9a830428f53a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Gewusst wie: Anzeigen von Befehlsinformationen in der Statusleiste
Beim Ausführen der Anwendung-Assistenten, um das Skelett Ihrer Anwendung zu erstellen, können Sie eine Symbolleiste und Statusleiste unterstützen. Nur eine Option im Anwendungs-Assistenten unterstützt. Bei eine Statusleiste vorhanden ist, gibt die Anwendung automatisch hilfreich Feedback, wenn der Benutzer den Zeiger über Elemente in den Menüs bewegt. Die Anwendung wird automatisch eine eingabeaufforderungs-Zeichenfolge in der Statusleiste angezeigt, wenn das Menüelement hervorgehoben ist. Beispielsweise, wenn der Benutzer den Mauszeiger über die **Ausschneiden** Befehl die **bearbeiten** im Menü die Statusleiste möglicherweise "Schneidet die Auswahl und fügt sie in der Zwischenablage" in den Bereich der Statusleiste angezeigt. Die Aufforderung hilft den Benutzer, die den Zweck des Menüelements kennen. Dies funktioniert auch, wenn der Benutzer eine Symbolleisten-Schaltfläche klickt.  
  
 Durch Definieren von eingabeaufforderungs-Zeichenfolgen für Menüelemente, die Sie, um das Programm hinzufügen kann dieser Hilfe Statusleiste hinzugefügt werden. Zu diesem Zweck geben Sie beim Bearbeiten der Eigenschaften des Menüelements im Menü-Editor die eingabeaufforderungs-Zeichenfolgen. Die Zeichenfolgen, die Sie definieren, werden in der Ressourcendatei für die Anwendung gespeichert. Sie haben die gleichen IDs wie die Befehle, die sie zu erläutern.  
  
 Standardmäßig fügt der Anwendungs-Assistent `AFX_IDS_IDLEMESSAGE`, die ID für eine standardmäßige "Bereit", der angezeigt wird, wenn das Programm auf neue Nachrichten wartet. Wenn Sie die Option kontextbezogene Hilfe im Anwendungs-Assistenten angeben, wird die Nachricht geändert auf "Hilfe, F1 drücken."  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

