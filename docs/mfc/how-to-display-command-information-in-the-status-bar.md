---
title: 'Vorgehensweise: Anzeigen von Befehlsinformationen in der Statusleiste | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 440e550e6e1ba5a82cac3f35dcb3c76b346b5343
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346044"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Gewusst wie: Anzeigen von Befehlsinformationen in der Statusleiste
Beim Ausführen der Anwendung-Assistenten, um das Skelett Ihrer Anwendung zu erstellen, können Sie eine Symbolleiste und Statusleiste unterstützen. Nur eine Option im Anwendungs-Assistenten unterstützt. Bei eine Statusleiste vorhanden ist, gibt die Anwendung automatisch hilfreich Feedback, wenn der Benutzer den Zeiger über Elemente in den Menüs bewegt. Die Anwendung wird automatisch eine eingabeaufforderungs-Zeichenfolge in der Statusleiste angezeigt, wenn das Menüelement hervorgehoben ist. Beispielsweise, wenn der Benutzer den Mauszeiger über die **Ausschneiden** Befehl die **bearbeiten** im Menü die Statusleiste möglicherweise "Schneidet die Auswahl und fügt sie in der Zwischenablage" in den Bereich der Statusleiste angezeigt. Die Aufforderung hilft den Benutzer, die den Zweck des Menüelements kennen. Dies funktioniert auch, wenn der Benutzer eine Symbolleisten-Schaltfläche klickt.  
  
 Durch Definieren von eingabeaufforderungs-Zeichenfolgen für Menüelemente, die Sie, um das Programm hinzufügen kann dieser Hilfe Statusleiste hinzugefügt werden. Zu diesem Zweck geben Sie beim Bearbeiten der Eigenschaften des Menüelements im Menü-Editor die eingabeaufforderungs-Zeichenfolgen. Die Zeichenfolgen, die Sie definieren, werden in der Ressourcendatei für die Anwendung gespeichert. Sie haben die gleichen IDs wie die Befehle, die sie zu erläutern.  
  
 Standardmäßig fügt der Anwendungs-Assistent `AFX_IDS_IDLEMESSAGE`, die ID für eine standardmäßige "Bereit", der angezeigt wird, wenn das Programm auf neue Nachrichten wartet. Wenn Sie die Option kontextbezogene Hilfe im Anwendungs-Assistenten angeben, wird die Nachricht geändert auf "Hilfe, F1 drücken."  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

