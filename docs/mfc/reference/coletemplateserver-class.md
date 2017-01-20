---
title: "COleTemplateServer Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "COleTemplateServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation servers [C++], Implementieren"
  - "COleTemplateServer class"
  - "link containers [C++]"
  - "OLE link containers"
  - "OLE-Serveranwendungen, COleTemplateServer class"
  - "OLE-Serveranwendungen, managing server documents"
  - "Server, OLE"
  - "visual editing, Server"
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COleTemplateServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird für Server der visuellen Bearbeitungen in OLE Automatisierungsserver, und Linkcontainer \(Anwendungen die Links zu den eingebetteten\).  
  
## Syntax  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](../Topic/COleTemplateServer::COleTemplateServer.md)|Erstellt ein `COleTemplateServer`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](../Topic/COleTemplateServer::ConnectTemplate.md)|Schließt eine Normal\-Vorlage an das zugrunde liegende Objekt `COleObjectFactory` an.|  
|[COleTemplateServer::Unregister](../Topic/COleTemplateServer::Unregister.md)|Hebt die Registrierung zugeordnete Normal\-Vorlage auf.|  
|[COleTemplateServer::UpdateRegistry](../Topic/COleTemplateServer::UpdateRegistry.md)|Registriert den Dokumenttyp mit der OLE\-Systemregistrierung.|  
  
## Hinweise  
 Diese Klasse wird von der Klasse [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) berechnet; normalerweise können Sie `COleTemplateServer`, anstatt eine eigene Klasse die Ableitung direkt verwenden.  `COleTemplateServer` verwendet ein [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)\-Objekt, um die Serverdokumente zu verwalten.  Verwenden Sie `COleTemplateServer`, wenn Sie einen vollständigen Server h. einen Server implementieren, der als eigenständige Anwendung ausgeführt werden kann.  Vollständige Server sind in der Regel MDI \(Multiple Document Interface\), obwohl Anwendungen für eine SDI \(Single Document Interface\) unterstützt werden.  Ein Objekt `COleTemplateServer` wird für jeden Typ Serverdokument Unterstützung einer Anwendung erforderlich; das heißt, wenn die Serveranwendung Arbeitsblätter und Diagramme unterstützt, müssen Sie zwei `COleTemplateServer`\-Objekte verfügen.  
  
 `COleTemplateServer` überschreibt die `OnCreateInstance`\-Memberfunktion, die von `COleObjectFactory` definiert ist.  Diese Memberfunktion wird vom Framework aufgerufen, um ein C\+\+\-Objekt des richtigen Typs zu erstellen.  
  
 Weitere Informationen zu Server, finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [MFC\-Beispiel HIERSVR](../../top/visual-cpp-samples.md)   
 [COleObjectFactory Class](../../mfc/reference/coleobjectfactory-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)