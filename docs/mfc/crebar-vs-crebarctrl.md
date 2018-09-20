---
title: CReBar im Vergleich zu CReBarCtrl | Microsoft-Dokumentation
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
ms.openlocfilehash: 6133e298cd0bc5b497fbbba47982a755afeefb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442850"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar im Vergleich zu CReBarCtrl

MFC stellt zwei Klassen um Infoleisten zu erstellen: [CReBar](../mfc/reference/crebar-class.md) und [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (die dient als Wrapper für die allgemeine Windows-Steuerungs-API). `CReBar` Stellt die gesamte Funktionalität des allgemeinen Grundleisten-Steuerelements, und viele der erforderlichen steuerelementeinstellungen für allgemeine und Strukturen für Sie verarbeitet.

`CReBarCtrl` ist eine Wrapperklasse für die Win32-Grundleisten-Steuerelement, und daher möglicherweise einfacher zu implementieren, wenn Sie nicht beabsichtigen, die die Infoleiste in die MFC-Architektur integriert. Wenn Sie planen, verwenden Sie `CReBarCtrl` und grundleiste in der MFC-Architektur integriert, Sie müssen zusätzliche Sorgfalt Grundleisten-Steuerelement Manipulationen mit MFC zu kommunizieren. Diese Kommunikation ist nicht schwierig. Es ist jedoch zusätzliche Arbeit, die nicht benötigten ist bei Verwendung von `CReBar`.

Visual C++ bietet zwei Möglichkeiten, um allgemeine Infoleisten-Steuerelements zu nutzen.

- Erstellen Sie die Infoleiste mit `CReBar`, und rufen dann [CReBar:: GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) für den Zugriff auf die `CReBarCtrl` Memberfunktionen.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` ist eine Inlinefunktion für den Member, die wandelt die **dies** Zeiger des Infoleiste-Objekts. Dies bedeutet, dass zur Laufzeit kein Mehraufwand von der Funktionsaufruf hat.

- Erstellen Sie die Infoleiste mit [CReBarCtrl](../mfc/reference/crebarctrl-class.md)Konstruktor.

Beide Methoden erhalten Sie Zugriff auf die Memberfunktionen des Infoleisten-Steuerelements. Beim Aufruf `CReBar::GetReBarCtrl`, es gibt einen Verweis auf eine `CReBarCtrl` Objekt, damit Sie beide Sätze von Memberfunktionen verwenden können. Finden Sie unter [CReBar](../mfc/reference/crebar-class.md) Informationen zum Erstellen und zum Erstellen eines Grundleisten `CReBar`.

## <a name="see-also"></a>Siehe auch

[Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

