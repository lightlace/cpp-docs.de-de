---
title: "Erweitern des einfachen schreibgesch&#252;tzten Anbieters | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetLocate-Klasse"
  - "IRowsetLocate-Klasse, Hinzufügen zu OLE DB-Vorlagenanbietern"
  - "Schreibgeschützte Anbieter [C++]"
  - "Einfache schreibgeschützte Anbieter [C++]"
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Erweitern des einfachen schreibgesch&#252;tzten Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt wird beschrieben, wie Sie den [einfachen schreibgeschützten Anbieter](../../data/oledb/implementing-the-simple-read-only-provider.md) erweitern, der im vorherigen Abschnitt erstellt wurde.  `IRowsetLocateImpl` erstellt eine Implementierung für die `IRowsetLocate`\-Schnittstelle und fügt die Lesezeichenunterstützung hinzu.  
  
 Wenn der Anbieter einwandfrei funktioniert, können Sie ihn erweitern, sodass er Aktualisierungen unterstützt und Transaktionen behandelt, oder um die Leistung des Zeilenabrufalgorithmus zu optimieren.  Bei den meisten Anbietererweiterungen wird einem vorhandenen COM\-Objekt eine Schnittstelle hinzugefügt.  
  
 Bei dem Beispiel in den folgenden Themen wird der Zeilenabrufmechanismus optimiert, indem `CAgentRowset` die `IRowsetLocate`\-Schnittstelle hinzugefügt wird.  Wie Sie diese Aufgaben ausführen, erfahren Sie unter:  
  
-   [Vererben von IRowsetLocate an RMyProviderRowset](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)  
  
-   [Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)  
  
## Siehe auch  
 [Erstellen eines einfachen schreibgeschützten Anbieters](../../data/oledb/creating-a-simple-read-only-provider.md)