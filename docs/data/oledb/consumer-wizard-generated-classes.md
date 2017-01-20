---
title: "Vom Consumer-Assistenten generierte Klassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen und Methoden mit Attributbeteiligung"
  - "Vom Assistenten generierte Klassen und Methoden"
  - "OLE DB-Consumer, von Assistenten generierte Klassen und Methoden"
  - "Befehlsklassen im OLE DB-Consumer"
  - "Klassen [C++], OLE DB-Consumer von Assistenten generiert"
  - "Vom Consumer-Assistenten generierte Klassen und Methoden"
  - "Benutzerdatensatzklassen im OLE DB-Consumer"
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Vom Consumer-Assistenten generierte Klassen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie den ATL OLE DB\-Consumer\-Assistenten zum Erstellen eines Consumers verwenden, haben Sie die Wahl, ob Sie OLE DB\-Vorlagen oder OLE DB\-Attribute verwenden möchten. In beiden Fällen generiert der Assistent eine Befehlsklasse und eine Benutzerdatensatz\-Klasse. Die Befehlsklasse enthält Code zum Öffnen der Datenquelle und des Rowsets, die Sie im Assistenten angegeben haben. Die Benutzerdatensatz\-Klasse enthält Spaltenzuordnung für die ausgewählte Datenbanktabelle. Der generierte Code unterscheidet sich jedoch in beiden Fällen:  
  
-   Wenn Sie einen auf einer Vorlage basierenden Consumer auswählen, erstellt der Assistent eine Befehlsklasse und eine Benutzerdatenbank\-Klasse. Die Befehlsklasse weist den Namen auf, den Sie im Assistenten im Feld „Klasse“ eingeben \(beispielsweise `CProducts`\), und die Benutzerdatensatz\-Klasse hat einen Namen der Form „*KlassenName*\-Accessor“ \(beispielsweise `CProductsAccessor`\). Beide Klassen werden in der Headerdatei des Consumers platziert.  
  
