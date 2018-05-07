---
title: Stile für das Statussteuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c1044c82c2864d71047e4fe3c7461d03a17d9d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="styles-for-the-progress-control"></a>Stile für das Statussteuerelement
Beim anfänglichen Erstellen des Statussteuerelements ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md#create)), verwenden Sie die `dwStyle` Parameter, um das gewünschte Fensterstile für Ihre Statussteuerelement anzugeben. In der folgenden Liste sind die entsprechenden Fensterstile. Das Steuerelement ignoriert alle Fensterstil als diejenigen, die hier aufgeführten. Sie sollten immer das Steuerelement als untergeordnetes Fenster, in der Regel von einem Dialogfeld übergeordnetes Element erstellen.  
  
|Fensterstil|Effekt|  
|------------------|------------|  
|`WS_BORDER`|Erstellt einen Rahmen um das Fenster an.|  
|**WS_CHILD**|Erstellt ein untergeordnetes Fenster (sollte immer verwendet werden, für die `CProgressCtrl`).|  
|**WS_CLIPCHILDREN**|Schließt den Bereich von untergeordnete Fenster belegt wird, wenn Sie innerhalb des übergeordneten Fensters zeichnen. Wird verwendet, wenn Sie das übergeordnete Fenster erstellen.|  
|**WS_CLIPSIBLINGS**|Kappt untergeordnete Fenster relativ zueinander.|  
|**WS_DISABLED**|Erstellt ein Fenster, das anfänglich deaktiviert ist.|  
|**WS_VISIBLE**|Erstellt ein Fenster, das anfänglich sichtbar ist.|  
|**WS_TABSTOP**|Gibt an, dass das Steuerelement den Fokus, beim Drücken der TAB-Taste erhalten kann, um darauf zu verschieben.|  
  
 Darüber hinaus können Sie angeben, zwei Formate, die nur für das Statussteuerelement gelten `PBS_VERTICAL` und `PBS_SMOOTH`.  
  
 Verwendung `PBS_VERTICAL` um das Steuerelement vertikal statt horizontal auszurichten. Verwendung `PBS_SMOOTH` das Steuerelement vollständig gefüllt wird, anstatt kleine abgegrenzt Quadrate, die inkrementell füllen Sie das Steuerelement anzeigen.  
  
 Ohne `PBS_SMOOTH` Format:  
  
 ![Standardstil der Statusleiste](../mfc/media/vc4ruw1.gif "vc4ruw1")  
  
 Mit `PBS_SMOOTH` und `PBS_VERTICAL` Formatvorlagen:  
  
 ![Balkenart, glatt und vertikal Status](../mfc/media/vc4ruw2.gif "vc4ruw2")  
  
 Weitere Informationen finden Sie unter [Fensterstile](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) in der *MFC-Referenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)

