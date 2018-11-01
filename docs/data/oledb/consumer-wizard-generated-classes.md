---
title: Vom Consumer-Assistenten generierte Klassen
ms.date: 10/17/2018
helpviewer_keywords:
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- command classes in OLE DB consumer
- classes [C++], OLE DB Consumer Wizard-generated
- consumer wizard-generated classes and methods
- user record classes in OLE DB consumer
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
ms.openlocfilehash: 2ebc2094ba7f12087de51119a134e2ef65ef92d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641137"
---
# <a name="consumer-wizard-generated-classes"></a>Vom Consumer-Assistenten generierte Klassen

Bei Verwendung der **ATL-OLE DB-Consumer-Assistenten** zum Generieren von eines Consumers, die Sie haben die Möglichkeit der Verwendung von OLE DB-Vorlagen oder OLE DB-Attribute. In beiden Fällen generiert der Assistent eine Befehlsklasse und eine Benutzerdatensatz-Klasse. Die Befehlsklasse enthält Code zum Öffnen der Datenquelle und des Rowsets, die Sie im Assistenten angegeben haben. Die Benutzerdatensatz-Klasse enthält Spaltenzuordnung für die ausgewählte Datenbanktabelle. Der generierte Code unterscheidet sich jedoch in beiden Fällen:

- Wenn Sie einen auf einer Vorlage basierenden Consumer auswählen, erstellt der Assistent eine Befehlsklasse und eine Benutzerdatenbank-Klasse. Die Command-Klasse hat den Namen, den Sie, in eingeben der **Klasse** Feld im Assistenten (z. B. `CProducts`), und die Benutzerdatensatz-Klasse hat einen Namen im Format "*ClassName*Accessor" (z. b. `CProductsAccessor`). Beide Klassen werden in der Headerdatei des Consumers platziert.

- Wenn Sie einen auf Consumer mit Attributbeteiligung auswählen, hat die Benutzerdatensatz-Klasse einen Namen der Form „_*KlassenName*-Accessor“ und wird injiziert. Also müssen Sie nur die Befehlsklasse im Text-Editor angezeigt werden sollen; Sie können die Benutzerdatensatz-Klasse nur als injizierten Code anzeigen. Informationen zum Anzeigen von injiziertem Code finden Sie unter [Debuggen von injiziertem Code](/visualstudio/debugger/how-to-debug-injected-code).

Die folgenden Beispiele verwenden eine Befehlsklasse erstellt die `Products` Tabelle mit den `Northwind` Datenbank, um den-Assistenten generierten Consumercode für die Klasse des Befehls und die Benutzerdatensatz-Klasse zu veranschaulichen.

## <a name="templated-user-record-classes"></a>Auf einer Vorlage basierende Benutzerdatensatz-Klassen

Wenn Sie mithilfe der OLE DB-Vorlagen (anstelle der OLE DB-Attribute) einen OLE DB-Consumer erstellen, generiert der Assistent Code, wie er in diesem Abschnitt beschrieben wird.

### <a name="column-data-members"></a>Spaltendatenmember

