---
title: "Implementieren von Arbeitsbereichen in Listensteuerelementen"
ms.custom: na
ms.date: "12/14/2016"
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
  - "List-Steuerelemente, Arbeitsbereiche"
  - "Arbeitsbereiche in Listensteuerelement"
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Implementieren von Arbeitsbereichen in Listensteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig ordnet ein Listensteuerelement alle Elemente in einer Standardrasterweise an.  Allerdings wird eine andere Methode, Arbeitsbereiche unterstützt, die die Listenelemente rechteckige in Gruppen angeordnet werden.  Ein Bild eines Listensteuerelements, die Arbeitsbereiche implementiert, finden Sie mit Listenansicht\-Steuerelementen in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Arbeitsbereiche sind nur sichtbar, wenn das Listensteuerelement im Symbol oder im kleinen Symbolmodus ist.  werden jedoch alle aktuellen Arbeitsbereiche beibehalten, wenn die Ansicht den Berichts\- oder Listenmodus gewechselt wird.  
  
 Arbeitsbereiche können verwendet werden, um einen leeren Bereich anzuzeigen \(links, oben und\/oder rechts von Elementen\), oder führen Sie eine horizontale Bildlaufleiste angezeigt, als sie normalerweise keine geben würde.  Eine weitere allgemeine Verwendung besteht, mehrere Arbeitsbereiche erstellen möchten, auf die Elemente verschoben werden oder verworfen werden können.  Mit dieser Methode können Sie Bereiche einer einzelnen Ansicht erstellen, die verschiedene Bedeutungen haben.  Der Benutzer kann dann die Elemente gliedern, indem er sie in einem anderen Bereich eingefügt hat.  Ein Beispiel hierfür ist eine Ansicht eines Dateisystems sein, das einen Bereich für Datei mit Lese\-\/Schreibzugriff und einen anderen Bereich für schreibgeschützte Dateien verfügt.  Wenn ein file\-Element in schreibgeschützten Bereich verschoben wurden, wird es automatisch als schreibgeschützt festgelegt.  Das Verschieben einer Datei im schreibgeschützten Bereich in den Lese\-Schreibbereich würde den Dateilese\-\/schreibzugriff machen.  
  
 `CListCtrl` stellt mehrere Memberfunktionen zum Erstellen und Verwalten von Arbeitsbereichen im Listensteuerelement bereit.  [GetWorkAreas](../Topic/CListCtrl::GetWorkAreas.md) und [SetWorkAreas](../Topic/CListCtrl::SetWorkAreas.md) ruft ab und legen ein Array `CRect`\-Objekte \(oder `RECT`\-Strukturen\) fest, die die derzeit implementierten Arbeitsbereiche für Ihr Listensteuerelement speichern.  Außerdem ruft [GetNumberOfWorkAreas](../Topic/CListCtrl::GetNumberOfWorkAreas.md) die aktuelle Anzahl von Arbeitsbereichen für Ihr Listensteuerelement ab \(standardmäßig, gleich\).  
  
## Elemente und Arbeitsbereichen  
 Wenn ein Arbeitsbereich erstellt wird, werden Elemente, die innerhalb des Arbeitsbereichs liegen, Member davon.  Auch wenn ein Element in einen Arbeitsbereich verschoben wird, wird es einen Member des Arbeitsbereichs, auf der es verschoben wurde.  Wenn ein Element nicht innerhalb eines Arbeitsbereichs liegt, wird es automatisch einen Member des ersten \(Index 0\) Arbeitsbereichs.  Wenn Sie ein Element erstellen und sie in einem bestimmten Arbeitsbereichs platzieren möchten, müssen Sie das Element erstellen und in den gewünschten Arbeitsbereich mit einem Aufruf an [SetItemPosition](../Topic/CListCtrl::SetItemPosition.md) bewegen.  Das zweite folgende Beispiel veranschaulicht diese Technik.  
  
 Das nächste Beispiel implementiert vier Arbeitsbereiche \(`rcWorkAreas`\), der gleichen Größe mit einem Pixel\-weiten Rahmen 10 um die einzelnen Arbeitsbereiche, in einem Listensteuerelement \(`m_WorkAreaListCtrl`\).  
  
 [!CODE [NVC_MFCControlLadenDialog#20](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#20)]  
  
 Der Aufruf von [ApproximateViewRect](../Topic/CListCtrl::ApproximateViewRect.md) wurde erstellt, um eine Schätzung der Gesamtfläche abzurufen, die erforderlich war, um alle Elemente in einem Bereich anzeigen.  Diese Schätzung ist dann in vier Bereiche unterteilt und aufgefüllt mit einem Rahmen Pixel\-weiten 5.  
  
 Im folgenden Beispiel wird jeder Gruppe \(`rcWorkAreas`\) und den Aktualisierungen die vorhandenen Listenelemente die Steuerelementansicht \(`m_``WorkAreaListCtrl`\) zu den Auswirkungen abzuschließen.  
  
 [!CODE [NVC_MFCControlLadenDialog#21](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#21)]  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)