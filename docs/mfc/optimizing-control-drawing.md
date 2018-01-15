---
title: Optimieren der Steuerelementdarstellung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b3e79a7b8e539198844c106a9c41408f04d69186
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="optimizing-control-drawing"></a>Optimieren der Steuerelementdarstellung
Wenn ein Steuerelement angewiesen wird, einen Container bereitgestellte Gerätekontext gezeichnet, in der Regel wählt GDI-Objekte (z. B. Stifte, Pinseln und Schriftarten) in den Gerätekontext, führt seine Zeichenvorgänge und die vorherigen GDI-Objekte wiederhergestellt. Wenn der Container verfügt über mehrere Steuerelemente, die den gleichen Gerätekontext gezeichnet werden soll, und jedes Steuerelement auswählt, GDI-Objekte, die erforderlich ist, kann Zeit gespeichert werden, wenn die Steuerelemente nicht zuvor ausgewählten Objekte einzeln wiederherstellen. Nachdem alle Steuerelemente gezeichnet wurden, kann die ursprünglichen Objekte automatisch der Container wiederhergestellt werden.  
  
 Um zu ermitteln, ob ein Container diese Technik unterstützt, kann ein Steuerelement Aufrufen der [COleControl::IsOptimizedDraw](../mfc/reference/colecontrol-class.md#isoptimizeddraw) Memberfunktion. Wenn diese Funktion gibt **"true"**, das Steuerelement den normalen Schritt bei der Wiederherstellung der zuvor ausgewählten Objekte überspringen kann.  
  
 Betrachten Sie ein Steuerelement, das die folgenden (nicht optimierte) hat `OnDraw` Funktion:  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/cpp/optimizing-control-drawing_1.cpp)]  
  
 Stift und Pinsel in diesem Beispiel werden lokale Variablen, d. h., deren Destruktoren aufgerufen werden, wenn sie außerhalb des Gültigkeitsbereichs liegen (wenn die `OnDraw` Funktion endet). Die Destruktoren versucht, die entsprechenden GDI-Objekte zu löschen. Aber sie sollten nicht gelöscht werden, wenn Sie beabsichtigen, die sie in den Gerätekontext, bei der Rückkehr aus ausgewählt lassen `OnDraw`.  
  
 Um zu verhindern, dass die [CPen](../mfc/reference/cpen-class.md) und [CBrush](../mfc/reference/cbrush-class.md) Objekte zerstört wird, wenn `OnDraw` abgeschlossen ist, in der Membervariablen anstelle von lokalen Variablen speichern. Fügen Sie in das Steuerelement Klassendeklaration Deklarationen für zwei neue Membervariablen hinzu:  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/cpp/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/cpp/optimizing-control-drawing_3.h)]  
  
 Anschließend wird die `OnDraw` Funktion kann wie folgt umgeschrieben werden:  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/cpp/optimizing-control-drawing_4.cpp)]  
  
 Dieser Ansatz vermeidet die Erstellung der Stift und Pinsel jedes Mal `OnDraw` aufgerufen wird. Zur Verbesserung der Geschwindigkeit der Preis zusätzliche Instanzdaten für die Wartung eines besteht.  
  
 Wenn die ForeColor oder BackColor-Eigenschaft geändert wird, muss der Stift oder Pinsel erneut erstellt werden. Überschreiben Sie dazu die [Memberfunktionen OnForeColorChanged](../mfc/reference/colecontrol-class.md#onforecolorchanged) und [OnBackColorChanged](../mfc/reference/colecontrol-class.md#onbackcolorchanged) Member-Funktionen:  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/cpp/optimizing-control-drawing_5.cpp)]  
  
 Schließlich vermeiden unnötige `SelectObject` Aufrufe ändern `OnDraw` wie folgt:  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/cpp/optimizing-control-drawing_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)   
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements](../mfc/mfc-activex-controls-painting-an-activex-control.md)

