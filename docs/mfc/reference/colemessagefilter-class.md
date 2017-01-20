---
title: "COleMessageFilter Class"
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
  - "COleMessageFilter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungen [OLE], managing interactions"
  - "COleMessageFilter class"
  - "message filters [C++]"
  - "Nachrichten [C++], OLE"
  - "OLE [C++], managing concurrency"
  - "OLE-Anwendungen [C++], managing interactions"
  - "OLE messages"
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# COleMessageFilter Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet die Parallelität, die durch die Interaktion der OLE\-Anwendungen benötigt wird.  
  
## Syntax  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleMessageFilter::COleMessageFilter](../Topic/COleMessageFilter::COleMessageFilter.md)|Erstellt ein `COleMessageFilter`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleMessageFilter::BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md)|Setzt die Anwendung in den ausgelasteten Zustand.|  
|[COleMessageFilter::EnableBusyDialog](../Topic/COleMessageFilter::EnableBusyDialog.md)|Aktiviert und deaktiviert das Dialogfeld, das angezeigt wird, wenn eine aufgerufene Anwendung ausgelastet ist.|  
|[COleMessageFilter::EnableNotRespondingDialog](../Topic/COleMessageFilter::EnableNotRespondingDialog.md)|Aktiviert und deaktiviert das Dialogfeld, das angezeigt wird, wenn eine aufgerufene Anwendung nicht reagiert.|  
|[COleMessageFilter::EndBusyState](../Topic/COleMessageFilter::EndBusyState.md)|Beendet den ausgelasteten Zustand der Anwendung.|  
|[COleMessageFilter::OnMessagePending](../Topic/COleMessageFilter::OnMessagePending.md)|Aufgerufen vom Framework, um Nachrichten zu verarbeiten, während ein OLE\-Aufruf ausgeführt wird.|  
|[COleMessageFilter::Register](../Topic/COleMessageFilter::Register.md)|Registriert den Meldungsfilter mit den OLE\-Systemen\-DLL.|  
|[COleMessageFilter::Revoke](../Topic/COleMessageFilter::Revoke.md)|Widerruft die Registrierung des Meldungsfilters mit den OLE\-Systemen\-DLL.|  
|[COleMessageFilter::SetBusyReply](../Topic/COleMessageFilter::SetBusyReply.md)|Bestimmt die ausgelastete Antwort der Anwendung auf einem OLE\-Aufruf.|  
|[COleMessageFilter::SetMessagePendingDelay](../Topic/COleMessageFilter::SetMessagePendingDelay.md)|Bestimmt, wie lange die Anwendung auf eine Antwort auf ein OLE\-Aufruf wartet.|  
|[COleMessageFilter::SetRetryReply](../Topic/COleMessageFilter::SetRetryReply.md)|Bestimmt die aufrufende Antwort der Anwendung auf eine ausgelastete Anwendung.|  
  
## Hinweise  
 Die Klasse ist `COleMessageFilter` im visuellen in Bearbeitungsserver und \-Containeranwendungen sowie in OLE\-Automatisierungs\-Anwendungen hilfreich.  Für Serveranwendungen, die aufgerufen werden, kann diese Klasse verwendet werden, um die Anwendung ausgelastet" zu "enthalten, damit eingehende Aufrufe von anderen Containeranwendungen entweder später abgebrochen oder wiederholt werden.  Diese Klasse kann auch verwendet werden, um die Aktion zu bestimmen, durch eine aufrufende Anwendung auszuführenden, wenn die aufgerufene Anwendung ausgelastet ist.  
  
 Üblicherweise wird, damit eine Serveranwendung [BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md) und [EndBusyState](../Topic/COleMessageFilter::EndBusyState.md) aufruft, als es gefährlich sein würde, sodass ein Dokument oder ein anderes OLE\-Objekt, auf das zugegriffen werden kann, zerstört werden kann.  Diese Aufrufe werden in [CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md) während der Benutzeroberflächeupdates gemacht.  
  
 Standardmäßig wird ein `COleMessageFilter`\-Objekt zugeordnet, wenn die Anwendung initialisiert wird.  Es kann mit [AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md) abgerufen werden.  
  
 Dies ist eine erweiterte Klasse; Sie müssen selten darin arbeiten direkt.  
  
 Weitere Informationen finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)