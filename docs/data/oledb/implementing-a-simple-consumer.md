---
title: Implementieren eines einfachen Consumers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ab109411117b99f816b094fca06ff08a4e7e3cb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="implementing-a-simple-consumer"></a>Implementieren eines einfachen Consumers
In den folgenden Themen zeigen, wie die Dateien erstellt, indem die MFC-Anwendung-Assistent und die ATL-OLE DB-Consumer-Assistenten zum Erstellen eines einfachen Consumers zu bearbeiten. In diesem Beispiel besteht aus folgenden Teilen:  
  
-   "Abrufen von Daten mit dem Consumer" zeigt, wie Code in der Consumer zu implementieren, die alle Daten zeilenweise aus einer Datenbanktabelle liest.  
  
-   "Hinzufügen von an den Consumer Lesezeichen unterstützen" zeigt, wie lesezeichenunterstützung an den Consumer hinzuzufügen.  
  
-   "Hinzufügen von XML-Unterstützung an den Consumer" zeigt, wie zum Ändern des Consumercodes, um die abgerufenen Rowsetdaten als XML-Daten ausgegeben.  
  
> [!NOTE]
>  Der Consumer-Anwendung, die in diesem Abschnitt beschriebenen können Sie um die Beispiel-Anbieter MyProv und Anbieter zu testen.  
  
> [!NOTE]
>  Erstellen Sie eine Consumeranwendung MyProv testen (die gleiche Anbieter, die in beschriebenen [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)), müssen Sie lesezeichenunterstützung einschließen, wie unter "Hinzufügen von Lesezeichenunterstützung an den Consumer."  
  
> [!NOTE]
>  Erstellen Sie eine Consumeranwendung zum Anbieter zu testen, lassen Sie die lesezeichenunterstützung in "Hinzufügen von Lesezeichen unterstützt, Consumer" beschrieben, und fahren Sie mit "Hinzufügen von XML-Unterstützung an den Consumer."  
  
## <a name="retrieving-data-with-the-consumer"></a>Abrufen von Daten mit dem Consumer  
  
#### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>So ändern Sie die Konsolenanwendung mithilfe der OLE DB-consumer  
  
1.  Ändern Sie die Hauptcodedatei in MyCons.cpp durch den fett formatierten Text wie folgt einfügen:  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);   // Instantiate rowset   CProducts rs;   hr = rs.OpenAll();   ATLASSERT(SUCCEEDED(hr ) );   hr = rs.MoveFirst();   // Iterate through the rowset   while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row      printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",             rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );      hr = rs.MoveNext();   }   rs.Close();   rs.ReleaseCommand();   CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="adding-bookmark-support-to-the-consumer"></a>Hinzufügen von Lesezeichenunterstützung an den Consumer  
 Ein Lesezeichen ist eine Spalte, die Zeilen in der Tabelle eindeutig identifiziert. Normalerweise ist die Schlüsselspalte jedoch nicht immer; Es ist anbieterspezifisch. In diesem Abschnitt wird gezeigt, wie die lesezeichenunterstützung hinzuzufügen. Zu diesem Zweck müssen Sie in der Benutzerdatensatz-Klasse die folgende Aktionen ausführen:  
  
-   Instanziieren Sie das Lesezeichen. Hierbei handelt es sich um Objekte des Typs [CBookmark](../../data/oledb/cbookmark-class.md).  
  
-   Fordern Sie eine Lesezeichenspalte vom Anbieter durch Festlegen der **DBPROP_IRowsetLocate** Eigenschaft.  
  
-   Die spaltenzuordnung mithilfe einen Lesezeicheneintrag hinzufügen die [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) Makro.  
  
 Die vorherigen Schritte bieten Ihnen lesezeichenunterstützung und ein Bookmark-Objekt, mit denen Sie arbeiten. Dieses Codebeispiel zeigt ein Lesezeichen wie folgt aus:  
  
-   Öffnen Sie eine Datei zum Schreiben.  
  
-   Rowset-Ausgabedaten auf die Datei zeilenweise.  
  
-   Das Lesezeichen durch Aufrufen den Rowset-Cursor ans [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).  
  
-   Die Ausgabe der Lesezeichen versehenen Zeile am Ende der Datei angefügt.  
  
> [!NOTE]
>  Wenn Sie diese Consumeranwendung So testen Sie die Anbieter-beispielanwendung Anbieter verwenden, lassen Sie die lesezeichenunterstützung, die in diesem Abschnitt beschrieben.  
  
#### <a name="to-instantiate-the-bookmark"></a>Um das Lesezeichen zu instanziieren.  
  
