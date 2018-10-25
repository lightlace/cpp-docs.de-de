---
title: Aktualisieren von Rowsets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/19/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4bac44066cae267e0b44d21a839de7ecdd9f2a5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057998"
---
# <a name="updating-rowsets"></a>Aktualisieren von Rowsets

Ein basic-Datenbank-Vorgang wird zum Aktualisieren oder Schreiben von Daten in den Datenspeicher. In OLE DB ist der Aktualisierungsmechanismus einfach: Die Consumeranwendung legt die Werte gebundener Datenmember fest und schreibt diese Werte dann in das Rowset. Anschließend fordert der Consumer den Anbieter auf, den Datenspeicher zu aktualisieren.

Kunden können die folgenden Arten von Updates auf Rowsetdaten abschließen: Festlegen von Spaltenwerten in einer Zeile, eine Zeile einfügen und Löschen einer Zeile. Zum Durchführen dieser Vorgänge, die OLE DB-Vorlagenklasse [CRowset](../../data/oledb/crowset-class.md) implementiert die [IRowsetChange](/previous-versions/windows/desktop/ms715790) -Schnittstelle und überschreibt die folgenden Schnittstellenmethoden:

- [SetData](../../data/oledb/crowset-setdata.md) ändert Spaltenwerte in einer Zeile eines Rowsets; es ist gleichbedeutend mit der SQL-Befehl UPDATE.

- [Fügen Sie](../../data/oledb/crowset-insert.md) Fügt eine Zeile in einem Rowset; es ist gleichbedeutend mit der SQL-Befehl INSERT.

- [Löschen Sie](../../data/oledb/crowset-delete.md) löscht Zeilen aus einem Rowset; es ist gleichbedeutend mit der SQL-DELETE-Befehl.

## <a name="supporting-update-operations"></a>Unterstützen von Aktualisierungsoperationen

Bei der Erstellung eines Consumers mit der **ATL-OLE DB-Consumer-Assistenten**, können Sie die Aktualisierungsoperationen unterstützen, durch die Auswahl einer oder mehrere der drei Kontrollkästchen **Änderung**, **einfügen**, und **löschen**. Wenn Sie diese Optionen auswählen, ändert der Assistent den Code entsprechend um den Typ der Änderungen zu unterstützen, die Sie auswählen. Jedoch wenn Sie den Assistenten nicht verwenden, müssen Sie die folgenden Rowseteigenschaften festgelegt werden, um `VARIANT_TRUE` um Updates zu unterstützen:

- `DBPROPVAL_UP_CHANGE` können Sie die Datenwerte in einer Zeile ändern.

- `DBPROPVAL_UP_INSERT` ermöglicht Ihnen, eine Zeile einzufügen.

- `DBPROPVAL_UP_DELETE` können Sie eine Zeile zu löschen.

Legen Sie die Eigenschaften wie folgt fest:

```cpp
CDBPropSet ps(DBPROPSET_ROWSET);

ps.AddProperty(DBPROP_IRowsetChange, true);
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
```

Ändern, INSERT- oder Delete-Vorgänge fehlschlagen, wenn eine oder mehrere Spalten ist nicht beschreibbar. Ändern Sie die cursorzuordnung, um dieses Problem zu beheben.

## <a name="setting-data-in-rows"></a>Festlegen von Daten in Zeilen

[CRowset::SetData](../../data/oledb/crowset-setdata.md) legt Datenwerte in einer oder mehreren Spalten der aktuellen Zeile fest. Der folgende Code legt die Werte der Datenelemente, die an die Spalten gebunden `Name` und `Units in Stock` der Tabelle `Products` und ruft dann `SetData` um diese Werte in der 100. Zeile des Rowsets zu schreiben:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_UnitsInStock = 10000;

