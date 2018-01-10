---
title: "Erstellen eines einfachen schreibgeschützten Anbieters | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b5f840a6f401d8eb1bcca598d86622deb8f86cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-simple-read-only-provider"></a>Erstellen eines einfachen schreibgeschützten Anbieters
Wenn Sie einen OLE DB-Anbieter verwenden die ATL-Projekt-Assistent und die ATL-OLE DB-Anbieter-Assistenten erstellt haben, können Sie andere Funktionen hinzufügen, die Sie unterstützen möchten. Starten Sie das Entwerfen von Ihrem Anbieter Cachefehlers, welche Art von Daten, die Sie an den Consumer und unter welchen Bedingungen gesendet werden. Es ist besonders wichtig, um festzustellen, ob die Befehle, Transaktionen und andere optionale Objekte unterstützt werden müssen. Vorab ein guter Entwurf beschleunigt die Implementierung und testen.  
  
 Im Beispiel erhält in zwei Teilen:  
  
-   Der erste Teil zeigt wie [erstellen ein einfaches schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md) , liest ein Paar von Zeichenfolgen.  
  
-   Der zweite Teil veranschaulicht wie [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) durch Hinzufügen der `IRowsetLocate` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)