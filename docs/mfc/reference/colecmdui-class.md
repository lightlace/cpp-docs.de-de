---
title: "COleCmdUI Class"
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
  - "COleCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "COleCmdUI class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# COleCmdUI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine Methode, sodass MFC den Zustand von den Benutzeroberflächenobjekten aktualisiert, die den en\-gesteuert Funktionen `IOleCommandTarget` der Anwendung verknüpft werden.  
  
## Syntax  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](../Topic/COleCmdUI::COleCmdUI.md)|Erstellt ein `COleCmdUI`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleCmdUI::Enable](../Topic/COleCmdUI::Enable.md)|Setzt oder freie Räume das aktivierensbefehlsflag.|  
|[COleCmdUI::SetCheck](../Topic/COleCmdUI::SetCheck.md)|Legt den Zustand eines Ein\/Ausen Toggle\-Befehls fest.|  
|[COleCmdUI::SetText](../Topic/COleCmdUI::SetText.md)|Gibt eine Textname\- oder \-Statuszeichenfolge für einen Befehl zurück.|  
  
## Hinweise  
 In einer Anwendung, die nicht für DocObjects aktiviert wird, wenn der Benutzer ein Menü in der Anwendung, MFC **UPDATE\_COMMAND\_UI** notifcations verarbeitet.  Jede Benachrichtigung wird ein [CCmdUI](../../mfc/reference/ccmdui-class.md)\-Objekt zugewiesen, das bearbeitet werden kann, um den Zustand eines bestimmten Befehls wiederzugeben.  Wenn die Anwendung jedoch für DocObjects aktiviert ist, weist MFC\-Prozesse **UPDATE\_OLE\_COMMAND\_UI** Benachrichtigungen und `COleCmdUI`\-Objekte.  
  
 `COleCmdUI` ermöglicht einem DocObject, um Befehle zu empfangen, die aus der Benutzeroberfläche des Containers \(wie FileNew, geöffnet, Drucken, usw.\). stammen, und ermöglicht dem Container, um Befehle zu empfangen, die aus der des DocObjects Benutzeroberfläche stammen.  Obwohl `IDispatch` verwendet werden kann, um die gleichen Befehle weiterzuleiten, `IOleCommandTarget` bietet eine einfachere Möglichkeit abzufragen und auszuführen, da sie auf einem Standardsatz von Befehlen, normalerweise ohne Argumente und keinen Typinformationen beruht, wird beteiligt ist.  `COleCmdUI` kann verwendet werden, um andere Eigenschaften von DocObject\-Benutzeroberflächenbefehlen zu aktivieren, zu aktualisieren und festzulegen.  Wenn Sie den Befehl aufrufen möchten, rufen Sie [COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md) auf.  
  
 Weitere Informationen zu DocObjects finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md).  Siehe auch [Internet\-erste Schritte: Active Documents](../../mfc/active-documents-on-the-internet.md) und [Active Documents](../../mfc/active-documents-on-the-internet.md).  
  
## Vererbungshierarchie  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## Anforderungen  
 **Header:**  afxdocobj.h  
  
## Siehe auch  
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)