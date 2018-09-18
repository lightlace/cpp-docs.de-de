---
title: Vom Consumer-Assistenten generierte Methoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a3f80d3e421701ac0612ddb2552d10d1eff1f02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056026"
---
# <a name="consumer-wizard-generated-methods"></a>Vom Consumer-Assistenten generierte Methoden

Der ATL-OLE DB-Consumer-Assistent und der MFC-Anwendungs-Assistent generiert für bestimmte Funktionen, die Sie berücksichtigen sollten. Beachten Sie, dass einige Methoden in attributierte Projekte unterschiedlich implementiert werden, daher gibt es einige Einschränkungen. jeder Fall wird im folgenden erläutert. Informationen zum Anzeigen von injiziertem Code finden Sie unter [Debuggen von injiziertem Code](/visualstudio/debugger/how-to-debug-injected-code).  
  
- `OpenAll` Öffnet die Datenquelle, Rowsets und Lesezeichen aktiviert, sofern diese verfügbar sind.  
  
- `CloseAll` Schließt alle geöffneten Rowsets und alle befehlsausführungen frei.  
  
- `OpenRowset` wird von OpenAll zum Öffnen des Consumers oder mehrere Rowsets aufgerufen.  
  
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
  
## <a name="remarks"></a>Hinweise  

Beachten Sie, dass, wenn Sie definieren eine `HasBookmark` -Methode, die `OpenAll` Code wird die DBPROP_IRowsetLocate-Eigenschaft; stellen Sie sicher, dass Sie nur dazu, wenn Ihr Anbieter diese Eigenschaft unterstützt.  
  
## <a name="openrowset"></a>OpenRowset  
  
```cpp  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
`OpenAll` Ruft diese Methode, um das Rowset oder Rowsets im Consumer zu öffnen. Sie müssen normalerweise nicht aufrufen, `OpenRowset` , wenn Sie mit mehreren Data-Quellen/Sitzungen/Rowsets arbeiten möchten. `OpenRowset` wird in der Headerdatei der Befehl oder eine Tabelle deklariert:  
  
```  
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
  
Diese Methode wird von die Attributen anders implementiert. Diese Version akzeptiert ein Sitzungsobjekt und eine Befehlszeichenfolge, die standardmäßig die Befehlszeichenfolge in Db_command, angegeben, obwohl Sie einen anderen Wert übergeben können. Beachten Sie, dass, wenn Sie definieren eine `HasBookmark` -Methode, die `OpenRowset` Code wird die DBPROP_IRowsetLocate-Eigenschaft; stellen Sie sicher, dass Sie nur dazu, wenn Ihr Anbieter diese Eigenschaft unterstützt.  
  
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
  
Diese Methode ruft einen Zeiger auf die Rowset-Eigenschaftengruppe ab. this-Zeiger können Eigenschaften wie DBPROP_IRowsetChange fest. `GetRowsetProperties` wird wie folgt in die Benutzerdatensatz-Klasse verwendet. Sie können diesen Code zum Festlegen zusätzlicher Rowset-Eigenschaften ändern:  
  
```cpp  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## <a name="remarks"></a>Hinweise  

Definieren Sie kein globales `GetRowsetProperties` Methode, da sie zusammen mit einem in Konflikt stehen kann, definiert durch den Assistenten. Beachten Sie, dass es sich um eine vom Assistenten generierte Methode handelt, die Sie mit Vorlagen und attributierte-Projekten zu erhalten. Führen Sie injizieren die Attribute dieser Code nicht.  
  
## <a name="opendatasource-and-closedatasource"></a>OpenDataSource und CloseDataSource  
  
```cpp  
HRESULT OpenDataSource();   

void CloseDataSource();  
```  
  
## <a name="remarks"></a>Hinweise  

Der Assistent definiert die Methoden `OpenDataSource` und `CloseDataSource`; `OpenDataSource` Aufrufe [CDataSource:: OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).  
  
## <a name="see-also"></a>Siehe auch  

[Erstellen eines OLE DB-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)