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
ms.openlocfilehash: c20ff02b2d72f1dfa6afab5a0d547b46aa55b18c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343553"
---
# <a name="handling-commands-in-the-document"></a>Behandeln von Kommentaren in einem Dokument
Ihre Dokumentklasse kann auch bestimmte Befehle, die durch die Menüelemente, Symbolleisten-Schaltflächen und Zugriffstasten generiert gehalten werden. Standardmäßig **CDocument** behandelt speichern, und speichern unter Befehle im Menü Datei mithilfe der Serialisierung. Andere Befehle, die Daten auswirken, können auch von Memberfunktionen des Dokuments behandelt werden. In das Scribble-Programm, z. B. Klasse `CScribDoc` stellt einen Handler für den Befehl Alle löschen bearbeiten, dadurch werden alle derzeit im Dokument gespeicherten Daten gelöscht. Dokumente können meldungszuordnungen, aber im Gegensatz zu Ansichten, Dokumente können nicht standardmäßige Windows-Meldungen verarbeiten – nur **WM_COMMAND** Nachrichten oder "Befehle".  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

