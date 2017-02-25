---
title: "Verbindungspunkte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IConnectionPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdTarget-Klasse, und Verbindungspunkte"
  - "COM, Verbindungspunkte"
  - "Verbindungspunkte [C++]"
  - "Verbindungen, Verbindungspunkte"
  - "IConnectionPoint-Schnittstelle"
  - "Schnittstellen, IConnectionPoint"
  - "MFC [C++], COM-Unterstützung"
  - "MFC COM, Verbindungspunkte"
  - "OLE COM-Verbindungspunkte"
  - "Senken, Verbindungspunkte"
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verbindungspunkte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird beschrieben, wie die Verbindung \(früher bekannt als OLE\-Verbindungspunkte\) mithilfe der MFC\-Klassen `CCmdTarget` und `CConnectionPoint` implementiert.  
  
 Früher definierte das Component Object Model \(COM\) einen allgemeinen Mechanismus \(**IUnknown::QueryInterface**\) der zulässigen Objekte, um Funktionalität in den Schnittstellen zu implementieren und verfügbar zu machen.  jedoch ein entsprechender Mechanismus, der die zulässigen Objekte, die ihre Funktion verfügbar zu machen, um bestimmte Schnittstellen aufzurufen nicht definiert wurden.  Das heißt, hatten definiertes COM, eingehende wie Zeiger auf Objekte \(Zeiger auf Schnittstellen des Objekts\) behandelt wurden, jedoch kein explizites Modell für Ausgangsschnittstellen \(Zeiger, die das Objekt mit den Schnittstellen anderer Objekte enthält\).  COM verfügt jetzt über ein Modell, aufgerufen Verbindungspunkte, das diese Funktionen unterstützt.  
  
 Eine Verbindung besteht aus zwei Teilen: das Objekt, das die Schnittstelle aufgerufen, die Quelle und das Objekt die Schnittstelle implementiert, aufgerufen die Senke aufruft.  Ein Verbindungspunkt ist die Schnittstelle, der die Quelle verfügbar gemacht wird.  Durch sie einen Verbindungspunkt verfügbar macht, kann eine Quelle Senken, um Verbindungen zu sich herzustellen \(die Quelle\).  Durch den Verbindungspunktmechanismus \(die **IConnectionPoint** \- Schnittstelle\), wird ein Zeiger auf die Senkenschnittstelle die übergeben.  Dieser Zeiger stellt die Quelle mit Zugriff auf die Implementierung der Senke von Memberfunktionen.  Um beispielsweise ein Ereignis auszulösen, das durch die Senke implementiert wird, ist die Quelle die entsprechende Methode der Senke aufrufen.  Die folgende Abbildung zeigt den Ereignisthemen Verbindungspunkt nur.  
  
 ![Implementierter Verbindungspunkt](../mfc/media/vc37lh1.png "vc37LH1")  
Implementierter Verbindungspunkt  
  
 MFC implementiert dieses Modell in den Klassen [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) und [CCmdTarget](../mfc/reference/ccmdtarget-class.md).  Die Klassen, die von **CConnectionPoint**  abgeleitet werden, implementieren die **IConnectionPoint**\-Schnittstelle, verwendet, um zu Verbindungspunkten anderen Objekten verfügbar.  Die Klassen, die von `CCmdTarget` abgeleitet werden, implementieren die **IConnectionPointContainer**\-Schnittstelle, die alle verfügbaren Verbindungspunkte eines Objekts aufgelistet werden können oder einen bestimmten Verbindungspunkt sucht.  
  
 Für jeden Verbindungspunkt, der in der Klasse implementiert wird, müssen Sie einen inneren Element deklarieren, die den Verbindungspunkt implementiert.  Wenn Sie eine oder mehrere Verbindungspunkte implementieren, müssen Sie eine einzelne Verbindungszuordnung in der Klasse auch deklarieren.  Eine Verbindungszuordnung ist eine Tabelle von Verbindungspunkten, die das ActiveX\-Steuerelement unterstützt werden.  
  
 Die folgenden Beispiele zeigen eine einfache Verbindungszuordnung und einen Verbindungspunkt.  Das erste Beispiel deklariert die Verbindungszuordnung und den Punkt; das zweite Beispiel implementiert die Belegung und den Punkt.  Beachten Sie, dass `CMyClass` `CCmdTarget` sein muss abgeleiteten Klasse.  Im ersten Beispiel wird Code in die Klassendeklaration, unter dem **protected** \-Abschnitt eingefügt:  
  
 [!CODE [NVC_MFCConnectionPoints#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#1)]  
  
 `BEGIN_CONNECTION_PART` und der **END\_CONNECTION\_PART** \-Makros deklarieren eine eingebettete Klasse, `XSampleConnPt` \(abgeleitet von `CConnectionPoint`\), die diesen bestimmten Verbindungspunkt implementiert.  Falls eine `CConnectionPoint`\-Memberfunktionen überschreiben oder Memberfunktionen von eigenen hinzufügen möchten, deklarieren Sie es zwischen diesen beiden Makros.  So überschreibt beispielsweise das `CONNECTION_IID`\-Makro die Memberfunktion `CConnectionPoint::GetIID`, wenn zwischen diese beiden Makros eingefügt wird.  
  
 Im zweiten Beispiel wird Code in der Implementierungsdatei des Steuerelements \(CPP\-Datei\) eingefügt.  Dieser Code implementiert die Verbindungszuordnung, die den Verbindungspunkt enthält, `SampleConnPt`:  
  
 [!CODE [NVC_MFCConnectionPoints#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#2)]  
  
 Wenn Ihre Klasse mehr als einen Verbindungspunkt hat, fügen Sie zusätzliche `CONNECTION_PART` zwischen Makros `BEGIN_CONNECTION_MAP` und den `END_CONNECTION_MAP`\-Makros.  
  
 Abschließend fügen Sie `EnableConnections` einen Aufruf im Konstruktor der Klasse hinzu.  Beispiel:  
  
 [!CODE [NVC_MFCConnectionPoints#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#3)]  
  
 Nachdem dieser Code eingefügt wurde, das `CCmdTarget` abgeleitete Klasse macht einen Verbindungspunkt für die **ISampleSink** \-Schnittstelle verfügbar.  Die folgende Abbildung veranschaulicht dieses Beispiel.  
  
 ![Mithilfe von MFC implementierter Verbindungspunkt](../mfc/media/vc37lh2.png "vc37LH2")  
Ein Verbindungspunkt implementiert mit MFC  
  
 Normalerweise unterstützen Verbindungspunkte "Multi \- Guss \- Element" \- die Möglichkeit, das mehreren Senken zu übertragen, die mit der gleichen Schnittstelle verbunden werden.  Im folgenden Beispielsfragment wird, die von Multicastdelegaten das Traversieren von Senke jede auf einen Verbindungspunkt:  
  
 [!CODE [NVC_MFCConnectionPoints#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#4)]  
  
 In diesem Beispiel ruft die aktuelle ab, der von den Verbindungen in dem Verbindungspunkt mit `SampleConnPt` einem Aufruf für `CConnectionPoint::GetConnections` festgelegt wird.  Anschließend durchläuft die Links durch und ruft **ISampleSink::SinkFunc** auf jeder aktiven Verbindung auf.  
  
## Siehe auch  
 [MFC COM](../mfc/mfc-com.md)