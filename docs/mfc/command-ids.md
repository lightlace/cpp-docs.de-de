---
title: Befehls-IDs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b651c734fbd7098705801aefcaa490293a4d661d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-ids"></a>Befehls-IDs
Ein Befehl wird durch die Befehls-ID, die allein vollständig beschrieben (codiert, der **WM_COMMAND** Nachricht). Diese ID wird mit dem Benutzeroberflächen-Objekt zugewiesen, die der Befehl generiert. In der Regel sind IDs für die Funktionalität des Benutzeroberflächen-Objekts mit dem Namen, denen ihnen zugewiesen wurden.  
  
 Z. B. ein alles Element im Menü Bearbeiten möglicherweise zugewiesen ID wie z. B. **ID_EDIT_CLEAR_ALL**. Die Klassenbibliothek sind einige IDs, insbesondere für Befehle, die das Framework selbst, wie z. B. verarbeitet vordefiniert **ID_EDIT_CLEAR_ALL** oder `ID_FILE_OPEN`. Andere Befehls-IDs werden Sie selbst erstellen.  
  
 Wenn Sie eine eigene Menüs Menü-Editor in Visual C++-Komponente erstellen, es ist eine gute Idee, die Klassenbibliothek folgen der Namenskonvention wie veranschaulicht `ID_FILE_OPEN`. [Standardbefehle](../mfc/standard-commands.md) erläutert die standard-Befehle von der Klassenbibliothek definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md)

