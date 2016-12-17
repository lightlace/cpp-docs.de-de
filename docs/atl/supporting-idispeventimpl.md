---
title: "Supporting IDispEventImpl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, IDispEventImpl support in COM objects"
  - "BEGIN_SINK_MAP macro"
  - "event sink maps, Deklarieren"
  - "IDispEventImpl class, advising and unadvising"
  - "IDispEventImpl class, Deklarieren"
  - "SINK_ENTRY macro"
  - "Typbibliotheken, Importieren"
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Supporting IDispEventImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse [IDispEventImpl](../atl/reference/idispeventimpl-class.md) kann verwendet werden, um Unterstützung zum Demonstrieren in der ATL\-Klasse zu unterstützen.  Eine Verbindungspunktsenke ermöglicht die Klasse zur Behandlung von Ereignissen, die von externen COM\-Objekten ausgelöst werden.  Diese Verbindungspunktsenken werden mit einer Ereignissenkenzuordnung, wenn von der Klasse zugeordnet.  
  
 Um eine Verbindungspunktsenke für die Klasse richtig zu implementieren, müssen die folgenden Schritte ausgeführt werden:  
  
-   Importieren Sie die Typbibliotheken für jedes externe Objekt  
  
-   Deklarieren Sie die `IDispEventImpl`\-Schnittstellen  
  
-   Deklarieren Sie eine Ereignissenkenzuordnung  
  
-   Melden Sie sich an und benachrichtigen Sie die Verbindungspunkte ab  
  
 Die Schritte, die gehören, wenn eine Verbindungspunktsenke implementiert, werden alle erreicht, indem nur die Headerdatei \(.h\) ändert der Klasse.  
  
## Importieren der Typbibliotheken  
 Für jedes Objekt, dessen externe Ereignisse, die Sie behandeln möchten, Sie, die Typbibliothek importieren muss.  Dieser Schritt definiert die Ereignisse, die behandelt werden können und enthält Informationen, die verwendet wird, wenn die Ereignissenkenzuordnung deklariert.  Die [\#import](../preprocessor/hash-import-directive-cpp.md)\-Direktiven können verwendet werden, um dies zu erreichen.  Fügen Sie die erforderlichen \- Direktive Zeilen `#import` für jede Dispatchschnittstelle hinzu, die Sie der Headerdatei \(.h\) unterstützen der Klasse.  
  
 Im folgenden Beispiel importiert die Typbibliothek eines externen COM\-Servers \(`MSCAL.Calendar.7`\):  
  
 [!CODE [NVC_ATL_Windowing#141](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#141)]  
  
> [!NOTE]
>  Sie müssen eine separate `#import`\-Anweisung für jede externe Typbibliothek haben, die Sie unterstützen.  
  
## Deklarieren der IDispEventImpl\-Schnittstellen  
 Nachdem Sie die Typbibliotheken jeder Dispatchschnittstelle importiert haben, müssen Sie separate `IDispEventImpl`\-Schnittstellen für jede externe Dispatchschnittstelle deklarieren.  Ändern Sie die Deklaration der Klasse, indem Sie eine `IDispEventImpl`\-Schnittstellendeklaration für jedes externe Objekt hinzufügen.  Weitere Informationen zu den Parametern, finden Sie unter [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
 Der folgende Code deklariert zwei Verbindungspunktsenken, für die `DCalendarEvents`\-Schnittstelle, denn das COM\-Objekt, das von Klasse `CMyCompositCtrl2` implementiert wird:  
  
 [!CODE [NVC_ATL_Windowing#142](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#142)]  
  
## Deklarieren einer Ereignissenkenzuordnung  
 Damit die Ereignisbenachrichtigungen durch die richtige Funktion behandelt werden können, die Klasse müssen jedes Ereignis auf den richtigen Handler weitergeleitet.  Dies wird erreicht, indem eine Ereignissenkenzuordnung deklariert.  
  
 ATL stellt mehrere Makros, [BEGIN\_SINK\_MAP](../Topic/BEGIN_SINK_MAP.md), [END\_SINK\_MAP](../Topic/END_SINK_MAP.md) und [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY.md), die diese Zuordnung vereinfachen.  Das Standardformat ist, wie folgt:  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `.  .  .  //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 Das folgende Beispiel deklariert eine Ereignissenkenzuordnung mit zwei Ereignisarten:  
  
 [!CODE [NVC_ATL_Windowing#136](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#136)]  
  
 Die Implementierung ist fast vollständig.  Der letzte Schritt betrifft die Protokollierung und das Abmelden der externen Schnittstellen.  
  
## Die IDispEventImpl\-Schnittstellen anmelden und abmeldend  
 Der letzte Schritt besteht darin, eine Methode implementieren, die \(oder abmelden\) alle Verbindungspunkte zu den richtigen Zeiten anmeldet.  Anmeldendes dieses muss vor Kommunikation zwischen Clients und dem Objekt ausgeführt werden stattfinden.  Bevor das Objekt sichtbar ist, wird jede externe Dispatchschnittstelle, die durch das Objekt unterstützt wird, für Ausgangsschnittstellen abgefragt.  Eine Verbindung wird hergestellt und ein Verweis auf die Ausgangsschnittstelle wird verwendet, um Ereignisse vom Objekt behandelt.  Diese Prozedur wird als "anmeldend."  
  
 Nachdem das Objekt mit den externen Schnittstellen beendet ist, sollten die Ausgangsschnittstellen benachrichtigt, dass sie nicht mehr von der Klasse verwendet werden.  Dieser Prozess wird als "abmeldend."  
  
 Aufgrund der eindeutigen Art von COM\-Objekten, ist dieses Verfahren, ausführlich und Ausführen, zwischen Implementierungen.  Diese Informationen sind im Rahmen dieses Themas und nicht behoben werden.  
  
## Siehe auch  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)