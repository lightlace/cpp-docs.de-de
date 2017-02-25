---
title: "OLE-Steuerelementklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Klassen [C++]"
  - "ActiveX-Steuerelementklasse [C++]"
  - "ActiveX-Steuerelemente [C++], OLE-Steuerelementklassen"
  - "Benutzerdefinierte Steuerelemente [MFC], Klassen"
  - "OLE-Steuerelementklassen [C++]"
  - "OLE-Steuerelemente [C++], Klassen"
  - "Wiederverwendbare Komponentenklassen"
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-Steuerelementklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese sind die primären Klassen, die Sie verwenden, wenn Sie OLE\-Steuerelemente schreiben.  Die `COleControlModule`\-Klasse in einem OLE\-Steuerelement\-Modul ist wie die [CWinApp](../mfc/reference/cwinapp-class.md)\-Klassen in einer Anwendung.  Jedes Modul implementiert eine oder mehrere OLE\-Steuerelemente; Diese Steuerelemente werden durch `COleControl`\-Objekte dargestellt.  Diese Steuerelemente sind deren Container mit `CConnectionPoint`\-Objekte kommunizieren.  
  
 Die `CPictureHolder` und `CFontHolder`\-Klassen kapseln COM\-Schnittstellen für Bilder und Schriftarten, während die `COlePropertyPage` und `CPropExchange`\-Klassen Ihnen helfen, Eigenschaftenseiten und Eigenschaftenpersistenz für das Steuerelement zu implementieren.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 Ersetzt `CWinApp` die Klasse des OLE\-Steuerelement\-Modul.  Leiten Sie von der `COleControlModule`\-Klasse, um ein OLE\-Steuerelement\-Modulobjekt zu entwickeln.  Es stellt Memberfunktionen für das Initialisieren des Moduls des OLE\-Steuerelements bereit.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 Leiten Sie von der `COleControl`\-Klasse, um ein OLE\-Steuerelement zu entwickeln.  Ist von `CWnd`, erbt diese Klasse die gesamte Funktionalität eines Windows\-Fensterobjekts sowie zusätzliche OLE\-Besonderefunktionalität, wie Auslösen der Ereignisse und die Fähigkeit, Methoden und Eigenschaften zu unterstützen.  
  
 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)  
 Die `CConnectionPoint`\-Klasse definiert einen speziellen Typ Schnittstelle verwendet, um mit anderen OLE\-Objekten zu kommunizieren, einen Verbindungspunkt bezeichnet.  Ein Verbindungspunkt implementiert eine Ausgangsschnittstelle, ist die, Aktionen auf andere Objekte, wie Auslösenereignissen und Änderungsbenachrichtigungen zu initiieren.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Kapselt die Funktionalität eines Windows\-Bildobjekts und der `IPicture` COM\-Schnittstelle; verwendet, um die benutzerdefinierte Eigenschaft eines OLE\-Steuerelements zu implementieren.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Kapselt die Funktionalität eines Windows\-Schriftartobjekts und der `IFont` COM\-Schnittstelle; verwendet, um die vordefinierte Schriftarteigenschaft eines OLE\-Steuerelements zu implementieren.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Zeigt die Eigenschaften eines OLE\-Steuerelements in einer grafischen Oberfläche an, ähnlich einem Dialogfeld.  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 Unterstützt die Implementierung der Eigenschaftenpersistenz für die OLE\-Steuerelemente.  Analog [CDataExchange](../mfc/reference/cdataexchange-class.md) für Dialogfelder.  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 Nimmt einen Moniker oder eine Zeichenfolgendarstellung, die er in einen Moniker machen kann, und bindet sie synchron den Stream, für den der Moniker ein Name ist.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 Funktioniert auf ähnliche Weise zu `CMonikerFile`; jedoch bindet sie den Moniker asynchron zum Stream, für den der Moniker ein Name ist.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 Implementiert eine OLE\-Steuerelementeigenschaft, die asynchron geladen werden kann.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 Implementiert eine asynchron übertragene und in einer Arbeitsspeicherdatei zwischengespeicherte OLE\-Steuerelementeigenschaft.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Ermöglicht einem aktiven Dokument, um Befehle zu empfangen, die aus der Benutzeroberfläche des Containers \(wie FileNew, Öffnen, Drucken, usw.\) stammen, und können einem Container, um Befehle zu empfangen, die aus der aktuellen Benutzeroberfläche des Dokuments ausgelöst werden.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 Funktioniert mit Arrays eines beliebigen Typs und Dimensionsgefühl.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)