---
title: "Vom Consumer-Assistenten generierte Methoden"
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
  - "CloseAll-Methode"
  - "CloseDataSource-Methode"
  - "Vom Consumer-Assistenten generierte Klassen und Methoden"
  - "GetRowsetProperties-Methode"
  - "Methoden [C++], OLE DB (vom Consumer-Assistenten generiert)"
  - "OLE DB-Consumer, Vom Assistenten generierte Klassen und Methoden"
  - "OpenAll-Methode"
  - "OpenDataSource-Methode"
  - "OpenRowset-Methode"
  - "Vom Assistenten generierte Klassen und Methoden"
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Vom Consumer-Assistenten generierte Methoden
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der ATL\-OLE DB\-Consumer\-Assistent und der MFC\-Anwendungs\-Assistent generieren bestimmte Funktionen, die Sie kennen sollten.  Manche Methoden werden in attributierten Projekten unterschiedlich implementiert, sodass einige Punkte beachtet werden müssen. Jeder dieser Fälle wird nachfolgend erläutert.  Informationen zum Anzeigen von eingefügtem Code finden Sie unter [Debuggen von eingefügtem Code](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
-   `OpenAll` öffnet die Datenquelle und Rowsets und aktiviert Lesezeichen, falls diese verfügbar sind.  
  
-   `CloseAll` schließt alle geöffneten Rowsets und gibt alle Befehlausführungen frei.  
  
-   `OpenRowset` wird von OpenAll aufgerufen, um das bzw. die Rowset\(s\) des Consumers zu öffnen.  
  
-   `GetRowsetProperties` ruft einen Zeiger auf das Eigenschaftenset des Rowsets ab, mit dem Eigenschaften festgelegt werden können.  
  
-   `OpenDataSource` öffnet die Datenquelle unter Verwendung der im Dialogfeld **Datenverknüpfungseigenschaften** festgelegten Initialisierungszeichenfolge.  
  
-   `CloseDataSource` schließt die Datenquelle auf geeignete Art und Weise.  
  
## "OpenAll" und "CloseAll"  
  
```  
HRESULT OpenAll();   
void CloseAll();  
```  
  
 Im folgenden Beispiel wird gezeigt, wie Sie `OpenAll` und `CloseAll`  aufrufen können, wenn Sie denselben Befehl mehrfach ausführen.  Vergleichen Sie dieses Beispiel mit dem Codebeispiel unter [CCommand::Close](../../data/oledb/ccommand-close.md), das eine Variation darstellt, die **Close** und `ReleaseCommand` statt `CloseAll` aufruft.  
  
```  
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
  
## Hinweise  
 Wenn Sie eine `HasBookmark`\-Methode definieren, wird mit dem `OpenAll` \-Code die DBPROP\_IRowsetLocate\-Eigenschaft festgelegt. Achten Sie daher darauf, diese Vorgehensweise nur zu wählen, wenn Ihr Anbieter diese Eigenschaft unterstützt.  
  
## "OpenRowset"  
  
```  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 **OpenAll** ruft diese Methode zum Öffnen des bzw. der Rowset\(s\) im Consumer auf.  Üblicherweise ist das Aufrufen von `OpenRowset` nur erforderlich, wenn Sie mit mehreren Datenquellen\/Sitzungen\/Rowsets arbeiten möchten.  `OpenRowset` wird in der Headerdatei der Befehls\- bzw. Tabellenklasse deklariert:  
  
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
  
 Mit den Attributen wird diese Methode anders implementiert.  In dieser Version sind ein Sitzungsobjekt und eine Befehlszeichenfolge erforderlich, bei der es sich standardmäßig um die in **db\_command** festgelegte Befehlszeichenfolge handelt. Sie können aber auch eine andere Zeichenfolge übergeben.  Wenn Sie eine `HasBookmark`\-Methode definieren, wird mit dem `OpenRowset` \-Code die DBPROP\_IRowsetLocate\-Eigenschaft festgelegt. Achten Sie daher darauf, diese Vorgehensweise nur zu wählen, wenn Ihr Anbieter diese Eigenschaft unterstützt.  
  
```  
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
  
## "GetRowsetProperties"  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 Diese Methode ruft einen Zeiger auf das Eigenschaftenset des Rowsets ab. Diesen Zeiger können Sie verwenden, um Eigenschaften wie DBPROP\_IRowsetChange festzulegen.  `GetRowsetProperties` wird in der Benutzerdatensatz\-Klasse verwendet, wie im Folgenden aufgezeigt.  Sie können diesen Code ändern, um zusätzliche Rowseteigenschaften festzulegen:  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## Hinweise  
 Sie sollten keine globale `GetRowsetProperties`\-Methode definieren, da diese einen Konflikt mit der vom Assistenten definierten Methode verursachen könnte.  Beachten Sie, dass es sich hierbei um eine vom Assistenten generierte Methode handelt, die Sie bei aus einer Vorlage gebildeten und attributierten Projekten erhalten. Die Attribute fügen diesen Code nicht ein.  
  
## "OpenDataSource" und "CloseDataSource"  
  
```  
HRESULT OpenDataSource();   
void CloseDataSource();  
```  
  
## Hinweise  
 Der Assistent definiert die Methoden `OpenDataSource` und `CloseDataSource`; `OpenDataSource` ruft [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) auf.  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)