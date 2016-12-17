---
title: "CConnectionPoint Class"
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
  - "CConnectionPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CConnectionPoint class"
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CConnectionPoint Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert einen besonderen Typ Schnittstelle verwendet, um mit anderen OLE\-Objekten zu kommunizieren, aufgerufen einen Verbindungspunkt "."  
  
## Syntax  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](../Topic/CConnectionPoint::CConnectionPoint.md)|Erstellt ein `CConnectionPoint`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CConnectionPoint::GetConnections](../Topic/CConnectionPoint::GetConnections.md)|Ruft alle Verbindungspunkte in einer Verbindungszuordnung ab.|  
|[CConnectionPoint::GetContainer](../Topic/CConnectionPoint::GetContainer.md)|Ruft den Container des Steuerelements ab, das die Verbindungszuordnung besitzt.|  
|[CConnectionPoint::GetIID](../Topic/CConnectionPoint::GetIID.md)|Ruft die Schnittstellen\-ID eines Verbindungspunktes ab.|  
|[CConnectionPoint::GetMaxConnections](../Topic/CConnectionPoint::GetMaxConnections.md)|Ruft die maximale Anzahl von Verbindungspunkten ab, die von einem Steuerelement unterstützt werden.|  
|[CConnectionPoint::GetNextConnection](../Topic/CConnectionPoint::GetNextConnection.md)|Ruft einen Zeiger auf das Verbindungselement bei `pos` ab.|  
|[CConnectionPoint::GetStartPosition](../Topic/CConnectionPoint::GetStartPosition.md)|Startet eine Zuordnungsiteration durch das Zurückgeben eines Werts **POSITION**, der einem `GetNextConnection` Aufruf übergeben werden kann.|  
|[CConnectionPoint::OnAdvise](../Topic/CConnectionPoint::OnAdvise.md)|Aufgerufen vom Framework, wenn Verbindungen eingerichtet werden oder unterbrochen werden.|  
|[CConnectionPoint::QuerySinkInterface](../Topic/CConnectionPoint::QuerySinkInterface.md)|Ruft einen Zeiger auf die angeforderte Senkenschnittstelle ab.|  
  
## Hinweise  
 Anders als normale OLE\-Schnittstellen die verwendet werden, um die Funktionalität eines OLE\-Steuerelements, implementiert eines Verbindungspunktes zu implementieren und verfügbar gemacht, die eine Ausgangsschnittstelle ist, Aktionen für andere Objekte, z Auslösenereignissen und Änderungsbenachrichtigungen zu initiieren.  
  
 Eine Verbindung besteht aus zwei Teilen: das Objekt, das die Schnittstelle aufgerufen, die Quelle "," und das Objekt implementiert die Schnittstelle aufruft, die die Senke" auf ". Wenn Sie einen Verbindungspunkt verfügbar macht, ermöglicht eine Quelle Senken, um Verbindungen auf festzulegen.  Durch den Verbindungspunktmechanismus erhält ein Quellobjekt ein Zeiger auf die Implementierung der Senke eines Satzes Memberfunktionen.  Um beispielsweise ein Ereignis auszulösen, das von der Senke implementiert ist, kann die Quelle die entsprechende Methode der Implementierung der Senke aufrufen.  
  
 Standardmäßig `COleControl` von abgeleitete Klasse implementiert zwei Verbindungspunkte: ein für Ereignisse und eines für Benachrichtigungen für Eigenschaftenänderungen.  Diese Verbindungen werden, bzw., für Auslösen von Ereignissen und zum Benachrichtigen einer Senke verwendet \(beispielsweise, der Container des Steuerelements\) wenn ein Eigenschaftswert geändert wurde.  Unterstützung wird auch bietet, damit OLE\-Steuerelemente zusätzliche Verbindungspunkten implementieren.  Für jeden zusätzlichen Verbindungspunkt, der in der Steuerelementklasse implementiert wird, müssen Sie einen "inneres Element" deklarieren diesen implementiert der Verbindungspunkt.  Wenn Sie eine oder mehrere Verbindungspunkte implementieren, müssen Sie auch eine einzelne "Verbindungszuordnung" in der Steuerelementklasse deklarieren.  
  
 Das folgende Beispiel zeigt eine einfache Verbindungszuordnung und einen Verbindungspunkt für das `Sample` OLE\-Steuerelement und besteht aus zwei Fragmenten des Codes: der erste Teil deklariert die Verbindungszuordnung und den Punkt; das zweite implementiert diese Zuordnung und Punkt.  Das erste Fragment wird in die Deklaration der Steuerelementklasse, unter dem `protected`\-Abschnitt eingefügt:  
  
 [!CODE [NVC_MFCConnectionPoints#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#7)]  
  
 Die `BEGIN_CONNECTION_PART` und `END_CONNECTION_PART`\-Makros deklarieren eine eingebettete Klasse, `XSampleConnPt` \(abgeleitet von\) `CConnectionPoint` dieses implementiert der bestimmte Verbindungspunkt.  Wenn Sie eine `CConnectionPoint`\-Memberfunktionen überschreiben möchten oder Memberfunktionen von eigenen hinzufügen, deklarieren Sie sie zwischen diesen beiden Makros.  Beispielsweise überschreibt das `CONNECTION_IID`\-Makro die `CConnectionPoint::GetIID`\-Memberfunktion, wenn zwischen diese beiden Makros platziert wird.  
  
 Das zweite Codefragment wird in die Implementierungsdatei \(.CPP\) der Steuerelementklasse eingefügt.  Dieser Code implementiert die Verbindungszuordnung, die zusätzlichen Verbindungspunkt einschließt, `SampleConnPt`:  
  
 [!CODE [NVC_MFCConnectionPoints#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#2)]  
  
 Nachdem diese Codefragmente eingefügt wurden, macht das Beispielole\-steuerelement einen Verbindungspunkt für die **ISampleSink**\-Schnittstelle verfügbar.  
  
 In der Regel unterstützen Verbindungspunkte "Multi \- Letzteres" Element, das die Fähigkeit ist, zu mehreren Senken zu übertragen, die an die gleiche Schnittstelle verbunden werden.  Das folgende Codefragment zeigt, wie Multi \- Letzteres Element erreicht, indem es durch jede Senke auf einem Verbindungspunkt durchläuft:  
  
 [!CODE [NVC_MFCConnectionPoints#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#4)]  
  
 In diesem Beispiel wird die aktuelle ab, der von den Verbindungen auf dem `SampleConnPt` Verbindungspunkt mit einem Aufruf von `CConnectionPoint::GetConnections` festgelegt ist.  Es wird durch die Verbindungen durch und ruft `ISampleSink::SinkFunc` auf jeder aktiven Verbindung auf.  
  
 Weitere Informationen zur Verwendung von `CConnectionPoint`, finden Sie im Artikel [Verbindungspunkte](../../mfc/connection-points.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)