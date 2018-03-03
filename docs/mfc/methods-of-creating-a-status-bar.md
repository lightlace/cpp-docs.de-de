---
title: Methoden zum Erstellen einer Statusleiste | Microsoft Docs
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
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce14870db466727f93daea15b60c99d975783e87
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="methods-of-creating-a-status-bar"></a>Methoden zum Erstellen einer Statusleiste
MFC stellt zwei Klassen zum Erstellen von Statusleisten: [CStatusBar](../mfc/reference/cstatusbar-class.md) und [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (die dient als Wrapper für die allgemeine Windows-Steuerungs-API). `CStatusBar`bietet alle Funktionen der Statusleiste Standardsteuerelements er automatisch interagiert mit Menüs und Symbolleisten und viele der erforderlichen steuerelementeinstellungen für allgemeine und Strukturen verarbeitet. die resultierende ausführbare Datei in der Regel werden jedoch größer ist als mit erstellt `CStatusBarCtrl`.  
  
 `CStatusBarCtrl`in der Regel die Ergebnisse in eine kleinere ausführbare Datei, und Sie bevorzugen `CStatusBarCtrl` , wenn Sie nicht beabsichtigen, die Statusleiste in der MFC-Architektur integriert. Wenn Sie planen, verwenden Sie `CStatusBarCtrl` und die Statusleiste in der MFC-Architektur integriert, müssen Sie zusätzliche Sorgfalt Statusleiste-Steuerelement Manipulationen mit MFC Kommunikation ausführen. Diese Kommunikation ist nicht schwierig. Es ist jedoch zusätzliche Arbeit, die nicht benötigten ist bei Verwendung von `CStatusBar`.  
  
 Visual C++ bietet zwei Möglichkeiten, um das allgemeine StatusBar-Steuerelement nutzen.  
  
-   Erstellen Sie die Statusleiste mit `CStatusBar`, und rufen dann [GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) für den Zugriff auf die `CStatusBarCtrl` Memberfunktionen.  
  
-   Erstellen Sie die Statusleiste mit [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)Konstruktor.  
  
 Beide Methoden erhalten Sie Zugriff auf die Memberfunktionen von Statusleisten-Steuerelement. Beim Aufruf `CStatusBar::GetStatusBarCtrl`, es gibt einen Verweis auf ein `CStatusBarCtrl` Objekt, damit die beiden Satz von Memberfunktionen verwendet werden kann. Finden Sie unter [CStatusBar](../mfc/reference/cstatusbar-class.md) Informationen zum Erstellen und das Erstellen einer Statusleiste mit `CStatusBar`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

