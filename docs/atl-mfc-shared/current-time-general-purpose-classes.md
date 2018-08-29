---
title: 'Aktuelle Zeit: Allgemeine Klassen | Microsoft-Dokumentation'
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
ms.openlocfilehash: c99a2626c9f60c6407ca9b374bed9c83c981e5b3
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132006"
---
# <a name="current-time-general-purpose-classes"></a>Aktuelle Zeit: Allgemeine Klassen
Das folgende Verfahren zeigt, wie Sie erstellen eine `CTime` Objekt, und initialisieren Sie es mit der aktuellen Zeit.  
  
#### <a name="to-get-the-current-time"></a>Um die aktuelle Uhrzeit abzurufen.  
  
1.  Zuordnen einer `CTime` Objekt wie folgt:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  Nicht initialisierte `CTime` Objekte werden nicht in eine gültige Zeit initialisiert.  
  
2.  Rufen Sie die `CTime::GetCurrentTime` Funktion, um die aktuelle Uhrzeit vom Betriebssystem abzurufen. Diese Funktion gibt eine `CTime` -Objekt, das verwendet werden kann, zum Festlegen des Werts der `CTime`wie folgt:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     Da `GetCurrentTime` ist eine statische Memberfunktion von der `CTime` -Klasse, müssen Sie den Namen mit dem Namen der Klasse und den Bereichsauflösungsoperator qualifizieren (`::`), `CTime::GetCurrentTime()`.  
  
 Natürlich könnten die zwei Schritte bereits in einer einzigen Anweisung wie folgt kombiniert werden:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  