-   Wenn Sie einen auf Consumer mit Attributbeteiligung auswählen, hat die Benutzerdatensatz\-Klasse einen Namen der Form „\_*KlassenName*\-Accessor“ und wird injiziert. Das heißt, Sie können nur die Befehlsklasse im Texteditor sehen; Sie können die Benutzerdatensatz\-Klasse nur als injizierten Code sehen. Informationen zum Anzeigen von injiziertem Code finden Sie unter [Debuggen von injiziertem Code](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
 Die folgenden Beispiele verwenden eine in der Tabelle „Products“ der Northwind\-Datenbank erstellte Befehlsklasse, um den vom Assistenten generierten Benutzercode für die Befehlsklasse und die Benutzerdatenbank\-Klasse zu veranschaulichen.  
  
## Auf einer Vorlage basierende Benutzerdatensatz\-Klassen  
 Wenn Sie mithilfe der OLE DB\-Vorlagen \(anstelle der OLE DB\-Attribute\) einen OLE DB\-Consumer erstellen, generiert der Assistent Code, wie er in diesem Abschnitt beschrieben wird.  
  
### Spaltendatenmember  
 Der erste Teil der Benutzerdatensatz\-Klasse enthält die Datenmemberdeklarationen und die Status\- und Längedatenmember für jede datengebundene Spalte. Informationen zu diesen Datenmembern finden Sie unter [Feldstatus\-Datenmember in vom Assistenten generierten Accessoren](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
> [!NOTE]
>  Wenn Sie die Benutzerdatensatz\-klasse ändern oder einen eigenen Consumer erstellen, müssen die Datenvariablen in der Reihenfolge vor den Status\- und Längenvariablen liegen.  
  
> [!NOTE]
>  Der ATL\-OLE DB\-Consumer\-Assistent verwendet den Typ **DB\_NUMERIC** zum Binden von numerischen Datentypen. Zuvor wurde dazu **DBTYPE\_VARNUMERIC** verwendet \(das Format dieses Typs wird durch den **DB\_VARNUMERIC**\-Typ beschrieben; siehe „Oledb.h“\). Wenn Sie zum Erstellen von Consumern nicht den Assistenten verwenden, wird die Verwendung von **DB\_NUMERIC** empfohlen.  
  
```  
// Products.H : Declaration of the CProducts class class CProductsAccessor { public: // Column data members: LONG m_ProductID; TCHAR m_ProductName[41]; LONG m_SupplierID; LONG m_CategoryID; TCHAR m_QuantityPerUnit[21]; CURRENCY m_UnitPrice; SHORT m_UnitsInStock; SHORT m_UnitsOnOrder; SHORT m_ReorderLevel; VARIANT_BOOL m_Discontinued; // Column status data members: DBSTATUS m_dwProductIDStatus; DBSTATUS m_dwProductNameStatus; DBSTATUS m_dwSupplierIDStatus; DBSTATUS m_dwCategoryIDStatus; DBSTATUS m_dwQuantityPerUnitStatus; DBSTATUS m_dwUnitPriceStatus; DBSTATUS m_dwUnitsInStockStatus; DBSTATUS m_dwUnitsOnOrderStatus; DBSTATUS m_dwReorderLevelStatus; DBSTATUS m_dwDiscontinuedStatus; // Column length data members: DBLENGTH m_dwProductIDLength; DBLENGTH m_dwProductNameLength; DBLENGTH m_dwSupplierIDLength; DBLENGTH m_dwCategoryIDLength; DBLENGTH m_dwQuantityPerUnitLength; DBLENGTH m_dwUnitPriceLength; DBLENGTH m_dwUnitsInStockLength; DBLENGTH m_dwUnitsOnOrderLength; DBLENGTH m_dwReorderLevelLength; DBLENGTH m_dwDiscontinuedLength;  
```  
  
### Rowset\-Eigenschaften  
 Anschließend legt der Assistent die Rowset\-Eigenschaften fest. Wenn Sie im ATL\-OLE DB\-Consumer\-Assistenten **Ändern**, **Einfügen** oder **Löschen** ausgewählt haben, werden die entsprechenden Eigenschaften hier festgelegt \(DBPROP\_IRowsetChange ist immer festgelegt, dann kommen DBPROPVAL\_UP\_CHANGE, DBPROPVAL\_UP\_INSERT, und\/oder DBPROPVAL\_UP\_DELETE hinzu\).  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet) { pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE); }  
