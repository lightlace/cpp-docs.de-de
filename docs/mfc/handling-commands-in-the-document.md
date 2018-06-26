---
title: Behandeln von Kommentaren in einem Dokument | Microsoft Docs
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
ms.openlocfilehash: 7a1e848827b46d40c1ec39f2af4788e6957932c5
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929111"
---
# <a name="handling-commands-in-the-document"></a>Behandeln von Kommentaren in einem Dokument
Ihre Dokumentklasse kann auch bestimmte Befehle, die durch die Menüelemente, Symbolleisten-Schaltflächen und Zugriffstasten generiert gehalten werden. Standardmäßig `CDocument` behandelt speichern, und speichern unter Befehle im Menü Datei mithilfe der Serialisierung. Andere Befehle, die Daten auswirken, können auch von Memberfunktionen des Dokuments behandelt werden. In das Scribble-Programm, z. B. Klasse `CScribDoc` stellt einen Handler für den Befehl Alle löschen bearbeiten, dadurch werden alle derzeit im Dokument gespeicherten Daten gelöscht. Dokumente können meldungszuordnungen, aber im Gegensatz zu Ansichten, Dokumente können nicht standardmäßige Windows-Meldungen verarbeiten – nur **WM_COMMAND** Nachrichten oder "Befehle".  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

