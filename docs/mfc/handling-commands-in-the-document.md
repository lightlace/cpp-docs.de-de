---
title: Behandeln von Kommentaren in einem Dokument
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
ms.openlocfilehash: f3cce539d52bd04e97a6b5f84cbd833b05afb5bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240573"
---
# <a name="handling-commands-in-the-document"></a>Behandeln von Kommentaren in einem Dokument

Die Dokumentklasse möglicherweise auch bestimmte Befehle, die von Menüelementen, die Symbolleisten-Schaltflächen und Zugriffstasten generiert behandeln. In der Standardeinstellung `CDocument` speichern behandelt, und Speichern von Befehlen auf der Sie im Menü Datei mithilfe der Serialisierung. Befehle, die Auswirkungen auf die Daten können auch durch die Memberfunktionen des Dokuments behandelt werden. Klicken Sie in das Scribble-Programm, z. B.-Klasse `CScribDoc` stellt einen Handler für den Befehl alle deaktivieren bearbeiten, dadurch werden alle derzeit im Dokument gespeicherten Daten gelöscht. Dokumente können meldungszuordnungen aufweisen, aber im Gegensatz zu Ansichten, Dokumente standard-Windows-Nachrichten verarbeiten können nicht – nur **WM_COMMAND** Nachrichten oder "Befehle".

## <a name="see-also"></a>Siehe auch

[Verwenden von Dokumenten](../mfc/using-documents.md)