// Set the data
HRESULT hr = product.SetData();
```

## <a name="inserting-rows-into-rowsets"></a>Einfügen von Zeilen in Rowsets

[CRowset::Insert](../../data/oledb/crowset-insert.md) erstellt und initialisiert eine neue Zeile unter Verwendung von Daten aus dem Accessor. `Insert` erstellt eine vollständig neue Zeile nach der aktuellen Zeile. Sie müssen angeben, ob die aktuelle Zeile zur nächsten Zeile inkrementiert oder unverändert bleiben. Hierzu müssen Sie den Parameter *bGetRow* festlegen:

```cpp
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)
```

- **false** (der Standardwert) gibt an, dass die aktuelle Zeile zur nächsten Zeile inkrementiert wird. (In diesem Fall wird auf die eingefügte Zeile verwiesen.)

- **"true"** gibt an, dass die aktuelle bleiben Zeile ist.

Der folgende Code legt die Werte der Datenelemente, die an die Spalten der Tabelle gebunden `Products` und ruft dann `Insert` um eine neue Zeile mit diesen Werten nach der 100. Zeile des Rowsets einzufügen. Es wird empfohlen, dass Sie festlegen, dass alle Spaltenwerte nicht definierte Daten in der neuen Zeile zu vermeiden:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Set the column values for a row of the Product table, then insert the row
product.m_ProductID = 101;
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_SupplierID = 27857;
product.m_CategoryID = 372;
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit, _T( "Pack of 10" ) );

product.m_UnitPrice = 20;
product.m_UnitsInStock = 10000;
product.m_UnitsOnOrder = 5201;
product.m_ReorderLevel = 5000;
product.m_Discontinued = false;

// You must also initialize the status and length fields before setting/inserting data
// Set the column status values
m_dwProductIDStatus = DBSTATUS_S_OK;
m_dwProductNameStatus = DBSTATUS_S_OK;
m_dwSupplierIDStatus = DBSTATUS_S_OK;
m_dwCategoryIDStatus = DBSTATUS_S_OK;
m_dwQuantityPerUnitStatus = DBSTATUS_S_OK;
m_dwUnitPriceStatus = DBSTATUS_S_OK;
m_dwUnitsInStockStatus = DBSTATUS_S_OK;
m_dwUnitsOnOrderStatus = DBSTATUS_S_OK;
m_dwReorderLevelStatus = DBSTATUS_S_OK;
m_dwDiscontinuedStatus = DBSTATUS_S_OK;

// Set the column length value for column data members that are not fixed-length types.
// The value should be the length of the string that you are setting.
m_dwProductNameLength = 6;             // "Candle" has 6 characters
m_dwQuantityPerUnitLength = 10;        // "Pack of 10" has 10 characters

// Insert the data
HRESULT hr = product.Insert();
```

Ein ausführlicheres Beispiel finden Sie unter [CRowset::Insert](../../data/oledb/crowset-insert.md).

