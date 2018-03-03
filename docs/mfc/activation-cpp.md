---
title: Aktivierung (C++) | Microsoft Docs
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
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70017721fb59fa0c6d18d568546d9618257328b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activation-c"></a>Aktivierung (C++)
Dieser Artikel beschreibt die Rolle der Aktivierung in die visuelle Bearbeitung von OLE-Elementen. Nachdem ein Benutzer ein OLE-Element in einem Containerdokument eingebettet ist, müssen sie möglicherweise verwendet werden. Zu diesem Zweck doppelklickt der Benutzer das Element, das dieses Element aktiviert wird. Die am häufigsten auftretende Aktivität für die Aktivierung wird bearbeitet. Viele aktuelle OLE-Elemente, wenn für die Bearbeitung aktiviert dazu führen, dass die Menüs und Symbolleisten in der aktuellen Rahmenfenster so ändern Sie entsprechend die Attribute für die Serveranwendung, die das Element erstellt. Dieses Verhalten, bekannt als direkte Aktivierung, kann der Benutzer ein eingebettetes Element in ein Verbunddokument bearbeiten, ohne das Containerdokument Fenster verlassen zu müssen.  
  
 Es ist auch möglich, eingebettete OLE-Elemente in einem separaten Fenster zu bearbeiten. Dies geschieht, wenn der Container oder der Server die direkte Aktivierung nicht unterstützt. In diesem Fall, wenn der Benutzer auf ein eingebettetes Element doppelklicken, die Serveranwendung in einem separaten Fenster gestartet wird, und das eingebettete Element wird als sein eigenes Dokument angezeigt. Der Benutzer das Element in diesem Fenster bearbeitet wird. Bearbeitung abgeschlossen wird, wird der Benutzer schließt die Serveranwendung und der containeranwendung zurückgibt.  
  
 Als Alternative, der Benutzer kann wahlweise "öffnen, bearbeiten" mit der  **\<Objekt > Öffnen** Befehl die **bearbeiten** Menü. Dadurch wird das Objekt in einem separaten Fenster geöffnet.  
  
> [!NOTE]
>  Bearbeiten von eingebetteten Elemente in einem separaten Fenster war das Standardverhalten in Version 1 von OLE, und einige OLE-serveranwendungen können nur auf diese Art der Bearbeitung unterstützen.  
  
 Direkte Aktivierung stuft einen dokumentorientierte Ansatz zum Erstellen eines Dokuments. Der Benutzer kann ein Verbunddokument als eine Einheit behandelt die Arbeit ohne Wechsel zwischen den Anwendungen. Direkte Aktivierung wird jedoch nur für eingebettete Elemente, nicht für verknüpfte Elemente verwendet: sie müssen in einem separaten Fenster bearbeitet werden. Dies ist, da ein verknüpftes Element in einem anderen Ort gespeichert ist. Die Bearbeitung eines verknüpften Elements findet innerhalb der Daten, d. h. die tatsächliche Kontext, in dem die Daten gespeichert werden. Bearbeiten ein verknüpftes Element in einem separaten Fenster daran erinnert, den Benutzer, den die Daten zu einem anderen Dokument gehört.  
  
 MFC unterstützt keine geschachtelten direkte Aktivierung. Wenn Sie eine Container/Server-Anwendung erstellen, und dass Container/Server in einem anderen Container und direktes aktiviert eingebettet ist es kein direktes aktivieren eingebettete darin enthaltenen Objekte.  
  
 Was auf ein eingebettetes Element geschieht, wenn der Benutzer darauf doppelklickt, hängt von der Verben, die für das Element definiert. Informationen finden Sie unter [Aktivierung: Verben](../mfc/activation-verbs.md).  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Containers](../mfc/containers.md)   
 [Server](../mfc/servers.md)

