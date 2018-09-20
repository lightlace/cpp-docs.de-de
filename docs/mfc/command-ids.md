---
title: Befehls-IDs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5087c271151793169cbf7350f78750044ccead0b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446971"
---
# <a name="command-ids"></a>Befehls-IDs

Ein Befehl ist vollständig mit der Befehls-ID, die allein beschrieben (in codiert die **WM_COMMAND** Nachricht). Diese ID wird das Benutzeroberflächen-Objekt zugewiesen, die der Befehl generiert. In der Regel sind IDs für die Funktionalität des Benutzeroberflächen-Objekts mit dem Namen, die, denen Ihnen zugewiesen wurden.

Z. B. ein Element alle löschen, in dem Menü "Bearbeiten" möglicherweise eine ID wie folgt zugewiesen werden **ID_EDIT_CLEAR_ALL**. Die Class-Bibliothek verfügt über vordefinierte einige IDs, insbesondere für Befehle, die das Framework selbst, wie z. B. verarbeitet **ID_EDIT_CLEAR_ALL** oder **ID_FILE_OPEN**. Sie werden andere Befehls-IDs selbst erstellen.

Wenn Sie Ihre eigenen Menüs Menü-Editor in der Visual C++ erstellen, es ist eine gute Idee, die Klassenbibliothek folgen der Namenskonvention wie dargestellt **ID_FILE_OPEN**. [Standardbefehle](../mfc/standard-commands.md) erläutert die standardmäßigen Befehle, die von der Klassenbibliothek definiert.

## <a name="see-also"></a>Siehe auch

[Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md)