```  
  
### Befehls\- oder Tabellenklasse  
 Wenn Sie eine Befehlsklasse angeben, deklariert der Assistent die Befehlsklasse; bei auf einer Vorlage basierendem Code sieht der Befehl so aus:  
  
```  
DEFINE_COMMAND_EX(CProductsAccessor, L" \ SELECT \ ProductID, \ ProductName, \ SupplierID, \ CategoryID, \ QuantityPerUnit, \ UnitPrice, \ UnitsInStock, \ UnitsOnOrder, \ ReorderLevel, \ Discontinued \ FROM dbo.Products")  
```  
  
### Spaltenzuordnung  
 Anschließend generiert der Assistent die Spaltenbindungen oder Spaltenzuordnung. Um verschiedene Probleme mit einigen Anbietern zu beheben, bindet der folgende Code Spalten möglicherweise in einer anderen Reihenfolge als vom Anbieter gemeldet.  
  
```  
BEGIN_COLUMN_MAP(CProductsAccessor) COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus) COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus) COLUMN_ENTRY_LENGTH_STATUS(3, m_SupplierID, m_dwSupplierIDLength, m_dwSupplierIDStatus) COLUMN_ENTRY_LENGTH_STATUS(4, m_CategoryID, m_dwCategoryIDLength, m_dwCategoryIDStatus) COLUMN_ENTRY_LENGTH_STATUS(5, m_QuantityPerUnit, m_dwQuantityPerUnitLength, m_dwQuantityPerUnitStatus) _COLUMN_ENTRY_CODE(6, DBTYPE_CY, _SIZE_TYPE(m_UnitPrice), 0, 0, offsetbuf(m_UnitPrice), offsetbuf(m_dwUnitPriceLength), offsetbuf(m_dwUnitPriceStatus)) COLUMN_ENTRY_LENGTH_STATUS(7, m_UnitsInStock, m_dwUnitsInStockLength, m_dwUnitsInStockStatus) COLUMN_ENTRY_LENGTH_STATUS(8, m_UnitsOnOrder, m_dwUnitsOnOrderLength, m_dwUnitsOnOrderStatus) COLUMN_ENTRY_LENGTH_STATUS(9, m_ReorderLevel, m_dwReorderLevelLength, m_dwReorderLevelStatus) _COLUMN_ENTRY_CODE(10, DBTYPE_BOOL, _SIZE_TYPE(m_Discontinued), 0, 0, offsetbuf(m_Discontinued), offsetbuf(m_dwDiscontinuedLength), offsetbuf(m_dwDiscontinuedStatus)) END_COLUMN_MAP() };  
```  
  
### Klassendeklaration  
 Schließlich generiert der Assistent eine Klassendeklaration wie etwa die folgende:  
  
```  
class CProducts : public CCommand<CAccessor<CProductsAccessor> >  
```  
  
## Benutzerdatensatz\-Klasse mit Attributbeteiligung  
 Wenn Sie einen OLE DB\-Consumer mithilfe der Datenbankattribute \([db\_command](../../windows/db-command.md) oder [db\_table](../../windows/db-table.md)\) erstellen, injizieren die Attribute eine Benutzerdatensatz\-Klasse mit einem Namen der Form "\_*ClassName*Accessor." Wenn Sie Ihre Befehlsklasse beispielsweise `COrders` genannt haben, heißt die Benutzerdatensatz\-Klasse `_COrdersAccessor`. Zwar wird die Benutzerdatensatz\-Klasse in der Klassenansicht angezeigt, über einen Doppelklick darauf wird aber zu der in der Headerdatei festgelegten Befehls\- oder Tabellenklasse navigiert. In diesen Fällen können Sie die eigentliche Deklaration der Benutzerdatensatz\-Klasse nur durch Anzeigen des durch die Attribute injizierten Codes zu sehen bekommen.  
  
 Das Hinzufügen oder Überschreiben von Methoden in Consumern mit Attributbeteiligung führt möglicherweise zu Komplikationen. Beispielsweise können Sie der `COrders`\-Deklaration einen `_COrdersAccessor`\-Konstruktor hinzufügen, beachten Sie aber, dass dadurch tatsächlich der injizierten `COrdersAccessor`\-Klasse ein Konstruktor hinzugefügt wird. Ein derartiger Konstruktor kann die Spalten\/Parameter initialisieren, Sie können auf diese Weise aber keinen Kopierkonstruktor erstellen, da er das `COrdersAccessor`\-Objekt nicht direkt instanziieren kann. Wenn Sie einen Konstruktor \(oder eine andere Methode\) direkt für die `COrders`\-Klasse benötigen, wird empfohlen, eine neue, aus `COrders` abgeleitete Klasse zu definieren, der Sie die erforderlichen Methoden hinzufügen.  
  
 Im folgenden Beispiel generiert der Assistent eine Deklaration für die Klasse `COrders`, die Benutzerdatensatz\-Klasse `COrdersAccessor` taucht jedoch nicht auf, da die Attribute sie injizieren.  
  
```  
#define _ATL_ATTRIBUTES #include <atlbase.h> #include <atldbcli.h> [ db_source(L"your connection string"), db_command(L"Select ShipName from Orders;") ] class COrders { public: // COrders()            // incorrect constructor name _COrdersAccessor()      // correct constructor name { } [db_column(1) ] TCHAR m_ShipName[41]; };  
```  
  
 Die Deklaration der injizierten Befehlsklasse sieht wie folgt aus:  
  
```  
class CProducts : public CCommand<CAccessor<_CProductsAccessor> >  
```  
  
 Der größte Teil des injizierten Codes ist mit dem der vorlagenbasierten Version identisch oder ihm ähnlich. Die Hauptunterschiede liegen in den injizierten Methoden, die unter [Vom Consumer\-Assistenten generierte Methoden](../../data/oledb/consumer-wizard-generated-methods.md) beschrieben sind.  
  
 Informationen zum Anzeigen von injiziertem Code finden Sie unter [Debuggen von injiziertem Code](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)