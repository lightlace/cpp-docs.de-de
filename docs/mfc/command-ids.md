---
title: Befehls-IDs
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: 76071105e72f1ca4a851b9cdb76d5f1a96f44edb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219891"
---
# <a name="command-ids"></a>Befehls-IDs

Ein Befehl ist vollständig mit der Befehls-ID, die allein beschrieben (in codiert die **WM_COMMAND** Nachricht). Diese ID wird das Benutzeroberflächen-Objekt zugewiesen, die der Befehl generiert. In der Regel sind IDs für die Funktionalität des Benutzeroberflächen-Objekts mit dem Namen, die, denen Ihnen zugewiesen wurden.

Z. B. ein Element alle löschen, in dem Menü "Bearbeiten" möglicherweise eine ID wie folgt zugewiesen werden **ID_EDIT_CLEAR_ALL**. Die Class-Bibliothek verfügt über vordefinierte einige IDs, insbesondere für Befehle, die das Framework selbst, wie z. B. verarbeitet **ID_EDIT_CLEAR_ALL** oder **ID_FILE_OPEN**. Sie werden andere Befehls-IDs selbst erstellen.

Bei der Erstellung Ihrer eigenen Menüs in der Visualisierung C++ Menü-Editor, es ist eine gute Idee, die Klassenbibliothek folgen der Namenskonvention wie dargestellt **ID_FILE_OPEN**. [Standardbefehle](../mfc/standard-commands.md) erläutert die standardmäßigen Befehle, die von der Klassenbibliothek definiert.

## <a name="see-also"></a>Siehe auch

[Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md)
