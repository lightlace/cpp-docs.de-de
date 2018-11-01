---
title: Vom Consumer-Assistenten generierte Methoden
ms.date: 11/04/2016
helpviewer_keywords:
- OpenAll method
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- methods [C++], OLE DB Consumer Wizard-generated
- CloseDataSource method
- consumer wizard-generated classes and methods
- OpenDataSource method
- CloseAll method
- OpenRowset method
- GetRowsetProperties method
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
ms.openlocfilehash: 4c364d0caccfc422b91a68e15704628a949ef67b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635798"
---
# <a name="consumer-wizard-generated-methods"></a>Vom Consumer-Assistenten generierte Methoden

Die **ATL-OLE DB-Consumer-Assistenten** und **MFS-Anwendungsassistenten** bestimmte Funktionen, von denen sollten Sie bedenken, zu generieren. Einige Methoden sind unterschiedlich in attributierte Projekte implementiert, daher gibt es ein paar Einschränkungen; jeder Fall wird im folgenden erläutert. Informationen zum Anzeigen von injiziertem Code finden Sie unter [Debuggen von injiziertem Code](/visualstudio/debugger/how-to-debug-injected-code).

- `OpenAll` Öffnet die Datenquelle, Rowsets und Lesezeichen aktiviert, sofern sie verfügbar sind.

- `CloseAll` Schließt alle geöffneten Rowsets und alle befehlsausführungen frei.

- `OpenRowset` wird aufgerufen, indem `OpenAll` des Consumers oder mehrere Rowsets zu öffnen.

- `GetRowsetProperties` Ruft einen Zeiger des Rowsets Eigenschaftensatz, der mit dem Eigenschaften festgelegt werden können.

- `OpenDataSource` Öffnet die Datenquelle, die mit der Initialisierungszeichenfolge, die Sie, in angegeben der **Datenlinkeigenschaften** Dialogfeld.

- `CloseDataSource` Schließt die Datenquelle in geeigneter Weise an.

## <a name="openall-and-closeall"></a>OpenAll und CloseAll

```cpp
HRESULT OpenAll(); 

void CloseAll();
```

Das folgende Beispiel zeigt, wie Sie aufrufen können `OpenAll` und `CloseAll` Wenn Sie den gleichen Befehl wiederholt ausführen. Vergleichen Sie das Codebeispiel in [CCommand:: Close](../../data/oledb/ccommand-close.md), die eine Variante, die aufruft, zeigt `Close` und `ReleaseCommand` anstelle von `CloseAll`.

```cpp
int main(int argc, char* argv[])
{
   HRESULT hr;

   hr = CoInitialize(NULL);

   CCustOrdersDetail rs;      // Your CCommand-derived class
   rs.m_OrderID = 10248;      // Open order 10248
   hr = rs.OpenAll();         // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the first command execution
   rs.Close();

   rs.m_OrderID = 10249;      // Open order 10249 (a new order)
   hr = rs.Open();            // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the second command execution;
   // Instead of rs.CloseAll() you could call
   // rs.Close() and rs.ReleaseCommand():
   rs.CloseAll();

   CoUninitialize();
   return 0;
}
```

### <a name="remarks"></a>Hinweise

Wenn Sie definieren eine `HasBookmark` -Methode, die `OpenAll` code wird die `DBPROP_IRowsetLocate` Eigenschaft; stellen Sie sicher, dass Sie nur dazu, wenn Ihr Anbieter diese Eigenschaft unterstützt.

## <a name="openrowset"></a>OpenRowset

```cpp
// OLE DB Template version: 
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);
```

`OpenAll` Ruft diese Methode, um das Rowset oder Rowsets im Consumer zu öffnen. In der Regel müssen nicht aufrufen, `OpenRowset` , wenn Sie mit mehreren Data-Quellen/Sitzungen/Rowsets arbeiten möchten. `OpenRowset` wird in der Headerdatei der Befehl oder eine Tabelle deklariert:

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
{
   HRESULT hr = Open(m_session, NULL, pPropSet);
   #ifdef _DEBUG
   if(FAILED(hr))
      AtlTraceErrorRecords(hr);
   #endif
   return hr;
}
```

Diese Methode wird von die Attributen anders implementiert. Diese Version akzeptiert ein Sitzungsobjekt und eine Befehlszeichenfolge, die standardmäßig die Befehlszeichenfolge in Db_command, angegeben, obwohl Sie einen anderen Wert übergeben können. Wenn Sie definieren eine `HasBookmark` -Methode, die `OpenRowset` code wird die `DBPROP_IRowsetLocate` Eigenschaft; stellen Sie sicher, dass Sie nur dazu, wenn Ihr Anbieter diese Eigenschaft unterstützt.

```cpp
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)
{

   DBPROPSET *pPropSet = NULL;
   CDBPropSet propset(DBPROPSET_ROWSET);
   __if_exists(HasBookmark)

   {
      propset.AddProperty(DBPROP_IRowsetLocate, true);
      pPropSet= &propset;
      }
...
}
```

## <a name="getrowsetproperties"></a>GetRowsetProperties

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet);
```

Diese Methode ruft einen Zeiger auf die Rowset-Eigenschaftengruppe ab. Sie können diesen Zeiger verwenden, um Eigenschaften festzulegen, wie z. B. `DBPROP_IRowsetChange`. `GetRowsetProperties` wird wie folgt in die Benutzerdatensatz-Klasse verwendet. Sie können diesen Code zum Festlegen zusätzlicher Rowset-Eigenschaften ändern:

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="remarks"></a>Hinweise

Sie sollten nicht definieren, eine globale `GetRowsetProperties` Methode, da sie zusammen mit einem in Konflikt stehen kann, definiert durch den Assistenten. Dies ist eine vom Assistenten generierte-Methode, die im Lieferumfang von auf Vorlagen basierende und nicht attributierte Projekte enthalten. die Attribute einfügen nicht diesen Code.

## <a name="opendatasource-and-closedatasource"></a>OpenDataSource und CloseDataSource

```cpp
HRESULT OpenDataSource(); 

void CloseDataSource();
```

### <a name="remarks"></a>Hinweise

Der Assistent definiert die Methoden `OpenDataSource` und `CloseDataSource`; `OpenDataSource` Aufrufe [CDataSource:: OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)