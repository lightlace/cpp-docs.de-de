---
title: 'Recordset: Lesezeichen und absolute Positionen (ODBC)'
ms.date: 11/04/2016
f1_keywords:
- SetAbsolutePosition
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
ms.openlocfilehash: 826c1c0124eb261c97fff8f1e2fa01c8becb073a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500937"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Recordset: Lesezeichen und absolute Positionen (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Wenn Sie über ein Recordset zu navigieren, benötigen Sie häufig eine Möglichkeit, zu einem bestimmten Datensatz zurückgeben. Geben Sie zwei Methoden, Lesezeichen und absolute Position eines Datensatzes.

In diesem Thema wird Folgendes erläutert:

- [Verwendung von Lesezeichen](#_core_bookmarks_in_mfc_odbc).

- [Gewusst wie: Festlegen des aktuellen Datensatzes, der mithilfe von absoluter Positionen](#_core_absolute_positions_in_mfc_odbc).

##  <a name="_core_bookmarks_in_mfc_odbc"></a> Lesezeichen im MFC-ODBC

Ein Lesezeichen identifiziert eindeutig einen Datensatz. Wenn Sie über ein Recordset navigieren, können nicht Sie immer auf die absolute Position eines Datensatzes verlassen, da Datensätze aus dem Recordset nicht gelöscht werden können. Die zuverlässige Möglichkeit zum Nachverfolgen die Position eines Datensatzes ist die Verwendung des Lesezeichens. Klasse `CRecordset` stellt Memberfunktionen zur:

- Abrufen des Lesezeichens für den aktuellen Datensatz aus, damit Sie sie in einer Variablen speichern können ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).

- Schnelles Navigieren zu einem bestimmten Datensatz durch Angabe des Lesezeichens, das Sie zuvor in einer Variablen gespeichert ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).

Das folgende Beispiel veranschaulicht, wie Sie markieren den aktuellen Datensatz und später zurückkehren, damit diese Memberfunktionen mit:

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

Sie müssen nicht zum Extrahieren des zugrunde liegende Datentyp aus der [CDBVariant-Klasse](../../mfc/reference/cdbvariant-class.md) Objekt. Weisen Sie den Wert mit `GetBookmark` und zurück zu diesem Lesezeichen mit `SetBookmark`.

> [!NOTE]
>  Lesezeichen können je nach ODBC-Treiber und der Recordsettyp nicht unterstützt. Sie können problemlos ermitteln, ob Lesezeichen, durch den Aufruf unterstützt werden [CRecordset:: CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark). Darüber hinaus Lesezeichen unterstützt, Sie müssen explizit auswählen, zur Implementierung durch Angabe der `CRecordset::useBookmarks` option die [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) Member-Funktion. Sie sollten auch die Beibehaltung von Lesezeichen nach bestimmten Vorgängen Recordset überprüfen. Z. B. Wenn Sie `Requery` eines Recordsets Lesezeichen möglicherweise nicht mehr gültig sein. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.

##  <a name="_core_absolute_positions_in_mfc_odbc"></a> Absolute Positionen in MFC-ODBC

Neben Lesezeichen Klasse `CRecordset` können Sie den aktuellen Datensatz festlegen, durch eine Ordnungsposition angeben. Dies wird als absolute Positionierung bezeichnet.

> [!NOTE]
>  Es ist nicht verfügbar, auf die Forward-only-Recordsets, absolute Positionierung. Weitere Informationen zu Forward-only-Recordsets, finden Sie unter [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md).

Aufrufen, um den Zeiger für den aktuellen Datensatz mithilfe einer absoluten Position zu verschieben, [CRecordset:: SetAbsolutePosition auf](../../mfc/reference/crecordset-class.md#setabsoluteposition). Wenn Sie einen Wert übergeben `SetAbsolutePosition`, den Datensatz entsprechend, dass die Ordinalposition des aktuellen Datensatzes ist.

> [!NOTE]
>  Die absolute Position eines Datensatzes ist möglicherweise unzuverlässig. Wenn der Benutzer die Datensätze aus dem Recordset, die die Ordnungsposition der nachfolgende Datensatz Änderungen löscht. Lesezeichen sind die empfohlene Methode zum Verschieben des aktuellen Datensatzes an. Weitere Informationen finden Sie unter [Lesezeichen in MFC ODBC](#_core_bookmarks_in_mfc_odbc).

Weitere Informationen zur Recordsetnavigation, finden Sie unter [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)