Weitere Informationen zum Festlegen der Datenmember für Status und Länge finden Sie unter [Feldstatus-Datenmember in vom Assistenten generierten Accessoren](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

## <a name="deleting-rows-from-rowsets"></a>Löschen von Zeilen aus Rowsets

[CRowset::Delete](../../data/oledb/crowset-delete.md) löscht die aktuelle Zeile aus dem Rowset. Der folgende code ruft `Delete` die 100. Zeile des Rowsets zu entfernen:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Delete the row
HRESULT hr = product.Delete();
```

## <a name="immediate-and-deferred-updates"></a>Unverzügliche und verzögerte Aktualisierungen

Es sei denn, Sie nichts anderes angeben möchten, Aufrufe an die `SetData`, `Insert`, und `Delete` Methoden Aktualisierung des Datenspeichers sofort. Sie können Aktualisierungen jedoch verzögern. Der Consumer speichert hierbei alle Änderungen in einem lokalen Cache und überträgt sie an den Datenspeicher, wenn eine der folgenden Aktualisierungsmethoden aufgerufen wird:

- [CRowset:: Update](../../data/oledb/crowset-update.md) überträgt alle Änderungen, die an der aktuellen Zeile seit der letzten Fetch oder `Update` für ihn aufrufen.

- [CRowset:: UpdateAll](../../data/oledb/crowset-updateall.md) überträgt alle Änderungen, die seit der letzten Abruf auf alle Zeilen oder `Update` für ihn aufrufen.

Update von updatemethoden verwendet der spezifischen Bedeutung von Änderungen auf Befehl und ist nicht zu verwechseln mit der SQL **aktualisieren** Befehl (`SetData` ist gleichbedeutend mit der SQL **aktualisieren** Befehl) .

Es sind verzögerte Aktualisierungen sinnvoll sein, z. B. in Situationen, z. B. eine Reihe von Banktransaktionen; Wenn eine Transaktion abgebrochen wird, können Sie die Änderung rückgängig zu machen, da Sie nicht die Reihe von Änderungen erst senden, nach der zuletzt ein Commit ausgeführt wird. Der Anbieter kann die Änderungen auch in einem Netzwerkaufruf bündeln. Dies ist eine noch effizientere Methode.

Um verzögerte Aktualisierungen zu unterstützen, müssen Sie festlegen der `DBPROP_IRowsetChange` Eigenschaft zusammen mit den Eigenschaften, die in beschriebenen **unterstützen von Aktualisierungsoperationen**:

```cpp
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);
```

Beim Aufruf `Update` oder `UpdateAll`, die Methoden Änderungen vom lokalen Cache mit dem Datenspeicher zu übertragen und anschließend wird der lokale Cache bereinigt. Da Update Änderungen nur für die aktuelle Zeile übertragen, ist es wichtig, welche Zeile wann aktualisiert in der Ihre Anwendung gespeichert werden. Im folgenden Beispiel wird das Aktualisieren von zwei aufeinander folgenden Zeilen demonstriert:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Wick" ) );

product.m_UnitsInStock = 10000;

HRESULT hr = product.SetData();  // No changes made to row 100 yet
product.Update();                 // Update row 100 now

// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table
product.MoveNext();

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName _T( "Wax" ) );

product.m_UnitsInStock = 500;

HRESULT hr = product.SetData();  // No changes made to row 101 yet
product.Update();                 // Update row 101 now
```

Um sicherzustellen, dass vorgenommene Änderungen übertragen werden, rufen Sie `Update` vor dem Verschieben in eine andere Zeile. Erscheint Ihnen dies jedoch als zu aufwendig oder ineffizient, z. B. wenn die Anwendung Hunderte von Zeilen aktualisieren muss, können Sie mithilfe von `UpdateAll` alle Zeilen auf einmal aktualisieren.

Z. B. wenn die erste `Update` -Aufruf im oben stehenden Code fehlen würde, Zeile 100 verbleiben unverändert, während Zeile 101 geändert würde. Nach diesem Punkt die Anwendung entweder müssten Aufrufen `UpdateAll` oder Aufruf zu Zeile 100 zurückgehen `Update` für diese Zeile aktualisiert werden.

Schließlich ist einer der Hauptgründe für die Verwendung verzögerter Aktualisierungen die Möglichkeit, sie rückgängig machen zu können. Wenn Sie [CRowset::Undo](../../data/oledb/crowset-undo.md) aufrufen, wird der lokale Änderungscache auf den Status des Datenspeichers vor dem Ausführen der Änderungen zurückgesetzt. Es ist wichtig zu beachten, dass `Undo` nicht genutzt haben, den Status des lokalen Caches einschrittigen (den Zustand vor der letzten Änderung) zurücksetzt, stattdessen es den lokalen Cache für die Zeile gelöscht. Darüber hinaus `Undo` wirkt sich auf nur die aktuelle Zeile.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[CRowset-Klasse](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790)<br/>
