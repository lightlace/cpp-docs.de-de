---
title: Aufzeichnen von Ansichten (MFC-Datenzugriff) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa8f3fd740de57cf556e723e00a8ef792adc5b36
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059011"
---
# <a name="record-views--mfc-data-access"></a>Datensatzansichten (MFC-Datenzugriff)

Dieser Abschnitt gilt nur für die MFC-ODBC-Klassen. Weitere Informationen zu OLE DB-Datensatzansichten finden Sie unter [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) und [mithilfe von OLE DB-Datensatzansichten](../data/oledb/using-ole-db-record-views.md).

Zur Unterstützung von formularbasierten formularbasierten datenzugriffsanwendungen stellt die Klassenbibliothek die Klasse [CRecordView](../mfc/reference/crecordview-class.md). Eine Datensatzansicht ist ein Formularansichtsobjekt, dessen Steuerelemente direkt an den Felddatenmembern zugeordnet sind, eine [Recordset](../data/odbc/recordset-odbc.md) Objekt (und indirekt den entsprechenden Spalten in einem Abfrageergebnis oder einer Tabelle in der Datenquelle). Wie ihre Basisklasse [CFormView](../mfc/reference/cformview-class.md), `CRecordView` basiert auf einer Dialogfeldvorlagen-Ressource.

## <a name="form-uses"></a>Verwendungszwecke für Formulare

Formulare eignen sich für eine Vielzahl von Datenzugriffsaufgaben:

- Eingeben von Daten

- Durchführen von schreibgeschützten Prüfung von Daten

- Aktualisieren von Daten

## <a name="further-reading-about-record-views"></a>Weitere Informationen zu Datensatzansichten

Die Informationen in diesen Themen gelten für die ODBC-basierten und DAO-basierte Klassen. Verwenden Sie `CRecordView` für ODBC und `CDaoRecordView` für DAO.

Folgende Themen werden behandelt:

- [Features von Datensatzansichts-Klassen](../data/features-of-record-view-classes-mfc-data-access.md)

- [Datenaustausch für Datensatzansichten](../data/data-exchange-for-record-views-mfc-data-access.md)

- [Aufgaben bei der Arbeit mit Datensatzansichten](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)

- [Entwerfen und Erstellen einer Datensatzansicht](../data/designing-and-creating-a-record-view-mfc-data-access.md)

- [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)

## <a name="see-also"></a>Siehe auch

[Datenzugriffsprogrammierung (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)