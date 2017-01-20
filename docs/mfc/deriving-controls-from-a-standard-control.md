---
title: "Ableiten von Steuerelementen von einem Standardsteuerelement"
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
  - "Allgemeine Steuerelemente [C++], Ableiten von"
  - "Steuerelemente [MFC], Abgeleitet"
  - "Abgeleitete Steuerelemente"
  - "Standardsteuerelemente"
  - "Standardsteuerelemente, Ableiten von Steuerelementen von"
  - "Allgemeine Windows-Steuerelemente [C++], Ableiten von"
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Ableiten von Steuerelementen von einem Standardsteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie mit [CWnd](../mfc/reference/cwnd-class.md) abgeleitete Klasse, können Sie ein Verhalten des Steuerelements ändern, indem Sie eine neue Klasse aus einer Klasse des vorhandenen Steuerelements berechnen.  
  
### So eine abgeleitete Steuerelementklasse erstellen  
  
1.  Ableiten der Klasse aus einer Klasse des vorhandenen Steuerelements und Überschreiben Sie optional die **Erstellen**\-Memberfunktion, sodass sie die erforderlichen Argumente der Basisklassen **Erstellen**\-Funktion bereitstellt.  
  
2.  Erstellen Sie Meldungshandlermemberfunktionen und \-Meldungszuordnungseinträge bereit, um das Verhalten des Steuerelements als Reaktion auf Windows\-Meldungen bestimmte zu ändern.  Siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
3.  Erstellen neuer Memberfunktionen bereit, um die Funktionalität des Steuerelements erweitern \(optional\).  
  
 Verwenden eines abgeleiteten Steuerelements in einem Dialogfeld erfordert zusätzliche Arbeit.  Die Typen und Position der Steuerelemente in einem Dialogfeld werden normalerweise in einer Dialogfeldvorlagenressource angegeben.  Wenn Sie eine abgeleitete Steuerelementklasse erstellen, können Sie sie in einer Dialogfeldvorlage nicht angeben, da der Ressourcencompiler nichts über die abgeleitete Klasse weiß.  
  
#### Um das Steuerelement abgeleitetes in einem Dialogfeld platzieren  
  
1.  Betten Sie ein Objekt der abgeleitete Steuerelementklasse in der Deklaration der abgeleiteten Dialogfeldklasse ein.  
  
2.  Überschreiben Sie die Memberfunktion `OnInitDialog` in der Dialogfeldklasse, um die `SubclassDlgItem` für Memberfunktion das abgeleitete Steuerelement aufzurufen.  
  
 `SubclassDlgItem` "ordnet dynamisch" ein Steuerelement konvertiert, das von einer Dialogfeldvorlage erstellt wird.  Wenn ein Steuerelement dynamisch als Unterklasse definiert ist, verknüpfen Sie in Windows, verarbeiten einige Meldungen in Ihrer eigenen Anwendung, dann werden die verbleibenden Meldungen an Windows weiter.  Weitere Informationen finden Sie in [SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md)\-Memberfunktion der `CWnd`\-Klasse in der *MFC\-Referenz*.  Das folgende Beispiel zeigt, wie Sie eine Überschreibung von `OnInitDialog` schreiben, um `SubclassDlgItem` aufzurufen:  
  
 [!CODE [NVC_MFCControlLadenDialog#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#3)]  
  
 Da das abgeleitete Steuerelement in Dialogklasse eingebettet wird, wird dieses erstellt, wenn das Dialogfeld erstellt wird, und es zerstört wird, wenn das Dialogfeld zerstört wird.  Vergleichen Sie diesen Code zum Beispiel unter [Steuerelemente von Hand hinzufügen](../mfc/adding-controls-by-hand.md).  
  
## Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)