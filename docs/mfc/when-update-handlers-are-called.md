---
title: Update-Ereignishandler werden aufgerufen, wenn | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d899d9952ae13b23121fb0b7a188f8136315c342
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="when-update-handlers-are-called"></a>Wann müssen Updatehandler aufgerufen werden?
Angenommen, das der Benutzer klickt der Maus auf das Menü Datei auf dem generiert eine `WM_INITMENUPOPUP` Nachricht. Das Framework Aktualisierungsmechanismus aktualisiert alle Elemente im Menü Datei zusammen, bevor das Dropdownmenü, damit der Benutzer sie anzeigen kann.  
  
 Zu diesem Zweck aktualisieren die Framework-Routen Befehle für alle Menüelemente im Popupmenü entlang des standardbefehlsroutings. Befehlsziele auf das routing haben die Möglichkeit, alle Menüelemente zu aktualisieren, indem Sie den Updatebefehl mit einer entsprechenden Meldungszuordnungseintrags entsprechen (im Format `ON_UPDATE_COMMAND_UI`) und Aufrufen einer Funktion "updatehandler". Daher sind für ein Menü mit sechs Menüelementen sechs Update-Befehle gesendet. Wenn ein Aktualisierungshandler für die Befehls-ID des Menüelements vorhanden ist, wird sie aufgerufen, um die Aktualisierung durchzuführen. Wenn dies nicht der Fall, das Framework überprüft das Vorhandensein von einem Handler für dieses Befehls-ID und aktiviert oder deaktiviert das Menüelement nach Bedarf.  
  
 Wenn das Framework keine findet eine `ON_UPDATE_COMMAND_UI` -Eintrag bei Befehlsrouting automatisch Dadurch werden die Benutzeroberflächen-Objekt befindet sich ein `ON_COMMAND` Eintrag an einer beliebigen Stelle mit der gleichen Befehls-ID. Andernfalls wird der Benutzeroberflächen-Objekt deaktiviert. Aus diesem Grund um sicherzustellen, dass ein Objekt der Benutzeroberfläche aktiviert ist, geben Sie einen Handler für den Befehl, den das Objekt generiert wird, oder geben Sie einen updatehandler dafür. Siehe Abbildung im Thema [Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md).  
  
 Es ist möglich, deaktivieren standardmäßig zu deaktivieren, Benutzeroberflächen-Objekten. Weitere Informationen finden Sie unter der [M_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) Member der Klasse `CFrameWnd` in der *MFC-Referenz*.  
  
 Menü-Initialisierung wird automatisch in das Framework, das auftritt, wenn die Anwendung empfängt eine `WM_INITMENUPOPUP` Nachricht. Während Leerlaufschleife sucht das Framework das Befehlsrouting für Schaltfläche Aktualisierungshandler im großen und ganzen genauso wie bei Menüs dar.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)

