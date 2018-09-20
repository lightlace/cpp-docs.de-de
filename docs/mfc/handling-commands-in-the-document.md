---
title: Behandeln von Kommentaren in einem Dokument | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8845ea7c44fd5a34774db0508302f5959987cdc9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441264"
---
# <a name="handling-commands-in-the-document"></a>Behandeln von Kommentaren in einem Dokument

Die Dokumentklasse möglicherweise auch bestimmte Befehle, die von Menüelementen, die Symbolleisten-Schaltflächen und Zugriffstasten generiert behandeln. In der Standardeinstellung `CDocument` speichern behandelt, und Speichern von Befehlen auf der Sie im Menü Datei mithilfe der Serialisierung. Befehle, die Auswirkungen auf die Daten können auch durch die Memberfunktionen des Dokuments behandelt werden. Klicken Sie in das Scribble-Programm, z. B.-Klasse `CScribDoc` stellt einen Handler für den Befehl alle deaktivieren bearbeiten, dadurch werden alle derzeit im Dokument gespeicherten Daten gelöscht. Dokumente können meldungszuordnungen aufweisen, aber im Gegensatz zu Ansichten, Dokumente standard-Windows-Nachrichten verarbeiten können nicht – nur **WM_COMMAND** Nachrichten oder "Befehle".

## <a name="see-also"></a>Siehe auch

[Verwenden von Dokumenten](../mfc/using-documents.md)

