---
title: Features von Datensatzansichts-Klassen (MFC-Datenzugriff)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: 2feda8f8f446e02a5056287c656707ea038f5387
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461151"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Features von Datensatzansichts-Klassen (MFC-Datenzugriff)

Erreichen Sie formularbasierte formularbasierte datenzugriffsprogrammierung mit Klasse [CFormView](../mfc/reference/cformview-class.md), aber [CRecordView](../mfc/reference/crecordview-class.md) ist im Allgemeinen eine bessere-Klasse abgeleitet. Zusätzlich zu seiner `CFormView` Features `CRecordView`:

- Bietet Dialogdatenaustausch (DDX) zwischen den Formularsteuerelementen und dem zugehörigen Recordset-Objekt.

- Verarbeitet die Befehle "Erste verschieben, Nächste verschieben, vorherige verschieben und letzte verschieben" zum Navigieren durch Datensätze in der zugehörigen Recordset-Objekt.

- Aktualisiert Änderungen in den aktuellen Datensatz, wenn der Benutzer zu einem anderen Datensatz wechselt.

Weitere Informationen zur Navigation finden Sie unter [Datensatzansichten: Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).

## <a name="see-also"></a>Siehe auch

[Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)<br/>
[Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)