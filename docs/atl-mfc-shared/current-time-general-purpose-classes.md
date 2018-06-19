---
title: 'Aktuelle Zeit: Allgemeine Klassen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec71cf76f859457aa76e69b57b58db3940e974da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354594"
---
# <a name="current-time-general-purpose-classes"></a>Aktuelle Zeit: Allgemeine Klassen
Das folgende Verfahren veranschaulicht das Erstellen einer `CTime` Objekt, und initialisieren Sie es mit der aktuellen Uhrzeit.  
  
#### <a name="to-get-the-current-time"></a>Um die aktuelle Uhrzeit abzurufen.  
  
1.  Zuordnen einer `CTime` Objekt, wie folgt:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  Nicht initialisiertes `CTime` Objekte werden nicht auf eine gültige Zeit initialisiert.  
  
2.  Rufen Sie die `CTime::GetCurrentTime` Funktion, um die aktuelle Zeit des Betriebssystems abzurufen. Diese Funktion gibt eine `CTime` -Objekt, das verwendet werden kann, zum Festlegen des Werts der `CTime`wie folgt:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     Da `GetCurrentTime` ist eine statische Memberfunktion aus der `CTime` -Klasse, müssen Sie seinen Namen durch den Namen der Klasse und den Bereichsauflösungsoperator qualifizieren (`::`), `CTime::GetCurrentTime()`.  
  
 Natürlich können die zwei Schritte zuvor in einer einzigen Anweisung wie folgt kombiniert werden:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit: Allgemeine Klassen](../atl-mfc-shared/date-and-time-general-purpose-classes.md)



