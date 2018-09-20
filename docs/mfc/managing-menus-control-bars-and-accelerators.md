---
title: Verwalten von Menüs, Steuerleisten und Zugriffstasten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1bd7a6515e943351980051d5f2344e80119cc9d4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428654"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>Verwalten von Menüs, Steuerleisten und Zugriffstasten

Das Rahmenfenster verwaltet aktualisieren Benutzeroberflächenobjekte, einschließlich Menüs, Symbolleisten-Schaltflächen, die Statusleiste und Zugriffstasten. Er verwaltet auch die gemeinsame Nutzung der Menüleiste im MDI-Anwendungen.

## <a name="managing-menus"></a>Verwalten von Menüs

Das Rahmenfenster beteiligt ist, Aktualisieren von Elementen der Benutzeroberfläche mit dem ON_UPDATE_COMMAND_UI-Mechanismus in beschriebenen [wie Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md). Schaltflächen in Symbolleisten und andere Schiebeleisten-Steuerelemente werden während der Leerlaufschleife aktualisiert. Menüelemente im Dropdown-Menüs in der Menüleiste werden aktualisiert, kurz bevor das Menü angezeigt wird.

Für MDI-Anwendungen verwaltet das MDI-Rahmenfenster, die Menüleiste und die Beschriftung. Ein MDI-Rahmenfenster besitzt eine Standardmenü, das als Menüleiste verwendet wird, wenn keine aktiven untergeordneten MDI-Fenster vorhanden sind. Bei der aktiven untergeordneten Elemente vorhanden sind, wird die Menüleiste des MDI-Rahmenfensters von klicken Sie im Menü für das aktive untergeordnete MDI-Fenster übernommen. Wenn eine MDI-Anwendung mehrere Dokumenttypen, z. B. Dokumenten, Diagramm oder Arbeitsblatt, unterstützt jeder setzt seine eigenen Menüs in der Menüleiste und ändert die Beschriftung für das Hauptrahmenfenster.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) stellt standardimplementierungen für die standard-Befehle im Menü Fenster, das angezeigt wird, für MDI-Anwendungen. Insbesondere wird der Befehl "Neues Fenster" (ID_WINDOW_NEW) implementiert, um ein neues Rahmenfensterobjekt und Ansicht für das aktuelle Dokument erstellen. Sie müssen diese Implementierungen nur überschreiben, wenn Sie erweiterte Anpassung benötigen.

Mehrere untergeordneten MDI-Fenster des gleichen Dokumenttyps freigeben Menüressourcen. Wenn mehrere untergeordnete MDI-Fenster mit den gleichen Dokumentvorlage erstellt werden, können sie alle die gleichen Menüressource, Systemressourcen in Windows speichern verwenden.

## <a name="managing-the-status-bar"></a>Verwalten der Statusleiste

Das Rahmenfenster ist auch die Statusleiste im Clientbereich positioniert und verwaltet den Status des Balkens Indikatoren. Das Rahmenfenster löscht und den Bereich in der Statusleiste aktualisiert bei Bedarf und eingabeaufforderungs-Zeichenfolgen wie der Benutzer, Menüelemente und Symbolleisten-Schaltflächen auswählt, zeigt, wie in beschrieben [wie zum Anzeigen von Befehlsinformationen in der Statusleiste](../mfc/how-to-display-command-information-in-the-status-bar.md).

## <a name="managing-accelerators"></a>Verwalten von Zugriffstasten

Jede Rahmenfenster verwaltet eine optionale Accelerator-Tabelle, die Accelerator-Übersetzung für Sie automatisch Tastaturfokus. Dieser Mechanismus erleichtert es, um Zugriffstasten (auch als Tastenkombinationen bezeichnet) zu definieren, der Aufruf von Menübefehlen.

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

