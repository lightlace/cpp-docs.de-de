---
title: Klassen für einfache Datentypen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: 4e415805301d7d12bd418a3b55509a7732851492
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307417"
---
# <a name="simple-data-type-classes"></a>Klassen für einfache Datentypen

Die folgenden Klassen kapseln, zeichnen Koordinaten, Zeichenfolgen und Zeit und aktuelle Informationen, sodass praktisch der C++-Syntax verwenden. Diese Objekte werden häufig als Parameter an die Memberfunktionen der Windows-Klassen in der Klassenbibliothek verwendet. Da `CPoint`, `CSize`, und `CRect` entsprechen den **Punkt**, **Größe**, und **RECT** -Strukturen bzw., im Windows SDK Sie können Objekte dieser C++-Klassen verwenden, an denen Sie diese Programmiersprache C-Strukturen verwendet werden. Die Klassen bieten nützliche Schnittstellen über deren Memberfunktionen. `CStringT` Stellt sehr flexibel, dynamische Zeichenfolgen bereit. `CTime`, `COleDateTime`, `CTimeSpan`, und `COleTimeSpan` stellen Werte für Datum und Uhrzeit dar. Weitere Informationen zu diesen Klassen finden Sie im Artikel [Datums- /](../atl-mfc-shared/date-and-time.md).

Die Klassen, die mit "`COle`" kapselungen der Datentypen, die von OLE bereitgestellt werden. Diese Datentypen können verwendet werden, in der Windows-Programme, unabhängig davon, ob andere OLE-Funktionen verwendet werden.

[CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Enthält Zeichenfolgen.

[CTime](../atl-mfc-shared/reference/ctime-class.md)<br/>
Enthält die absoluten Werte für Datum und Uhrzeit.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Wrapper für den Typ der OLE-Automatisierung **Datum**. Stellt Werte für Datum und Uhrzeit dar.

[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
Enthält die relativen Werte für Datum und Uhrzeit.

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
Enthält einen relativen `COleDateTime` Werten, z. B. den Unterschied zwischen zwei `COleDateTime` Werte.

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Die Koordinate (X, y)-Paare enthält.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Enthält paarweise zugeordneten Werte, relativen Positionen oder Entfernung an.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Enthält die Koordinaten der rechteckige Bereiche.

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Stellt die Funktionen der Liste der Windows-Bilder. Bilderliste für das werden mit Listensteuerelementen und Struktursteuerelementen verwendet. Sie können auch zum Speichern und archivieren eine Reihe von Bitmaps mit derselben Größe verwendet werden.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Wrapper für den Typ der OLE-Automatisierung **VARIANT**. Daten in **VARIANT**s kann in vielen Formaten gespeichert werden.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Wrapper für den Typ der OLE-Automatisierung **Währung**, Festkomma-arithmetischen Typs, mit 15 Stellen vor dem Dezimaltrennzeichen und 4 Ziffern nach dem.

> [!NOTE]
>  `CRect`, `CSize`, und `CPoint` in entweder ATL oder MFC-Anwendungen verwendet werden können. Darüber hinaus `CStringT` bietet eine MFC-unabhängigen `CString`-wie-Klasse. Weitere Informationen über gemeinsam genutzte Dienstprogramme-Klassen finden Sie unter [gemeinsam genutzten Klassen](../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
