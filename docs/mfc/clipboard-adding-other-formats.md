---
title: "Zwischenablage: Hinzuf&#252;gen anderer Formate | Microsoft Docs"
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
  - "Zwischenablage, Formate"
  - "Benutzerdefinierte Zwischenablagedatenformate"
  - "Benutzerdefinierte Formate"
  - "Benutzerdefinierte Formate, Ablegen in der Zwischenablage"
  - "Formate [C++], Zwischenablage"
  - "Registrieren benutzerdefinierter Datenformate für die Zwischenablage"
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Zwischenablage: Hinzuf&#252;gen anderer Formate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie die Liste der unterstützten Formaten, besonders für OLE\-Unterstützung erweitert.  Im Thema [Zwischenablage: Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md) wird die minimale Implementierung, die erforderlich ist, das Kopieren und Einfügen aus der Zwischenablage zu unterstützen.  Wenn dieses alle ist, implementieren Sie, die einzelnen Stile, die in der Zwischenablage abgelegt werden, sind `CF_METAFILEPICT`, **CF\_EMBEDSOURCE**, **CF\_OBJECTDESCRIPTOR** und möglicherweise `CF_LINKSOURCE`.  Die meisten Anwendungen erfordern mehrere Stile auf die Zwischenablage als diese drei.  
  
##  <a name="_core_registering_custom_formats"></a> Registrieren von Gewohnheits\-Formaten  
 Um eigene Gewohnheitsformate zu erstellen, halten Sie die gleiche Prozedur ein, die Sie verwenden würden wenn jedes benutzerdefinierte Zwischenablageformat registriert wurde: Führen Sie den Namen des Formats der **RegisterClipboardFormat**\-Funktion und verwenden Sie deren Rückgabewert als Format ID  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> Platzieren von Formaten in der Zwischenablage  
 Weitere Formate denen hinzuzufügen, die in der Zwischenablage abgelegt werden, müssen Sie die Funktion `OnGetClipboardData` in der Klasse überschreiben, die Sie entweder von `COleClientItem` oder von `COleServerItem` abgeleitet haben \(je nachdem ob die Daten ist systemeigen kopiert wird\).  In dieser Funktion können Sie die folgende Prozedur aus.  
  
#### Weitere Formate in der Zwischenablage einfügen  
  
1.  Erstellen eines `COleDataSource`\-Objekts  
  
2.  Führen Sie diese Datenquelle mit einer Funktion, die den systemeigenen Datenformaten der Liste der unterstützten Formaten hinzufügen, indem Sie `COleDataSource::CacheGlobalData` aufrufen.  
  
3.  Fügen Sie Standardformaten hinzu, indem Sie `COleDataSource::CacheGlobalData` für jedes Standardformat aufrufen, die Sie unterstützen möchten.  
  
 Diese Vorgehensweise wird im Beispielprogramm [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE verwendet \(überprüfen Sie die `OnGetClipboardData`\-Memberfunktion der **CServerItem**\-Klasse\).  Der einzige Unterschied in dieses Beispiels ist, dass Schritt drei nicht implementiert wird, da HIERSVR keine anderen Standardformate unterstützt.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [OLE\-Datenobjekte und Datenquellen und einheitliche Datenübertragung](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [Drag & Drop](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## Siehe auch  
 [Zwischenablage: Verwenden des OLE\-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)