---
title: "Stile f&#252;r das Statussteuerelement | Microsoft Docs"
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
  - "CProgressCtrl-Klasse, Formate"
  - "PBS_SMOOTH-Format"
  - "PBS_VERTICAL-Format"
  - "Statussteuerelemente [C++], Formate"
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Stile f&#252;r das Statussteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie das Statussteuerelement \([CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)\) erstellen, verwenden Sie den Parameter `dwStyle`, um den gewünschten Fensterstilen für das Statussteuerelement anzugeben.  Die folgende Liste führt die zutreffenden Fensterstile aufgeführt.  Das Steuerelement ignoriert jeden Fensterstil als die, die im Folgenden aufgeführt werden.  Sie sollten das Steuerelement als untergeordnetes Fenster, normalerweise einem Dialogfeldelternteils immer erstellen.  
  
|Fensterstil|Auswirkung|  
|-----------------|----------------|  
|`WS_BORDER`|Erstellt einen Rahmen um das Fenster.|  
|**WS\_CHILD**|Stellt ein untergeordnetes Fenster erstellt \(sollte für `CProgressCtrl` immer verwendet werden\).|  
|**WS\_CLIPCHILDREN**|Schließt den Bereich aus, der über untergeordnete Fenster angezeigt wird, wenn Sie innerhalb des übergeordneten Fensters zeichnen.  Wird verwendet, wenn Sie das übergeordnete Fenster erstellen.|  
|**WS\_CLIPSIBLINGS**|Schneidet untergeordnete Fenster relativ zueinander ab.|  
|**WS\_DISABLED**|Erstellt ein Fenster, das zunächst deaktiviert wird.|  
|**WS\_VISIBLE**|Erstellt ein Fenster, das zuerst sichtbar ist.|  
|**WS\_TABSTOP**|Gibt an, dass das Steuerelement Fokus erhalten kann, wenn der Benutzer direkt zu ihr die TAB\-TASTE drückt.|  
  
 Sie können zusätzlich zwei Formate angeben, die nur auf das Statussteuerelement \-, `PBS_VERTICAL` \- und `PBS_SMOOTH` gelten.  
  
 Verwenden Sie `PBS_VERTICAL`, um das Steuerelement, horizontal statt vertikal auszurichten.  Verwenden Sie `PBS_SMOOTH`, um das Steuerelement vollständig ausgefüllt, anstatt, kleine Quadrate abgegrenzte anzeigt, die inkrementell das Steuerelement füllen.  
  
 Ohne `PBS_SMOOTH` Format:  
  
 ![Standardstil der Statusleiste](../mfc/media/vc4ruw1.png "vc4RUW1")  
  
 Mit `PBS_SMOOTH` und `PBS_VERTICAL` Stile:  
  
 ![Stil der Statusanzeige, glatt und vertikal](../mfc/media/vc4ruw2.png "vc4RUW2")  
  
 Weitere Informationen finden Sie unter [Fensterstile](../mfc/reference/frame-window-styles-mfc.md) in der *MFC\-Referenz*.  
  
## Siehe auch  
 [Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)