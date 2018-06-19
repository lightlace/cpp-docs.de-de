---
title: CReBar im Vergleich zu CReBarCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6d0b8df40676cc64c97a6bdef013321c404899f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344973"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar im Vergleich zu CReBarCtrl
MFC stellt zwei Klassen um Infoleisten zu erstellen: [CReBar](../mfc/reference/crebar-class.md) und [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (die dient als Wrapper für die allgemeine Windows-Steuerungs-API). **CReBar** enthält alle die Funktionalität des allgemeinen Grundleisten-Steuerelements, und viele der erforderlichen steuerelementeinstellungen für allgemeine und Strukturen für Sie verarbeitet.  
  
 `CReBarCtrl` ist eine Wrapperklasse für die Win32-Grundleisten-Steuerelement, und daher leichter zu implementieren, wenn Sie nicht beabsichtigen, die Infoleiste in die MFC-Architektur integriert werden kann. Wenn Sie planen, verwenden Sie `CReBarCtrl` und die Infoleiste in der MFC-Architektur integriert, müssen Sie zusätzliche Sorgfalt Grundleisten-Steuerelement Manipulationen mit MFC Kommunikation ausführen. Diese Kommunikation ist nicht schwierig. Es ist jedoch zusätzliche Arbeit, die nicht benötigten ist bei Verwendung von **CReBar**.  
  
 Visual C++ bietet zwei Möglichkeiten, dem allgemeinen Grundleisten-Steuerelement nutzen.  
  
-   Erstellen Sie die Infoleiste mit **CReBar**, und rufen dann [CReBar:: GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) für den Zugriff auf die `CReBarCtrl` Memberfunktionen.  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl` ist eine Inline-Memberfunktion, die wandelt die **dies** Zeiger des Grundleisten-Objekts. Dies bedeutet, dass zur Laufzeit kein Mehraufwand für die von der Funktionsaufruf hat.  
  
-   Erstellen Sie die Infoleiste mit [CReBarCtrl](../mfc/reference/crebarctrl-class.md)Konstruktor.  
  
 Beide Methoden erhalten Sie Zugriff auf die Memberfunktionen von Grundleisten-Steuerelement. Beim Aufruf `CReBar::GetReBarCtrl`, es gibt einen Verweis auf ein `CReBarCtrl` Objekt, damit die beiden Satz von Memberfunktionen verwendet werden kann. Finden Sie unter [CReBar](../mfc/reference/crebar-class.md) Informationen zum Erstellen und das Erstellen einer Infoleiste mit **CReBar**.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

