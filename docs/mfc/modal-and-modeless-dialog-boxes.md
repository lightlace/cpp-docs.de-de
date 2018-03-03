---
title: Modale und nicht modale Dialogfelder | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 982bb8f195c3744246addc18d66bee953914dde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="modal-and-modeless-dialog-boxes"></a>Modale und nicht modale Dialogfelder
Sie können die Klasse [CDialog](../mfc/reference/cdialog-class.md) auf zwei Arten von Dialogfeldern zu verwalten:  
  
-   *Modale Dialogfelder*, die erfordern, dass des Benutzers reagiert, bevor Sie fortfahren das Programm  
  
-   *Nicht modale Dialogfelder*, die auf dem Bildschirm und sind für die Verwendung zu einem beliebigen Zeitpunkt verfügbar bleiben jedoch andere Aktivitäten des Benutzers zulassen  
  
 Die Ressource zu bearbeiten und-Verfahren zum Erstellen einer Dialogfeldvorlage entsprechen für modale und nicht modale Dialogfelder.  
  
 Erstellen ein Dialogfeld für das Programm erfordert die folgenden Schritte aus:  
  
1.  Verwenden der [Dialog-Editor](../windows/dialog-editor.md) Entwerfen des Dialogfelds "" und erstellen die Dialogfeldvorlagen-Ressource.  
  
2.  Erstellen einer Dialogfeldklasse.  
  
3.  Verbinden der [Dialog-Ressource Steuerelemente Meldungshandler](../windows/adding-event-handlers-for-dialog-box-controls.md) in Dialogklasse.  
  
4.  Hinzufügen von Datenelementen, die verknüpft sind, mit dem Dialogfeld-Steuerelemente sowie an [Dialogdatenaustausch](../mfc/dialog-data-exchange.md) und [Dialogfeld Daten Überprüfungen](../mfc/dialog-data-validation.md) für die Steuerelemente.  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

