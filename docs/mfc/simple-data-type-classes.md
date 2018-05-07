---
title: Klassen für einfache Datentypen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54d7f200ee35489f37256023d28bdd3260bf48ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="simple-data-type-classes"></a>Klassen für einfache Datentypen
Die folgenden Klassen kapseln, zeichnen Koordinaten, Zeichenfolgen und Uhrzeit und Datumsinformationen, sodass die praktische von C++-Syntax verwenden. Diese Objekte werden häufig als Parameter für die Memberfunktionen der Windows-Klassen in der Klassenbibliothek verwendet werden. Da `CPoint`, `CSize`, und `CRect` entsprechen der **Punkt**, **Größe**, und `RECT` um Datenstrukturen handelt, bzw., im Windows SDK können Sie Objekte dieser C++-Klassen, wo Sie diese Strukturen C-Sprachen verwenden können. Die Klassen bieten nützliche Schnittstellen über deren Memberfunktionen. `CStringT` Stellt sehr flexibel, dynamische Zeichenfolgen bereit. `CTime`, `COleDateTime`, `CTimeSpan`, und **COleTimeSpan** Uhrzeit-und Datumswerte darstellen. Weitere Informationen zu diesen Klassen finden Sie im Artikel [Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md).  
  
 Die Klassen, die mit "**COle**" Encapsulations Datentypen, die von OLE bereitgestellt werden. Diese Datentypen können verwendet werden, in der Windows-Programme, unabhängig davon, ob andere OLE-Funktionen verwendet werden.  
  
 [CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)  
 Enthält die Zeichenfolgen.  
  
 [CTime](../atl-mfc-shared/reference/ctime-class.md)  
 Enthält die absoluten Werte für Datum und Uhrzeit.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **Datum**. Stellt die Datums-und Uhrzeitwerte dar.  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 Enthält die entsprechenden Werte für Datum und Uhrzeit.  
  
 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)  
 Relative enthält `COleDateTime` Werten, z. B. den Unterschied zwischen zwei `COleDateTime` Werte.  
  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Koordinate (X, y)-Paare enthält.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Enthält Abstand, relativen Positionen oder paarweise zugeordneten Werte.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Enthält die Koordinaten der rechteckige Bereiche.  
  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Stellt die Funktionalität der Liste der Windows-Image bereit. Bilderliste für das werden mit List-Steuerelemente und Struktursteuerelemente verwendet. Sie können auch verwendet werden, zum Speichern und einen Satz von Bitmaps mit derselben Größe zu archivieren.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **VARIANT**. Daten in **VARIANT**s kann in vielen verschiedenen Formaten gespeichert werden.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper für den Typ der OLE-Automatisierung **Währung**, Festkommanotation in jedem Fall arithmetischen Typs, mit 15 Stellen vor dem Dezimaltrennzeichen und 4 Ziffern nach dem.  
  
> [!NOTE]
>  `CRect`, `CSize`, und `CPoint` in ATL- oder MFC-Anwendungen verwendet werden können. Darüber hinaus `CStringT` bietet eine MFC-unabhängigen `CString`-wie-Klasse. Weitere Informationen zu freigegebenen Hilfsklassen, finden Sie unter [gemeinsam genutzten Klassen](../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

