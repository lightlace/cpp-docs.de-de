---
title: Dialogfeld-Steuerelemente im Framework | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 840e66def6a908b26b5021537eddee68c50a9628
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-box-components-in-the-framework"></a>Dialogfeld-Steuerelemente im Framework
In der MFC-Framework besteht ein Dialogfeld aus zwei Komponenten:  
  
-   Dialogfeldvorlagen-Ressource, die das Dialogfeld-Steuerelemente und die Position angibt.  
  
     Die Dialogressource speichert eine Dialogfeldvorlage aus der Windows im Dialogfenster erstellt und angezeigt. Die Vorlage gibt das Dialogfeld Eigenschaften, einschließlich seiner Größe, Position, Stil, und die Typen und Positionen der Steuerelemente des Dialogfelds. Verwenden Sie in der Regel einer Dialogfeldvorlage als Ressource gespeichert, aber Sie können auch eine eigene Vorlage erstellen, im Arbeitsspeicher.  
  
-   Abgeleitet von eine Dialogfeldklasse [CDialog](../mfc/reference/cdialog-class.md), um eine programmgesteuerte Schnittstelle für die Verwaltung des Dialogfelds "" bereitzustellen.  
  
     Ein Dialogfeld ist ein Fenster, und in einem Windows-Fenster, wenn es sichtbar angehängt wird. Wenn Sie im Dialogfeld erstellt wird, wird der Dialogfeldvorlagen-Ressource als Vorlage zum Erstellen von untergeordneten Window-Steuerelementen für das Dialogfeld verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

