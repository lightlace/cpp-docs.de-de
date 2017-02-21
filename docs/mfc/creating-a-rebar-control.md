---
title: "Erstellen eines Grundleisten-Steuerelements | Microsoft Docs"
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
  - "CReBarCtrl-Klasse, Erstellen"
  - "rebar-Steuerelemente, Erstellen"
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Erstellen eines Grundleisten-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CReBarCtrl](../mfc/reference/crebarctrl-class.md) sollten Objekte erstellt werden, bevor das übergeordnete Objekt sichtbar ist.  Dies hält die Möglichkeiten von Zeichnenproblemen.  
  
 Beispielsweise sind die Infoleistensteuerelemente \(verwendet in den Rahmenfensterobjekten\) als übergeordnete Fenster für Symbolleisten\-Steuerelemente häufig verwendet.  Daher ist das übergeordnete Element des Infoleiste\-Steuerelements das Rahmenfensterobjekt.  Da das Rahmenfensterobjekt das übergeordnete Element ist, ist die `OnCreate`\-Memberfunktion \(übergeordneten\) ein ausgezeichneter Platz, um den Infoleiste\-Steuerelements zu erstellen.  
  
 Um ein `CReBarCtrl`\-Objekt zu verwenden, führen Sie normalerweise folgende Schritte:  
  
### Um ein CReBarCtrl\-Objekt verwenden  
  
1.  Erstellen Sie das Objekt unter [CReBarCtrl](../mfc/reference/crebarctrl-class.md).  
  
2.  Rufen Sie [Erstellen](../Topic/CReBarCtrl::Create.md) auf, um die Windows\-Infoleistengemeinsame allgemeinen ToolTip\-Steuerelement zu erstellen und auf das Objekt `CReBarCtrl` anzufügen und allen gewünschten Formate angeben.  
  
3.  Laden Sie eine Bitmap, mit einem Aufruf von [CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md), als Hintergrund des Infoleiste\-Steuerelement\-Objekts verwendet werden.  
  
4.  Erstellen und initialisieren Sie alle Objekte des untergeordneten Fensters \(Symbolleisten, Dialogfeldkontrollen, usw.\). die vom Infoleiste\-Steuerelement\-Objekt enthalten sind.  
  
5.  Initialisieren Sie eine **REBARBANDINFO**\-Struktur mit den erforderlichen Informationen für das einzufügende Band, näherungsweise.  
  
6.  Rufen Sie [InsertBand](../Topic/CReBarCtrl::InsertBand.md) auf, um vorhandene untergeordnete Fenster \(wie `m_wndReToolBar`\) in das neue Grundleistensteuerelement einzufügen.  Weitere Informationen zum Einfügen stellt in ein vorhandenes Grundleistensteuerelement, finden Sie unter [Infoleistensteuerelemente und Bänder](../mfc/rebar-controls-and-bands.md) mit ein Band.  
  
## Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)