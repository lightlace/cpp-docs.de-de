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
ms.openlocfilehash: d2f0a7271452ace9b9e06ff995af61881db4403c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548953"
---
# <a name="handling-commands-in-the-document"></a>Behandeln von Kommentaren in einem Dokument

Die Dokumentklasse möglicherweise auch bestimmte Befehle, die von Menüelementen, die Symbolleisten-Schaltflächen und Zugriffstasten generiert behandeln. In der Standardeinstellung `CDocument` speichern behandelt, und Speichern von Befehlen auf der Sie im Menü Datei mithilfe der Serialisierung. Befehle, die Auswirkungen auf die Daten können auch durch die Memberfunktionen des Dokuments behandelt werden. Klicken Sie in das Scribble-Programm, z. B.-Klasse `CScribDoc` stellt einen Handler für den Befehl alle deaktivieren bearbeiten, dadurch werden alle derzeit im Dokument gespeicherten Daten gelöscht. Dokumente können meldungszuordnungen aufweisen, aber im Gegensatz zu Ansichten, Dokumente standard-Windows-Nachrichten verarbeiten können nicht – nur **WM_COMMAND** Nachrichten oder "Befehle".

## <a name="see-also"></a>Siehe auch

[Verwenden von Dokumenten](../mfc/using-documents.md)

