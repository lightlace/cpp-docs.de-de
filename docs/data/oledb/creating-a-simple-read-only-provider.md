---
title: "Erstellen eines einfachen schreibgeschützten Anbieters | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 830ba99037607f4fc8ceac9bad451381c30c7786
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="creating-a-simple-read-only-provider"></a>Erstellen eines einfachen schreibgeschützten Anbieters
Wenn Sie einen OLE DB-Anbieter verwenden die ATL-Projekt-Assistent und die ATL-OLE DB-Anbieter-Assistenten erstellt haben, können Sie andere Funktionen hinzufügen, die Sie unterstützen möchten. Starten Sie das Entwerfen von Ihrem Anbieter Cachefehlers, welche Art von Daten, die Sie an den Consumer und unter welchen Bedingungen gesendet werden. Es ist besonders wichtig, um festzustellen, ob die Befehle, Transaktionen und andere optionale Objekte unterstützt werden müssen. Vorab ein guter Entwurf beschleunigt die Implementierung und testen.  
  
 Im Beispiel erhält in zwei Teilen:  
  
-   Der erste Teil zeigt wie [erstellen ein einfaches schreibgeschützten Anbieters](../../data/oledb/implementing-the-simple-read-only-provider.md) , liest ein Paar von Zeichenfolgen.  
  
-   Der zweite Teil veranschaulicht wie [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) durch Hinzufügen der `IRowsetLocate` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)