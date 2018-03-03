---
title: DATE-Typ | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- DATE
dev_langs:
- C++
helpviewer_keywords:
- Date data type, implementing
- Date data type
- DATE type
- Date data type, about Date data type
- MFC, date and time
- hour values representation
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f1ed7eb2b467fd52545f65f98b87e8e34ad71f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="date-type"></a>DATE-Typ
Die **Datum** Typ wird mit einer 8-Byte-Gleitkommazahl implementiert. Tage werden durch ganze Zahl erhöht werden beginnend am 30. Dezember 1899 Mitternacht als jeweils auf die nächsthöhere dargestellt. Stundenwerte werden als der Absolute Wert des Bruchteils der Zahl dargestellt. Die folgende Tabelle zeigt verschiedene Datumsangaben zusammen mit ihren **Datum** Typ numerische Entsprechung:  
  
|Datum und Uhrzeit|Darstellung|  
|-------------------|--------------------|  
|Am 30. Dezember 1899 Mitternacht|0,00|  
|1. Januar 1900, Mitternacht|2.00|  
|4. Januar 1900, Mitternacht|5.00|  
|4. Januar 1900, 6 Uhr|5.25|  
|4. Januar 1900 Mittag|5.50|  
|4. Januar 1900, 9-Uhr|5.875|  
  
 Die **Datum** Typ Datum als auch die `COleDateTime` -Klasse stellt Datums- und Uhrzeitangaben als eine klassische Position. Die `COleDateTime` Klasse enthält mehrere Methoden zum Bearbeiten von Datumswerten, einschließlich der Konvertierung in und aus anderen allgemeinen Datumsformate.  
  
 Beachten Sie die folgenden Punkte bei der Arbeit mit diesen Datums- und Uhrzeitformate in Automation:  
  
-   Datumsangaben werden in Ortszeit angegeben. Synchronisierung muss manuell ausgeführt werden, bei der Arbeit mit Datumsangaben in unterschiedlichen Zeitzonen.  
  
-   Date-Datentypen für die Sommerzeit nicht berücksichtigt.  
  
-   Die Zeitachse Datum wird (vor dem 30. Dezember 1899) unterbrochenen für Datumswerte kleiner als 0. Dies ist, da der ganzzahlige Teil des Datumswerts behandelt wird als signiert, während der Bruchteil behandelt wird, als Zahl ohne Vorzeichen. Das heißt, kann der ganzzahlige Teil des Datumswerts positiv oder negativ sein, während der Bruchteil des Datumswerts immer dem gesamten logischen Datum hinzugefügt wird. Die folgende Tabelle zeigt einige Beispiele:  
  
|Datum und Uhrzeit|Darstellung|  
|-------------------|--------------------|  
|27 Dezember 1899 (Mitternacht)|-3.00|  
|28 Dezember 1899 Mittag|-2.50|  
|28 Dezember 1899 (Mitternacht)|-2.00|  
|29. Dezember 1899, Mitternacht|-1.00|  
|Am 30. Dezember 1899 18: 00 Uhr|-0.75|  
|Am 30. Dezember 1899 Mittag|-0.50|  
|Am 30. Dezember 1899 6 Uhr|-0.25|  
|Am 30. Dezember 1899 Mitternacht|0,00|  
|Am 30. Dezember 1899 6 Uhr|0.25|  
|Am 30. Dezember 1899 Mittag|0.50|  
|Am 30. Dezember 1899 18: 00 Uhr|0.75|  
|31. Dezember 1899, Mitternacht|1.00|  
|1. Januar 1900, Mitternacht|2.00|  
|1. Januar 1900 Mittag|2.50|  
|2 Januar 1900 (Mitternacht)|3.00|  
  
> [!CAUTION]
>  Beachten Sie, dass, weil 6:00 Uhr wird durch ein Dezimalstellenwert 0,25 unabhängig davon, ob die ganze Zahl, die den Tag darstellt (nach dem 30. Dezember 1899 wieder) positiv ist immer dargestellt oder negative (vor dem 30. Dezember 1899 wieder), ein einfachen floating Point-Vergleich würde fälschlicherweise sortieren alle **Datum** für 6:00 an einem Tag älter als 12/30/1899 zurück als *später* als eine **Datum** 7:00 Uhr für denselben Tag darstellt.  
  
 Weitere Informationen zu Problemen im Zusammenhang mit der **Datum** und `COleDateTime` Typen finden Sie unter [COleDateTime Klasse](../atl-mfc-shared/reference/coledatetime-class.md) und [Datum und Uhrzeit: Automatisierungsunterstützung](../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime-Klasse](../atl-mfc-shared/reference/coledatetime-class.md)

