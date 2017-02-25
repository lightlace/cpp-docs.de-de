---
title: "MFC-ActiveX-Steuerelemente: Optimierung | Microsoft Docs"
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
  - "Gerätekontexte, ungeschnitten für MFC-ActiveX-Steuerelemente"
  - "Flimmerfreie ActiveX-Steuerelemente"
  - "MFC-ActiveX-Steuerelemente, aktiver/inaktiver Zustand"
  - "MFC-ActiveX-Steuerelemente, flimmerfrei"
  - "MFC-ActiveX-Steuerelemente, Mausinteraktion"
  - "MFC-ActiveX-Steuerelemente, Optimieren"
  - "MFC-ActiveX-Steuerelemente, Windowless"
  - "Optimierung, ActiveX-Steuerelemente"
  - "Optimieren der Leistung, ActiveX-Steuerelemente"
  - "Leistung, ActiveX-Steuerelemente"
  - "fensterlose MFC-ActiveX-Steuerelemente"
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# MFC-ActiveX-Steuerelemente: Optimierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt Techniken, die Sie verwenden können, um die ActiveX\-Steuerelemente für eine bessere Leistung zu optimieren.  
  
 Die Themen [Deaktivieren der Option Aktivieren, wenn sichtbar](../mfc/turning-off-the-activate-when-visible-option.md) und [Bereitstellen von Maus\-Interaktion, wenn inaktiv](../mfc/providing-mouse-interaction-while-inactive.md) erläutert werden Steuerelemente, die kein Fenster erstellen, bis aktiviert.  Das Thema [für die fensterlose Aktivierung](../mfc/providing-windowless-activation.md) erläutert Steuerelemente, die niemals ein Fenster erstellen, selbst wenn sie aktiviert sind.  
  
 Windows haben zwei signifikante Nachteile für OLE\-Objekte: sie verhindern Objekte am Sein transparent oder Nicht rechteckige, wenn aktiv, und fügen sie einem großen Aufwand der Instanziierung und Anzeige der Steuerelemente hinzu.  In der Regel ist das Erstellen eines Fensters 60 Prozent Erstellungszeitpunkt eines Steuerelements.  Mit einem einzelnen freigegebenen Fenster \(üblicherweise des Containers\) und einem weiterleitendem Code empfängt ein Steuerelement dieselben Fensterdienstleistungen, ohne im Allgemeinen einen Leistungsrückgang.  Ein Fenster haben sich größtenteils unnötiger Aufwand für das Objekt.  
  
 Einige Optimierungen nicht notwendigerweise die Leistung verbessert, wenn das Steuerelement in bestimmten Containern verwendet wird.  Beispielsweise unterstützten die Container, die vor 1996 freigegeben wurden, nicht fensterlose Aktivierung, daher stellt das Implementieren dieser Funktion keinen Vorteil in älteren Containern.  Allerdings unterstützt fast jeder Container Dauerhaftigkeit, sodass verbessert das Optimieren des Persistenzcodes wahrscheinlich die Leistung des Steuerelements in einem Container.  Wenn das Steuerelement speziell vorgesehen ist, mit einem bestimmten Typ Container verwendet werden, können Sie überprüfen, das von diesen Optimierungen durch diesen Container unterstützt wird.  Im Allgemeinen jedoch sollten Sie versuchen, möglichst viel dieser Techniken zu implementieren, wie zu dem bestimmten Steuerelement gelten, das Steuerelement zu gewährleisten so gut ausgeführt, wie er möglicherweise in einer großen Auswahl Containern kann.  
  
 Sie können viele dieser Optimierungen durch [MFC\-ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md), auf der Seite [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) implementieren.  
  
### Optimierungs\-Optionen MFC\-ActiveX\-Steuerelement\-Assistenten\-OLE  
  
|Steuerelementeinstellung im MFC\-ActiveX\-Steuerelement\-Assistenten|Aktion|Weitere Informationen|  
|--------------------------------------------------------------------------|------------|---------------------------|  
|Kontrollkästchen **Aktivieren, wenn sichtbar**|Clear|[Deaktivieren der Option Aktivieren, wenn sichtbar](../mfc/turning-off-the-activate-when-visible-option.md)|  
|Kontrollkästchen **Fensterlose Aktivierung**|Auswählen|[für die fensterlose Aktivierung](../mfc/providing-windowless-activation.md)|  
|Kontrollkästchen **Nicht\-geschnittener Gerätekontext**|Auswählen|[Verwenden eines ungestutzten Gerätekontexts](../mfc/using-an-unclipped-device-context.md)|  
|Kontrollkästchen **Flimmerfreie Aktivierung**|Auswählen|[Bereitstellen der flimmerfreien Aktivierung](../mfc/providing-flicker-free-activation.md)|  
|Kontrollkästchen **Mauszeiger\-Benachrichtigung wenn inaktiv**|Auswählen|[Bereitstellen von Maus\-Interaktion, wenn inaktiv](../mfc/providing-mouse-interaction-while-inactive.md)|  
|Kontrollkästchen **Optimierter Zeichencode**|Auswählen|[Optimieren der Steuerzeichnung](../mfc/optimizing-control-drawing.md)|  
  
 Ausführliche Informationen über die Memberfunktionen, die diese Optimierungen implementieren, finden Sie unter [COleControl](../mfc/reference/colecontrol-class.md).  Die Memberfunktionen können durch Verwendungen, wie [Fensterlose Vorgänge](assetId:///e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) und [Deaktivierte Zeiger\-Behandlungs\-Funktionen](assetId:///e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) aufgeführt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Optimieren Dauerhaftigkeit und von Initialisierung](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [für die fensterlose Aktivierung](../mfc/providing-windowless-activation.md)  
  
-   [Deaktivieren der Option Aktivieren, wenn sichtbar](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [Bereitstellen von Maus\-Interaktion, wenn inaktiv](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [Bereitstellen der flimmerfreien Aktivierung](../mfc/providing-flicker-free-activation.md)  
  
-   [Verwenden eines ungestutzten Gerätekontexts](../mfc/using-an-unclipped-device-context.md)  
  
-   [Optimieren der Steuerzeichnung](../mfc/optimizing-control-drawing.md)  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)