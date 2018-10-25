---
title: Funktionen des Datensatzes anzeigen-Klassen (MFC-Datenzugriff) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 524fd0ac48c0f26f8621c074f5460e55d7690761
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074656"
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