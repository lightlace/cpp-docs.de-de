---
title: 'Aktivierung: Verben | Microsoft Docs'
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
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2a443f4ce65dcc7e9460bd016638aa5069e7e6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activation-verbs"></a>Aktivierung: Verben
Dieser Artikel beschreibt die Rolle primären und sekundären Verben Play in OLE [Aktivierung](../mfc/activation-cpp.md).  
  
 Doppelklicken Sie auf ein eingebettetes Element kann in der Regel die Benutzer zu bearbeiten. Bestimmte Elemente jedoch nicht auf diese Weise Verhalten. Beispielsweise wird durch Doppelklicken auf ein Element mit der Audiorecorder-Anwendung erstellt nicht die Server in einem separaten Fenster geöffnet; Stattdessen gibt er den Sound.  
  
 Die Ursache für dieses Verhalten Unterschied ist, dass Audiorecorder Elementen ein anderes "primäres Verb." Primäre Verb ist die Aktion ausgeführt, wenn der Benutzer ein OLE-Element doppelklickt. Für die meisten Typen von OLE-Elementen ist das primäre Verb bearbeiten, das den Server startet, die das Element erstellt. Für einige Typen von Elementen, z. B. Audiorecorder-Elementen ist das primäre Verb wiedergeben.  
  
 Viele Typen von OLE-Elementen unterstützt nur ein Verb, und bearbeiten ist die am häufigsten verwendeten. Einige Typen von Elementen unterstützen jedoch mehrere Verben. Audiorecorder Elementen unterstützt z. B. als sekundäre Verb bearbeiten.  
  
 Ist eine andere häufig verwendete Verb "Open". Das Verb "Open" ist identisch mit "Bearbeiten", außer die Serveranwendung in einem separaten Fenster gestartet wird. Das Verb sollte verwendet werden, wenn der Container-Anwendung oder die Anwendung für die direkte Aktivierung nicht unterstützt.  
  
 Alle Verben als primäres Verb müssen über ein Untermenübefehl aufgerufen werden, wenn das Element ausgewählt ist. Dieses Untermenü enthält alle Verben, die vom Element unterstützt und wird normalerweise durch die *Typename* **Objekt** Befehl die **bearbeiten** Menü. Informationen zu den *Typename* **Objekt** Befehl, finden Sie im Artikel [Menüs und Ressourcen: Containererweiterungen](../mfc/menus-and-resources-container-additions.md).  
  
 Die Verben, die von die eine Server-Anwendung unterstützt werden in der Windows-Registrierung-Datenbank aufgeführt. Wenn die Server-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wird, wird es automatisch alle Verben registrieren, wenn der Server gestartet wird. Wenn dies nicht der Fall ist, sollten Sie diese während der Initialisierungsphase für die Server-Anwendung registrieren. Weitere Informationen finden Sie im Artikel [Registrierung](../mfc/registration.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Aktivierung](../mfc/activation-cpp.md)   
 [Containers](../mfc/containers.md)   
 [Server](../mfc/servers.md)

