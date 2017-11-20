---
title: Erstellen eigener Dialogfeldklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd80d55df3ae9adc4a586d1cc5387ee6d1f53282
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="creating-your-dialog-class"></a>Erstellen eigener Dialogfeldklassen
Für jedes Dialogfeld im Programm Erstellen einer neuen Dialogfeldklasse zur Bearbeitung der Dialogfeldressource.  
  
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md) erläutert das Erstellen einer neuen Dialogfeldklasse. Beim Erstellen einer Dialogfeldklasse mit dem Klassen-Assistenten, schreibt er die folgenden Elemente in der. H und. CPP-Dateien, die Sie angeben:  
  
 In der. H-Datei:  
  
-   Eine Klassendeklaration für die Dialogfeldklasse. Die abgeleitete Klasse wird von [CDialog](../mfc/reference/cdialog-class.md).  
  
 In der. CPP-Datei:  
  
-   Einer meldungszuordnung für die Klasse.  
  
-   Ein standard-Konstruktor für das Dialogfeld.  
  
-   Eine Überschreibung der [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) Memberfunktion. Bearbeiten Sie diese Funktion. Es dient für Dialogfeld Dialogdatenaustausch und-Validierung Funktionen wie weiter unten im [Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer Dialogfeldklasse mit Code-Assistenten](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

