---
title: "CCmdTarget Class"
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
  - "CCmdTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdTarget class"
  - "Befehlsrouting, command targets"
  - "command targets"
  - "message maps, CCmdTarget base class"
  - "Ziele, Befehl"
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CCmdTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für die Microsoft Foundation Class\-Bibliothek\-Meldungszuordnungsarchitektur.  
  
## Syntax  
  
```  
class CCmdTarget : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CCmdTarget::CCmdTarget](../Topic/CCmdTarget::CCmdTarget.md)|Erstellt ein `CCmdTarget`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)|Zeigt den Cursor als Sanduhrcursor an.|  
|[CCmdTarget::DoOleVerb](../Topic/CCmdTarget::DoOleVerb.md)|Verursacht eine Aktion, die von einem ausgeführt werden OLE\-angegeben wird Verb.|  
|[CCmdTarget::EnableAutomation](../Topic/CCmdTarget::EnableAutomation.md)|Ermöglicht das OLE\-Automatisierung `CCmdTarget`\-Objekt zu.|  
|[CCmdTarget::EnableConnections](../Topic/CCmdTarget::EnableConnections.md)|Ermöglicht das Auslösen von Ereignissen zu Verbindungspunkten.|  
|[CCmdTarget::EnableTypeLib](../Topic/CCmdTarget::EnableTypeLib.md)|Aktiviert die Typbibliothek eines Objekts.|  
|[CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)|EINGABETASTE zum vorherigen Cursor.|  
|[CCmdTarget::EnumOleVerbs](../Topic/CCmdTarget::EnumOleVerbs.md)|Listet das OLE\-Verben eines Objekts auf.|  
|[CCmdTarget::FromIDispatch](../Topic/CCmdTarget::FromIDispatch.md)|Gibt einen Zeiger auf `CCmdTarget`\-Objekt zurück, das mit dem `IDispatch` Zeiger zugeordnet ist.|  
|[CCmdTarget::GetDispatchIID](../Topic/CCmdTarget::GetDispatchIID.md)|Ruft die primäre Dispatchschnittstelle ID ab|  
|[CCmdTarget::GetIDispatch](../Topic/CCmdTarget::GetIDispatch.md)|Gibt einen Zeiger auf `IDispatch`\-Objekt zurück, das mit dem `CCmdTarget`\-Objekt zugeordnet ist.|  
|[CCmdTarget::GetTypeInfoCount](../Topic/CCmdTarget::GetTypeInfoCount.md)|Ruft die Anzahl der Typinformationsschnittstellen ab, die ein Objekt bereitstellt.|  
|[CCmdTarget::GetTypeInfoOfGuid](../Topic/CCmdTarget::GetTypeInfoOfGuid.md)|Ruft die Typenbeschreibung ab, die der angegebenen GUID entspricht.|  
|[CCmdTarget::GetTypeLib](../Topic/CCmdTarget::GetTypeLib.md)|Ruft einen Zeiger auf eine Typbibliothek.|  
|[CCmdTarget::GetTypeLibCache](../Topic/CCmdTarget::GetTypeLibCache.md)|Ruft den Typbibliothekscachen ab.|  
|[CCmdTarget::IsInvokeAllowed](../Topic/CCmdTarget::IsInvokeAllowed.md)|Ermöglicht Automatisierungsmethodenaufruf.|  
|[CCmdTarget::IsResultExpected](../Topic/CCmdTarget::IsResultExpected.md)|Gibt Wert ungleich 0 zurück, wenn eine Automatisierungsfunktion einen Wert zurückgibt.|  
|[CCmdTarget::OnCmdMsg](../Topic/CCmdTarget::OnCmdMsg.md)|Routen und Dispatches beherrschen Meldungen.|  
|[CCmdTarget::OnFinalRelease](../Topic/CCmdTarget::OnFinalRelease.md)|Die bereinigt auf, nachdem der Verweis des letzten OLE freigegeben ist.|  
|[CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)|Stellt den Sanduhrcursor wiederher.|  
  
## Hinweise  
 Eine Meldungszuordnung leitet Befehle oder Meldungen zu den Memberfunktionen weiter, die Sie schreiben, um sie zu behandeln.  \(A\-Befehl ist eine Nachricht von einem Menüelement, einer Befehlsschaltfläche oder einer Zugriffstaste.\)  
  
 Die Schlüsselframeworkklassen, die von `CCmdTarget` abgeleitet werden, enthalten [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md) und [CFrameWnd](../../mfc/reference/cframewnd-class.md).  Wenn Sie für eine neue Klasse bestimmen, Meldungen verarbeiten, leiten Sie die Klasse von einer aus diesem `CCmdTarget` von abgeleitete Klassen.  Sie leiten selten eine Klasse von `CCmdTarget` direkt.  
  
 Eine Übersicht über den Befehlszielen und `OnCmdMsg`\-Routing finden Sie unter [Befehls\-Ziele](../../mfc/command-targets.md), [Befehlsrouting](../../mfc/command-routing.md) und [Zuordnen von Meldungen](../../mfc/mapping-messages.md).  
  
 `CCmdTarget` enthält Memberfunktionen, die die Anzeige eines Sanduhrcursors behandeln.  Zeigen Sie den Sanduhrcursor an, wenn Sie einen Befehl erwarten, ein beträchtliches Zeitintervall zu verwenden, um.  
  
 Die Dispatchzuordnungen, die den Meldungszuordnungen ähnlich sind, werden verwendet, um `IDispatch`\-OLE\-Automatisierungsfunktionalität verfügbar zu machen.  Mithilfe dieser Schnittstelle verfügbar machen, können andere Anwendungen \(wie Visual Basic\) in der Anwendung aufrufen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel ACDual](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [COleDispatchDriver Class](../../mfc/reference/coledispatchdriver-class.md)