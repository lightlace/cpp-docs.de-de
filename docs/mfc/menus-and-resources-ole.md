---
title: Menüs und Ressourcen (OLE) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cae180ca71b89732e073b9039483b8b46366a42a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929633"
---
# <a name="menus-and-resources-ole"></a>Menüs und Ressourcen (OLE)
Diese Gruppe von Artikeln wird die Verwendung von Menüs und Ressourcen in MFC-OLE-dokumentanwendungen erläutert.  
  
 OLE visuelle Bearbeitung zusätzliche stellt Anforderungen an die im Menü und andere Ressourcen von OLE-dokumentanwendungen bereitgestellt werden, da es eine Reihe von Modi, in welchem beide Container gibt und serveranwendungen (Komponente) gestartet und verwendet werden können. Beispielsweise kann eine vollständige Serveranwendung in einem der folgenden drei Modi ausführen:  
  
-   Eigenständig.  
  
-   Für das Bearbeiten eines Elements innerhalb des Kontexts eines Containers eingerichtet.  
  
-   Zum Bearbeiten eines Elements im Kontext des Containers, oft in einem separaten Fenster geöffnet.  
  
 Dies erfordert drei separate Menülayouts, eine für jeden möglichen Modus der Anwendung. Zugriffstastentabellen sind auch für jeden neuen Modus erforderlich. Eine Steuerelementcontainer-Anwendung möglicherweise nicht unterstützen oder direkte Aktivierung; Wenn dies der Fall ist, benötigt eine neue Menüstruktur und zugeordnete Zugriffstastentabellen.  
  
 Direkte Aktivierung erfordert, dass die Container und serveranwendungen in Menüs, Symbolleisten und Status Leiste Speicherplatz aushandeln müssen. Alle Ressourcen müssen mit diesem entworfen werden. Der Artikel [Menüs und Ressourcen: Menüs schachteln](../mfc/menus-and-resources-menu-merging.md) werden in diesem Thema im Detail behandelt.  
  
 Aufgrund dieser Probleme können mit Anwendungs-Assistenten erstellte OLE-dokumentanwendungen bis zu vier separate Menüs und Ressourcen der Accelerator-Tabelle verfügen. Diese werden aus den folgenden Gründen verwendet:  
  
|Ressourcenname|Mit|  
|-------------------|---------|  
|IDR_MAINFRAME|In einer MDI-Anwendung, wenn keine Datei geöffnet ist oder in einer SDI-Anwendung unabhängig von der geöffneten Dateien verwendet. Dies ist die standardmäßige Menü in nicht-OLE-Anwendungen verwendet.|  
|IDR_\<Projekt > Typ|In einer MDI-Anwendung verwendet, wenn Dateien geöffnet sind. Verwendet, wenn eine Anwendung eigenständig ausgeführt wird. Dies ist die standardmäßige Menü in nicht-OLE-Anwendungen verwendet.|  
|IDR_\<Projekt > TYPE_SRVR_IP|Vom Server oder Container verwendet, wenn ein Objekt öffnen vorhanden ist.|  
|IDR_\<Projekt > TYPE_SRVR_EMB|Von einer Serveranwendung verwendet, wenn ein Objekt ohne direkte Aktivierung geöffnet ist.|  
  
 Jedes dieser Ressource-Namen darstellt eines Menüs und, in der Regel einer Zugriffstastentabelle. Eine ähnliche Schema sollte in MFC-Anwendungen verwendet werden, die nicht mit dem Anwendungs-Assistenten erstellt werden.  
  
 Die folgenden Artikel werden Themen im Zusammenhang mit Containern, Servern und die direkte Aktivierung implementiert Zusammenführungsfunktion behandelt:  
  
-   [Menüs und Ressourcen: Containererweiterungen](../mfc/menus-and-resources-container-additions.md)  
  
-   [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md)  
  
-   [Menüs und Ressourcen: Menüs schachteln](../mfc/menus-and-resources-menu-merging.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)

