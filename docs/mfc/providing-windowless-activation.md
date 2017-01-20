---
title: "Bereitstellung von fensterloser Aktivierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Aktivierung [C++], MFC-ActiveX-Steuerelemente"
  - "Aktivierung [C++], Windowless"
  - "MFC ActiveX-Steuerelemente [C++], Aktivieren von Optionen"
  - "Fensterlose Aktivierung von MFC-ActiveX-Steuerelementen"
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Bereitstellung von fensterloser Aktivierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fenstererstellungscode \(das heißt, alle, die eintritt, wenn Sie **CreateWindow** aufrufen\), ist aufwändig auszuführen.  Ein Steuerelement, das ein Fenster auf dem Bildschirm wird, muss Meldungen zum Fenster verwalten.  Fensterlose Steuerelemente sind daher schneller als Steuerelemente Fenstern.  
  
 Ein weiterer Vorteil von fensterlose Steuerelemente ist, dass, im Gegensatz zu Steuerelementen mit Fenstern, fensterlose Steuerelemente transparentes Zeichnen und Nicht rechteckige Bildschirmbereiche unterstützen.  Ein allgemeines Beispiel eines transparenten Steuerelements ist ein Textsteuerelement mit einem transparenten Hintergrund.  Die Steuerelemente zeichnen den Text aber nicht den Hintergrund, sodass was unter den Textshows durch ist.  Neuere Formularen häufig nutzen Nicht rechteckige Steuerelemente, z Pfeile und eine runde Schaltflächen.  
  
 Häufig erfordert ein Steuerelement ein Fenster von eigenen und kann die Fensterdienste seines Containers stattdessen verwenden, vorausgesetzt, dass der Container geschrieben wird, um fensterlose Objekte zu unterstützen.  Fensterlose Steuerelemente sind abwärtskompatibel mit älteren Containern.  In älteren Containern, die nicht geschrieben werden, um fensterlose Steuerelemente unterstützt, stellen die fensterlose Steuerelemente ein Fenster, wenn aktiv.  
  
 Da fensterlose Steuerelemente keine eigenen Fenster haben, ist der Container der \(ein Fenster hat\), für von Diensten zur Bereitstellung zuständig, die andernfalls vom eigenen Fenster des Steuerelements bereitgestellt worden wären.  Wenn das Steuerelement den Tastaturfokus, abfragen, die Maus zu erfassen oder einem Gerätekontext abzurufen, diese Vorgänge vom Container verwaltet werden.  Der Container leitet die Benutzereingabemeldungen weiter, die an ihren Fenster zum entsprechenden fensterlose Steuerelement, mit der Schnittstelle `IOleInPlaceObjectWindowless` gesendet werden. \(Siehe das *ActiveX\-SDK*  für eine Beschreibung dieser Schnittstelle.\), erhalten `COleControl`\-Memberfunktionen diese Dienste vom Container auf.  
  
 Um das Steuerelement erstellen fensterlose Aktivierung zu verwenden, schließen Sie das Flag **windowlessActivate**  im Satz von Flags ein, die von [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) zurückgegeben werden.  Beispiel:  
  
 [!CODE [NVC_MFC_AxOpt#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#5)]  
[!CODE [NVC_MFC_AxOpt#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#6)]  
[!CODE [NVC_MFC_AxOpt#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#7)]  
  
 Der Code, mit dem dieses Flags einzuschließen wird automatisch generiert, wenn Sie die Option **Fensterlose Aktivierung** auf der Seite [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC\-ActiveX\-Steuerelement\-Assistenten auswählen.  
  
 Wenn fensterlose Aktivierung aktiviert wird, delegiert der Container Eingabemeldungen zur `IOleInPlaceObjectWindowless`\-Schnittstelle des Steuerelements.  `COleControl` Implementierung dieser Schnittstelle leitet die Meldungen durch die Meldungszuordnung des Steuerelements weiter, nachdem die Mauskoordinaten entsprechend anpassen.  Sie können die Meldungen wie gewöhnliche Fenstermeldungen verarbeiten, indem Sie den entsprechenden Einträgen zur Meldungszuordnung hinzufügen.  In den Handler für diese Meldungen, vermeiden Sie es, die `m_hWnd`\-Membervariable \(oder eine Memberfunktion, die sie verwendet\), ohne zuerst die Prüfung zu verwenden, dass der Wert nicht **NULL** ist.  
  
 `COleControl` stellt Memberfunktionen, die die Mausauswahl, den Tastaturfokus, den Bildlauf und andere Fensterdienste vom Container nach Bedarf aufrufen und enthält:  
  
-   [GetFocus](../Topic/COleControl::GetFocus.md), [SetFocus](../Topic/COleControl::SetFocus.md)  
  
-   [GetCapture](../Topic/COleControl::GetCapture.md), [SetCapture](../Topic/COleControl::SetCapture.md), [ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)  
  
-   [GetDC](../Topic/COleControl::GetDC.md), [ReleaseDC](../Topic/COleControl::ReleaseDC.md)  
  
-   [InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)  
  
-   [ScrollWindow](../Topic/COleControl::ScrollWindow.md)  
  
-   [GetClientRect](../Topic/COleControl::GetClientRect.md)  
  
 In den fensterlose Steuerelemente sollten Sie die Memberfunktionen `COleControl` anstelle entsprechender `CWnd`\-Memberfunktionen oder ihrer verwandten Win32\-API\-Funktionen immer verwenden.  
  
 Sie sollten ein fensterloses Steuerelement das Ziel eines Drag & Drop\-Vorgangs sein.  Normalerweise würde diese erfordern, dass das Fenster des Steuerelements als Ablageziel registriert wird.  Da das Steuerelement kein Fenster von eigenen verfügt, verwendet der Container ein eigenes Fenster als Ablageziel.  Das Steuerelement stellt eine Implementierung der Schnittstelle `IDropTarget`, zu der der Container Aufrufe zur richtigen Zeit delegieren kann.  Um diese Schnittstelle dem Container verfügbar zu machen, überschreiben Sie unter [COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md).  Beispiel:  
  
 [!CODE [NVC_MFC_AxOpt#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#8)]  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)