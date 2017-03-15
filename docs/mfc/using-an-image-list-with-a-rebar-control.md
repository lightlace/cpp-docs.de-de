---
title: "Verwenden einer Bildliste mit einem Grundleisten-Steuerelement | Microsoft Docs"
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
  - "Bilderlisten [C++], rebar-Steuerelemente"
  - "rebar-Steuerelemente, Bilderlisten"
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden einer Bildliste mit einem Grundleisten-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jedes Infoleistenband kann unter anderem ein Bild von einer entsprechenden Bildliste enthalten.  In der folgenden Prozedur werden ausführlich die erforderlichen Schritte zum Anzeigen eines Bilds in einem Infoleistenband aufgeführt.  
  
### So zeigen Sie Bilder in einem Infoleistenband  
  
1.  Hinzufügen einer Bildliste zu dem Infoleiste\-Steuerelement\-Objekt an, indem Sie einen Aufruf von [SetImageList](../Topic/CReBarCtrl::SetImageList.md) ausführen und einen Zeiger auf einer vorhandenen Bildliste übergeben.  
  
2.  Ändern Sie **REBARBANDINFO**\-Struktur, um ein Bild zuzuweisen einem Infoleistenband:  
  
    -   Legen Sie den Member auf **fMaskRBBIM\_IMAGE**, mit dem bitweisen OR\-Operators auf zusätzliche Flags für gehören wie erforderlich fest.  
  
    -   Legen Sie den `iImage` auf den Member Bildlistenindex des anzuzeigenden Bilds fest.  
  
3.  Initialisieren Sie alle verbleibenden Datenmember, wie die Größe, der Text und das Handle des enthaltenen untergeordneten Fensters, mit den notwendigen Informationen.  
  
4.  Fügen Sie das neue Band \(dem Bild\) mit einem Aufruf von [CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md) ein und die **REBARBANDINFO** \-Struktur übergeben.  
  
 Im folgenden Beispiel wird davon ausgegangen, dass ein vorhandenes Bildlistenobjekt mit zwei Bilder zum Infoleiste\-Steuerelement\-Objekt \(`m_wndReBar`\) angefügt wurde.  Ein neues Infoleistenband \(durch `rbi`\), zum ersten Bild enthalten, wird mit einem Aufruf von `InsertBand` hinzugefügt:  
  
 [!CODE [NVC_MFCControlLadenDialog#28](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#28)]  
  
## Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)