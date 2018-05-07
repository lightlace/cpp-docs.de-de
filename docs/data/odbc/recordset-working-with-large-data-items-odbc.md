---
title: 'Recordset: Arbeiten mit großen Datenelementen (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6845d2e3c1b1eac31486200a0f610037d4774626
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Recordset: Arbeiten mit großen Datenelementen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen und die MFC-DAO-Klassen.  
  
> [!NOTE]
>  Wenn Sie die MFC-DAO-Klassen verwenden, verwalten Sie große Datenelemente mit Klasse [CByteArray](../../mfc/reference/cbytearray-class.md) anstatt Klasse [CLongBinary](../../mfc/reference/clongbinary-class.md). Verwenden Sie bei Verwendung von MFC-ODBC-Klassen mit gesammelte `CLongBinary` statt `CByteArray`. Weitere Informationen über das gesammelte finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Nehmen Sie an, dass die Datenbank große Teile der Daten, z. B. Bitmaps (Fotos der Mitarbeiter, Karten, Bilder von Produkten, OLE-Objekte und So weiter) gespeichert werden kann. Diese Art von Daten wird häufig als Binary Large Object (oder BLOB) da bezeichnet:  
  
-   Der Wert jedes Felds ist groß.  
  
-   Im Gegensatz zu Zahlen und anderen einfachen Datentypen hat sie keine vorhersagbare Größe.  
  
-   Die Daten werden aus der Perspektive des Programms besitzen.  
  
 In diesem Thema wird erläutert, welche Unterstützung die Datenbankklassen zum Arbeiten mit solchen Objekten bieten.  
  
##  <a name="_core_managing_large_objects"></a> Verwalten von großen Objekten  
 Recordsets haben zwei Möglichkeiten, um die spezielle Schwierigkeit der Verwaltung von binary large Object zu lösen. Sie können die Klasse [CByteArray](../../mfc/reference/cbytearray-class.md) oder Sie können die Klasse [CLongBinary](../../mfc/reference/clongbinary-class.md). Im allgemeinen `CByteArray` ist die bevorzugte Methode zum Verwalten von großer binäre Daten.  
  
 `CByteArray` erfordert einen höheren Aufwand als `CLongBinary` jedoch besser geeignet ist, wie in beschrieben [leistungsfähiger](#_core_the_cbytearray_class). `CLongBinary` wird in kurz beschrieben [CLongBinary-Klasse](#_core_the_clongbinary_class).  
  
 Ausführliche Informationen zur Verwendung von `CByteArray` zum Arbeiten mit großen Datenelementen finden Sie unter [technischen Hinweis 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_cbytearray_class"></a> CByteArray-Klasse  
 `CByteArray` ist eine MFC-Auflistungsklassen. Ein `CByteArray` Objekt speichert ein dynamisches Bytearray – das Array bei Bedarf anwachsen kann. Die Klasse bietet schnellen Zugriff über einen Index, wie mit integrierten C++-Arrays. `CByteArray` -Objekte können serialisiert und Diagnosezwecken. Die Klasse stellt Memberfunktionen zum Abrufen und Festlegen der angegebenen Bytes, Einfügen von und Anhängen Bytes und Entfernen eines oder alle Bytes bereit. Diese Funktionen stellen die binären Daten, die einfacher zu analysieren. Wenn binary Object eines OLE-Objekts ist, müssen Sie z. B. möglicherweise über einige Header Bytes zum Erreichen des eigentlichen Objekts arbeiten.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> Verwenden CByteArray in Recordsets  
 Durch die Vergabe Felddatenmember der Recordset Typ `CByteArray`, geben Sie eine feste Basis aus dem [RFX](../../data/odbc/record-field-exchange-rfx.md) können verwalten, die Übertragung ein solches Objekt zwischen Recordset und der Datenquelle die die Daten innerhalb des Objekts. RFX benötigt einen bestimmten Standort für die abgerufenen Daten, und Sie benötigen eine Möglichkeit zum Zugriff auf die zugrunde liegenden Daten.  
  
 Ausführliche Informationen zur Verwendung von `CByteArray` zum Arbeiten mit großen Datenelementen finden Sie unter [technischen Hinweis 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_clongbinary_class"></a> CLongBinary-Klasse  
 Ein [CLongBinary](../../mfc/reference/clongbinary-class.md) Objekt ist eine einfache Shell aus, um eine `HGLOBAL` handle für einen Block von Speicher auf dem Heap reserviert. Wenn sie eine Tabellenspalte, die ein binary large Object enthält gebunden, RFX ordnet die `HGLOBAL` behandelt wird, wenn er die Datenübertragung an das Recordset muss und das Handle in speichert die `CLongBinary` Feld des Recordsets.  
  
 Verwenden Sie wiederum die `HGLOBAL` zu behandeln, `m_hData`, um mit den Daten selbst, die darauf ausgeführt werden, wie Sie für jedes beliebige Daten arbeiten zu. Dies ist, wenn [CByteArray](../../mfc/reference/cbytearray-class.md) fügt Funktionen hinzu.  
  
> [!CAUTION]
>  CLongBinary-Objekte können nicht als Parameter in Funktionsaufrufen verwendet werden. Darüber hinaus, der aufgerufen wird, deren Implementierung **:: SQLGetData**, unbedingt durch die die fortlaufenden Leistung für einen bildlauffähigen Snapshot. Dies kann auch "true" sein, bei der Verwendung einer **:: SQLGetData** selbst zum Abrufen von dynamischen Schemaspalten aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)