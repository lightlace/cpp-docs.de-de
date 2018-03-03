---
title: CReBar im Vergleich zu CReBarCtrl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CReBar
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68cd21e21c14a34122f1b26345fab767728ac6a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crebar-vs-crebarctrl"></a>CReBar im Vergleich zu CReBarCtrl
MFC stellt zwei Klassen um Infoleisten zu erstellen: [CReBar](../mfc/reference/crebar-class.md) und [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (die dient als Wrapper für die allgemeine Windows-Steuerungs-API). **CReBar** enthält alle die Funktionalität des allgemeinen Grundleisten-Steuerelements, und viele der erforderlichen steuerelementeinstellungen für allgemeine und Strukturen für Sie verarbeitet.  
  
 `CReBarCtrl`ist eine Wrapperklasse für die Win32-Grundleisten-Steuerelement, und daher leichter zu implementieren, wenn Sie nicht beabsichtigen, die Infoleiste in die MFC-Architektur integriert werden kann. Wenn Sie planen, verwenden Sie `CReBarCtrl` und die Infoleiste in der MFC-Architektur integriert, müssen Sie zusätzliche Sorgfalt Grundleisten-Steuerelement Manipulationen mit MFC Kommunikation ausführen. Diese Kommunikation ist nicht schwierig. Es ist jedoch zusätzliche Arbeit, die nicht benötigten ist bei Verwendung von **CReBar**.  
  
 Visual C++ bietet zwei Möglichkeiten, dem allgemeinen Grundleisten-Steuerelement nutzen.  
  
-   Erstellen Sie die Infoleiste mit **CReBar**, und rufen dann [CReBar:: GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) für den Zugriff auf die `CReBarCtrl` Memberfunktionen.  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl`ist eine Inline-Memberfunktion, die wandelt die **dies** Zeiger des Grundleisten-Objekts. Dies bedeutet, dass zur Laufzeit kein Mehraufwand für die von der Funktionsaufruf hat.  
  
-   Erstellen Sie die Infoleiste mit [CReBarCtrl](../mfc/reference/crebarctrl-class.md)Konstruktor.  
  
 Beide Methoden erhalten Sie Zugriff auf die Memberfunktionen von Grundleisten-Steuerelement. Beim Aufruf `CReBar::GetReBarCtrl`, es gibt einen Verweis auf ein `CReBarCtrl` Objekt, damit die beiden Satz von Memberfunktionen verwendet werden kann. Finden Sie unter [CReBar](../mfc/reference/crebar-class.md) Informationen zum Erstellen und das Erstellen einer Infoleiste mit **CReBar**.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