Der erste Teil der Benutzerdatensatz-Klasse enthält die Datenmemberdeklarationen und die Status- und Längedatenmember für jede datengebundene Spalte. Informationen zu diesen Datenmembern finden Sie unter [Feldstatus-Datenmember in vom Assistenten generierten Accessoren](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

> [!NOTE]
> Wenn Sie die Benutzerdatensatz-klasse ändern oder einen eigenen Consumer erstellen, müssen die Datenvariablen in der Reihenfolge vor den Status- und Längenvariablen liegen.

> [!NOTE]
> Der ATL-OLE DB-Consumer-Assistent verwendet die `DB_NUMERIC` Typ zum Binden von numerischen Datentypen. Es früher verwendete `DBTYPE_VARNUMERIC` (das Format wird durch beschrieben die `DB_VARNUMERIC` geben; Siehe "OleDb.h"). Wenn Sie den Assistenten zum Erstellen von Consumern nicht verwenden, wird empfohlen, Sie verwenden `DB_NUMERIC`.

```cpp
// Products.H : Declaration of the CProducts class

class CProductsAccessor
{
public:
   // Column data members:
   LONG m_ProductID;
   TCHAR m_ProductName[41];
   LONG m_SupplierID;
   LONG m_CategoryID;
   TCHAR m_QuantityPerUnit[21];
   CURRENCY m_UnitPrice;
   SHORT m_UnitsInStock;
   SHORT m_UnitsOnOrder;
   SHORT m_ReorderLevel;
   VARIANT_BOOL m_Discontinued;

   // Column status data members:
   DBSTATUS m_dwProductIDStatus;
   DBSTATUS m_dwProductNameStatus;
   DBSTATUS m_dwSupplierIDStatus;
   DBSTATUS m_dwCategoryIDStatus;
   DBSTATUS m_dwQuantityPerUnitStatus;
   DBSTATUS m_dwUnitPriceStatus;
   DBSTATUS m_dwUnitsInStockStatus;
   DBSTATUS m_dwUnitsOnOrderStatus;
   DBSTATUS m_dwReorderLevelStatus;
   DBSTATUS m_dwDiscontinuedStatus;

   // Column length data members:
   DBLENGTH m_dwProductIDLength;
   DBLENGTH m_dwProductNameLength;
   DBLENGTH m_dwSupplierIDLength;
   DBLENGTH m_dwCategoryIDLength;
   DBLENGTH m_dwQuantityPerUnitLength;
   DBLENGTH m_dwUnitPriceLength;
   DBLENGTH m_dwUnitsInStockLength;
   DBLENGTH m_dwUnitsOnOrderLength;
   DBLENGTH m_dwReorderLevelLength;
   DBLENGTH m_dwDiscontinuedLength;
```

### <a name="rowset-properties"></a>Rowset-Eigenschaften

Anschließend legt der Assistent die Rowset-Eigenschaften fest. Wenn Sie im ATL-OLE DB-Consumer-Assistenten **Ändern**, **Einfügen**oder **Löschen** ausgewählt haben, werden die entsprechenden Eigenschaften hier festgelegt (DBPROP_IRowsetChange ist immer festgelegt, dann kommen DBPROPVAL_UP_CHANGE, DBPROPVAL_UP_INSERT, und/oder DBPROPVAL_UP_DELETE hinzu).

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="command-or-table-class"></a>Befehls- oder Tabellenklasse

Wenn Sie eine Befehlsklasse angeben, deklariert der Assistent die Befehlsklasse; bei auf einer Vorlage basierendem Code sieht der Befehl so aus:

```cpp
DEFINE_COMMAND_EX(CProductsAccessor, L" \
SELECT \
   ProductID, \
   ProductName, \
   SupplierID, \
   CategoryID, \
   QuantityPerUnit, \
   UnitPrice, \
   UnitsInStock, \
   UnitsOnOrder, \
   ReorderLevel, \
   Discontinued \
   FROM dbo.Products")
```

### <a name="column-map"></a>Spaltenzuordnung

Anschließend generiert der Assistent die Spaltenbindungen oder Spaltenzuordnung. Um verschiedene Probleme mit einigen Anbietern zu beheben, bindet der folgende Code Spalten möglicherweise in einer anderen Reihenfolge als vom Anbieter gemeldet.

```cpp
   BEGIN_COLUMN_MAP(CProductsAccessor)
      COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
      COLUMN_ENTRY_LENGTH_STATUS(3, m_SupplierID, m_dwSupplierIDLength, m_dwSupplierIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(4, m_CategoryID, m_dwCategoryIDLength, m_dwCategoryIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(5, m_QuantityPerUnit, m_dwQuantityPerUnitLength, m_dwQuantityPerUnitStatus)
      _COLUMN_ENTRY_CODE(6, DBTYPE_CY, _SIZE_TYPE(m_UnitPrice), 0, 0, offsetbuf(m_UnitPrice), offsetbuf(m_dwUnitPriceLength), offsetbuf(m_dwUnitPriceStatus))
      COLUMN_ENTRY_LENGTH_STATUS(7, m_UnitsInStock, m_dwUnitsInStockLength, m_dwUnitsInStockStatus)
      COLUMN_ENTRY_LENGTH_STATUS(8, m_UnitsOnOrder, m_dwUnitsOnOrderLength, m_dwUnitsOnOrderStatus)
      COLUMN_ENTRY_LENGTH_STATUS(9, m_ReorderLevel, m_dwReorderLevelLength, m_dwReorderLevelStatus)
      _COLUMN_ENTRY_CODE(10, DBTYPE_BOOL, _SIZE_TYPE(m_Discontinued), 0, 0, offsetbuf(m_Discontinued), offsetbuf(m_dwDiscontinuedLength), offsetbuf(m_dwDiscontinuedStatus))
   END_COLUMN_MAP()
};
```

### <a name="class-declaration"></a>Klassendeklaration

Schließlich generiert der Assistent eine Klassendeklaration wie etwa die folgende:

```cpp
class CProducts : public CCommand<CAccessor<CProductsAccessor>>
```

## <a name="attribute-injected-user-record-classes"></a>Benutzerdatensatz-Klasse mit Attributbeteiligung

Wenn Sie einen OLE DB-Consumer mithilfe der Datenbankattribute ([db_command](../../windows/db-command.md) oder [db_table](../../windows/db-table.md)) erstellen, injizieren die Attribute eine Benutzerdatensatz-Klasse mit einem Namen der Form "_*ClassName*Accessor." Wenn Sie Ihre Befehlsklasse beispielsweise `COrders`genannt haben, heißt die Benutzerdatensatz-Klasse `_COrdersAccessor`. Obwohl die Benutzerdatensatz-Klasse, die in angezeigt wird **Klassenansicht**, Doppelklick auf die Klasse Befehl oder eine Tabelle in der Headerdatei navigiert. In diesen Fällen können Sie die eigentliche Deklaration der Benutzerdatensatz-Klasse nur durch Anzeigen des durch die Attribute injizierten Codes zu sehen bekommen.

Das Hinzufügen oder Überschreiben von Methoden in Consumern mit Attributbeteiligung führt möglicherweise zu Komplikationen. Beispielsweise können Sie der `_COrdersAccessor` -Deklaration einen `COrders` -Konstruktor hinzufügen, beachten Sie aber, dass dadurch tatsächlich der injizierten `COrdersAccessor` -Klasse ein Konstruktor hinzugefügt wird. Ein solcher Konstruktor kann die Spalten/Parameter initialisieren, aber Sie können nicht keinen Kopierkonstruktor erstellen auf diese Weise, da er nicht direkt instanziieren kann die `COrdersAccessor` Objekt. Bei Bedarf einen Konstruktor (oder andere Methode) direkt auf die `COrders` -Klasse, es wird empfohlen, dass Sie eine neue Klasse ableiten von definieren `COrders` und die erforderlichen Methoden hinzufügen.

Im folgenden Beispiel generiert der Assistent eine Deklaration für die Klasse `COrders`, aber die Benutzerdatensatz-Klasse `COrdersAccessor` nicht angezeigt wird, da die Attribute sie injizieren.

```cpp
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>
[
   db_source(L"your connection string"),
   db_command(L"Select ShipName from Orders;")
]
class COrders
{
public:

   // COrders()            // incorrect constructor name
   _COrdersAccessor()      // correct constructor name
   {
   }
      [db_column(1) ] TCHAR m_ShipName[41];
   };
```

Die Deklaration der injizierten Befehlsklasse sieht wie folgt aus:

```cpp
class CProducts : public CCommand<CAccessor<_CProductsAccessor>>
```

Der größte Teil des injizierten Codes ist mit dem der vorlagenbasierten Version identisch oder ihm ähnlich. Die Hauptunterschiede liegen in den injizierten Methoden, die unter [Vom Consumer-Assistenten generierte Methoden](../../data/oledb/consumer-wizard-generated-methods.md)beschrieben sind.

Informationen zum Anzeigen von injiziertem Code finden Sie unter [Debuggen von injiziertem Code](/visualstudio/debugger/how-to-debug-injected-code).

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)