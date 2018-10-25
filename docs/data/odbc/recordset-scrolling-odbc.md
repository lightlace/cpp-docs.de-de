---
title: 'Recordset: Scrollen (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f8b5107f6e264c5d9915e809c9d198fd4cc4ba24
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053239"
---
# <a name="recordset-scrolling-odbc"></a>Recordset: Scrollen (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Nach dem Öffnen eines Recordsets, müssen Sie die Datensätze zum Anzeigen von Werten, den Zugriff auf Berechnungen ausführen, Generieren von Berichten und so weiter. Scrollen können, die Sie von Datensatz zu Datensatz im Recordset verschieben.

In diesem Thema wird Folgendes erläutert:

- [Wie Sie von einem Datensatz in eine andere in einem Recordset Scrollen](#_core_scrolling_from_one_record_to_another).

- [Unter welche Umständen Durchführen eines Bildlaufs ist und wird nicht unterstützt](#_core_when_scrolling_is_supported).

##  <a name="_core_scrolling_from_one_record_to_another"></a> Durchführen eines Bildlaufs aus einem Datensatz in eine andere

Klasse `CRecordset` bietet die `Move` Memberfunktionen für das Scrollen innerhalb eines Recordsets. Diese Funktionen Verschieben des aktuellen Datensatzes von Rowsets. Wenn Sie implementiert haben, gesammelte eine `Move` Vorgang verschiebt das Recordset, um die Größe des Rowsets. Wenn Sie das gesammelte Abrufen von, handelt es sich bei einem Aufruf von nicht implementiert haben eine `Move` -Funktion verschiebt das Recordset um einen Datensatz jeweils. Weitere Informationen zu gesammelten Abrufens von Zeilen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
>  Beim Verschieben von durch ein Recordset möglicherweise gelöschte Datensätze werden nicht übersprungen. Weitere Informationen finden Sie unter den [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) Member-Funktion.

Zusätzlich zu den `Move` Funktionen `CRecordset` stellt Memberfunktionen zum Überprüfen, ob Sie über das Ende oder Anfang des Recordset gescrollt haben.

Um zu bestimmen, ob Scrollen im Recordset möglich ist, rufen Sie die `CanScroll` Member-Funktion.

#### <a name="to-scroll"></a>Scrollen

1. Einen Datensatz oder ein Rowset vorwärts: Rufen Sie die [MoveNext](../../mfc/reference/crecordset-class.md#movenext) Member-Funktion.

1. Rückwärts einen Datensatz oder ein Rowset: Rufen Sie die [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) Member-Funktion.

1. Zu den ersten Datensatz im Recordset: Rufen Sie die [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) Member-Funktion.

1. Um den letzten Datensatz im Recordset oder des letzten Rowsets: Rufen Sie die [MoveLast](../../mfc/reference/crecordset-class.md#movelast) Member-Funktion.

1. *N* Datensätze relativ zur aktuellen Position: Rufen Sie die [verschieben](../../mfc/reference/crecordset-class.md#move) Member-Funktion.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>So testen Sie das Ende oder Anfang des Recordset-Objekts

1. Haben Sie hinter dem letzten Datensatz werden gescrollt? Rufen Sie die [IsEOF](../../mfc/reference/crecordset-class.md#iseof) Member-Funktion.

1. Haben Sie einen Bildlauf vor den ersten Datensatz (rückwärts) durchgeführt? Rufen Sie die [IsBOF](../../mfc/reference/crecordset-class.md#isbof) Member-Funktion.

Das folgende Codebeispiel verwendet `IsBOF` und `IsEOF` um die Grenzen eines Recordsets in beide Richtungen Durchführen eines Bildlaufs zu erkennen.

```
// Open a recordset; first record is current
CCustSet rsCustSet( NULL );
rsCustSet.Open( );

if( rsCustSet.IsBOF( ) )
    return;
    // The recordset is empty

// Scroll to the end of the recordset, past
// the last record, so no record is current
while ( !rsCustSet.IsEOF( ) )
    rsCustSet.MoveNext( );

// Move to the last record
rsCustSet.MoveLast( );

// Scroll to beginning of the recordset, before
// the first record, so no record is current
while( !rsCustSet.IsBOF( ) )
    rsCustSet.MovePrev( );

// First record is current again
rsCustSet.MoveFirst( );
```

`IsEOF` Gibt einen Wert ungleich NULL zurück, wenn das Recordset hinter dem letzten Datensatz positioniert ist. `IsBOF` Gibt einen Wert ungleich NULL zurück, wenn das Recordset, vor dem ersten Datensatz (vor allen Datensätzen positioniert ist). In beiden Fällen besteht kein aktueller Datensatz zu verarbeitende zur Verfügung. Aufrufen `MovePrev` beim `IsBOF` ist bereits auf "true" fest, oder rufen Sie `MoveNext` beim `IsEOF` bereits TRUE ist, löst das Framework eine `CDBException`. Sie können auch `IsBOF` und `IsEOF` zu prüfen, eine leere Datensatzgruppe.

Weitere Informationen zur Recordsetnavigation, finden Sie unter [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="_core_when_scrolling_is_supported"></a> Beim Durchführen eines Bildlaufs unterstützt wird

Als ursprünglich entwickelte SQL bereitgestellten Bildlauf ausschließlich vorwärts ausgeführt, aber ODBC erweitert die Bildlauf-Funktionen. Das verfügbare Maß an Unterstützung für das Scrollen, hängt die ODBC-Treiber, die die Anwendung mit ODBC-API-Konformitätsgrad des Treibers funktioniert, und gibt an, ob die ODBC-Cursorbibliothek geladen ist. Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [ODBC: die ODBC-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!TIP]
>  Sie können steuern, ob die Cursorbibliothek verwendet wird. Finden Sie unter den *bUseCursorLib* und *DwOptions* Parameter [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open).

> [!NOTE]
>  Im Gegensatz zu den MFC-DAO-Klassen, die MFC-ODBC-Klassen nicht bieten eine Reihe von `Find` Funktionen für Suchen der nächsten (oder vorherigen) Datensatzes, erfüllt die Kriterien angegeben.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)