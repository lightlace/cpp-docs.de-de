---
title: Befehl Ziele | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 408f63b80ff30a7ebdc51e5becb1dd97bb062852
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404227"
---
# <a name="command-targets"></a>Befehlsziele

In der Abbildung [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md) zeigt die Verbindung zwischen einem Benutzeroberfläche-Objekt, z. B. ein Menüelement, und die Handlerfunktion, die vom Framework aufgerufen, um den Befehl ausführen, wenn das-Objekt geklickt wird.

Windows sendet Nachrichten ohne Command-Meldungen direkt an ein Fenster, dessen Handler für die Nachricht dann aufgerufen wird. Jedoch das Framework leitet Befehle, um eine Reihe von möglichen Objekten – "Befehlsziele" aufgerufen, von denen normalerweise einen Handler für den Befehl aufruft. Die Handlerfunktionen in gleicher Weise für sowohl Befehle als auch standard-Windows-Meldungen, unterscheiden sich jedoch die Mechanismen, mit dem sie aufgerufen werden, wie unter [wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