1.  Der Accessor muss ein Objekt des Typs enthalten [CBookmark](../../data/oledb/cbookmark-class.md). Die `nSize` Parameter gibt die Größe des Lesezeichenpuffers in Bytes (in der Regel 4 für 32-Bit-Plattformen) und 8 für 64-Bit-Plattformen. Fügen Sie die folgende Deklaration auf der Spaltenelemente für die Daten in die Benutzerdatensatz-Klasse hinzu:  
  
    ```  
    //////////////////////////////////////////////////////////////////////  
    // Products.h  
    class CProductsAccessor  
    {  
    public:  
       CBookmark<4> m_bookmark;   // Add bookmark declaration  
       LONG m_ProductID;  
       ...  
    ```  
  
#### <a name="to-request-a-bookmark-column-from-the-provider"></a>So fordern Sie eine Lesezeichenspalte vom Anbieter an  
  
1.  Fügen Sie den folgenden Code in die `GetRowsetProperties` Methode in die Benutzerdatensatz-Klasse:  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Hinzufügen einen Lesezeicheneintrag zu der spaltenzuordnung  
  
1.  Fügen Sie den folgenden Eintrag, um die spaltenzuordnung in der Benutzerdatensatz-Klasse:  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### <a name="to-use-a-bookmark-in-your-main-code"></a>So verwenden Sie ein Lesezeichen in Ihrer Hauptcodedatei  
  
1.  Ändern Sie die Hauptcodedatei wie folgt, in der Datei MyCons.cpp von der Konsolenanwendung, die Sie zuvor erstellt haben. Um Lesezeichen zu verwenden, muss die Hauptcodedatei eigene Bookmark-Objekt zu instanziieren (`myBookmark`); Dies ist ein anderes Lesezeichen in den Accessor (`m_bookmark`).  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       hr = rs.OpenAll();  
       hr = rs.MoveFirst();  
  
       // Cast CURRENCY m_UnitPrice to a long value  
       LONGLONG lPrice = rs.m_UnitPrice.int64;  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // Instantiate a bookmark object myBookmark for the main code  
       CBookmark<4> myBookmark;  
       int nCounter = 0;  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "initial row dump" << endl;  
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if(nCounter == 5 )  
             myBookmark = rs.bookmark;  
          // Output the column information for each row:  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       // Move cursor to bookmark  
       hr = rs.MoveToBookmark(myBookmark);  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "row dump starting from bookmarked row" << endl;  
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          // Output the column information for each row  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
 Weitere Informationen zu Lesezeichen, finden Sie unter [mithilfe von Lesezeichen](../../data/oledb/using-bookmarks.md). Außerdem werden Beispiele für die Lesezeichen angezeigt [Aktualisieren von Rowsets](../../data/oledb/updating-rowsets.md).  
  
## <a name="adding-xml-support-to-the-consumer"></a>Hinzufügen von XML-Unterstützung an den Consumer  
 Entsprechend der Anleitung unter [zugreifen auf XML-Daten](../../data/oledb/accessing-xml-data.md), es gibt zwei Möglichkeiten zum Abrufen von XML-Daten aus einer Datenquelle: mit [CStreamRowset](../../data/oledb/cstreamrowset-class.md) oder [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md). Dieses Beispiel verwendet `CStreamRowset`, wodurch ist jedoch effizienter, jedoch benötigen Sie SQL Server 2000 ausgeführt wird, auf dem Computer, auf dem Sie diese beispielanwendung ausführen, kann.  
  
#### <a name="to-modify-the-command-class-to-inherit-from-cstreamrowset"></a>So ändern Sie die Befehlsklasse von CStreamRowset erben  
  
1.  In der Consumeranwendung, die Sie zuvor erstellt haben, ändern Sie Ihre `CCommand` Deklaration an `CStreamRowset` als Rowset-Klasse wie folgt:  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### <a name="to-modify-the-main-code-to-retrieve-and-output-the-xml-data"></a>So ändern Sie die Hauptcodedatei zum Abrufen und die Ausgabe der XML-Daten  
  
1.  In der MyCons.cpp-Datei von der Konsolenanwendung, die Sie zuvor erstellt haben, ändern Sie die Hauptcodedatei wie folgt:  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       // Add variable declarations for the Read method to handle sequential stream data  
       CHAR buffer[1001];  // Pointer to buffer into which data stream is read  
       ULONG cbRead;       // Actual number of bytes read from the data stream  
  
       hr = rs.OpenAll();  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // The following loop reads 1000 bytes of the data stream at a time   
       // until it reaches the end of the data stream  
       for (;;)  
       {  
          // Read sequential stream data into buffer  
    HRESULT hr = rs.m_spStream->Read(buffer, 1000, &cbRead);  
          if (FAILED (hr))  
             break;  
          // Output buffer to file  
          buffer[cbRead] = 0;  
          outfile << buffer;  
          // Test for end of data stream  
          if (cbRead < 1000)  
             break;  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)