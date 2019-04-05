---
title: 'Recordset: Arbeiten mit großen Datenelementen (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 3ba8d4af5b0781c425dd3b1223e2208b279f055e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033043"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Recordset: Arbeiten mit großen Datenelementen (ODBC)

Dieses Thema gilt sowohl für die MFC-ODBC-Klassen als auch für die MFC-DAO-Klassen.

> [!NOTE]
>  Wenn Sie die MFC-DAO-Klassen verwenden, verwalten, große Datenelemente mit Klasse [CByteArray](../../mfc/reference/cbytearray-class.md) statt Klasse [CLongBinary](../../mfc/reference/clongbinary-class.md). Wenn Sie die MFC-ODBC-Klassen mit gesammelte verwenden, verwenden Sie `CLongBinary` statt `CByteArray`. Weitere Informationen zu gesammelten Abrufens von Zeilen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Nehmen wir an, dass die Datenbank kann große Teile der Daten, z. B. Bitmaps (Fotos von Mitarbeitern, Karten, Bilder von Produkten, OLE-Objekte und So weiter) speichern. Diese Art von Daten wird häufig als ein Binary Large Object (oder BLOB) da bezeichnet:

- Jeder Feldwert ist groß.

- Im Gegensatz zu Zahlen und anderen einfachen Datentypen hat er keine feste Größe.

- Die Daten werden aus der Perspektive des Programms besitzen.

In diesem Thema wird erläutert, welche Unterstützung Datenbankklassen für die Verwendung solcher Objekte zu bieten.

##  <a name="_core_managing_large_objects"></a> Verwalten von großen Objekten

Durch Recordsets haben zwei Möglichkeiten, die die spezielle Schwierigkeit der Verwaltung von binary large Object lösen. Sie können die Klasse [CByteArray](../../mfc/reference/cbytearray-class.md) oder Sie können die Klasse [CLongBinary](../../mfc/reference/clongbinary-class.md). Im allgemeinen `CByteArray` ist die bevorzugte Methode zum Verwalten von großer binärer Daten.

`CByteArray` erfordert mehr Aufwand als `CLongBinary` mehr kann jedoch, wie in beschrieben [leistungsfähiger](#_core_the_cbytearray_class). `CLongBinary` wird kurz in beschrieben [CLongBinary-Klasse](#_core_the_clongbinary_class).

Ausführliche Informationen zur Verwendung von `CByteArray` zum Arbeiten mit großen Datenelementen finden Sie unter [technischen Hinweis 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

##  <a name="_core_the_cbytearray_class"></a> CByteArray-Klasse

`CByteArray` ist der MFC-Auflistungsklassen. Ein `CByteArray` Objekt speichert ein dynamisches Array von Bytes, bei Bedarf größer werden kann. Die Klasse bietet schnellen Zugriff über einen Index, wie mit integrierten C++-Arrays. `CByteArray` Objekte können serialisiert und Diagnosezwecken werden. Die Klasse bietet Memberfunktionen für das Abrufen und Festlegen der angegebenen Bytes, einfügen und Anfügen von Bytes und Entfernen eines oder alle Bytes. Diese Funktionen stellen die binären Daten, die einfacher zu analysieren. Z. B. wenn das binäre Objekt ein OLE-Objekt ist, Sie möglicherweise, einige Bytes Header, um das eigentliche Objekt erreichen durchzuarbeiten.

##  <a name="_core_using_cbytearray_in_recordsets"></a> Verwenden CByteArray in Recordsets

Erteilen Sie den Typ für die Felddatenmember der Recordset `CByteArray`, Sie angeben, dass eine feste Basis aus dem [RFX](../../data/odbc/record-field-exchange-rfx.md) können verwalten, die Übertragung eines Objekts zwischen dem Recordset und der Datenquelle und über die Sie bearbeiten können die die Daten innerhalb des Objekts. RFX einen bestimmten Standort für die abgerufenen Daten benötigt, und Sie benötigen eine Möglichkeit zum Zugriff auf die zugrunde liegenden Daten.

Ausführliche Informationen zur Verwendung von `CByteArray` zum Arbeiten mit großen Datenelementen finden Sie unter [technischen Hinweis 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).

##  <a name="_core_the_clongbinary_class"></a> CLongBinary-Klasse

Ein [CLongBinary](../../mfc/reference/clongbinary-class.md) Objekt ist eine einfache Umgebung ein, um eine `HGLOBAL` handle für einen Block von Speicher auf dem Heap zugeordnet. Beim Binden einer Tabellenspalte, die ein großes binäres Objekt enthält, RFX ordnet die `HGLOBAL` behandelt wird, wenn sie auf das Recordset die Daten übertragen werden soll, und das Handle in speichert die `CLongBinary` Feld des Recordset-Objekts.

Verwenden Sie wiederum die `HGLOBAL` zu behandeln, `m_hData`, um mit den Daten selbst, die darauf ausgeführt werden, wie auf Daten zu arbeiten. Hier kommt [CByteArray](../../mfc/reference/cbytearray-class.md) fügt Funktionen hinzu.

> [!CAUTION]
>  CLongBinary-Objekte können nicht als Parameter in Funktionsaufrufen verwendet werden. Darüber hinaus ihre Implementierung, die ruft `::SQLGetData`, unbedingt verlangsamt sich das Scrollen für eine bildlauffähige Momentaufnahme. Dies kann auch "true" sein, bei der Verwendung einer `::SQLGetData` selbst zum Abrufen von Spalten für das dynamische Schema aufrufen.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)