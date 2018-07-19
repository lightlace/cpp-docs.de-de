---
title: Erstellen eines einfachen schreibgeschützten Anbieters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2662a071f443967b921c4a8db27713bc7c3e8bb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096937"
---
# <a name="creating-a-simple-read-only-provider"></a>Erstellen eines einfachen schreibgeschützten Anbieters
Wenn Sie einen OLE DB-Anbieter verwenden die ATL-Projekt-Assistent und die ATL-OLE DB-Anbieter-Assistenten erstellt haben, können Sie andere Funktionen hinzufügen, die Sie unterstützen möchten. Starten Sie das Entwerfen von Ihrem Anbieter Cachefehlers, welche Art von Daten, die Sie an den Consumer und unter welchen Bedingungen gesendet werden. Es ist besonders wichtig, um festzustellen, ob die Befehle, Transaktionen und andere optionale Objekte unterstützt werden müssen. Vorab ein guter Entwurf beschleunigt die Implementierung und testen.  
  
 Im Beispiel erhält in zwei Teilen:  
  
-   Der erste Teil zeigt wie [erstellen ein einfaches schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md) , liest ein Paar von Zeichenfolgen.  
  
-   Der zweite Teil veranschaulicht wie [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) durch Hinzufügen der `IRowsetLocate` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)