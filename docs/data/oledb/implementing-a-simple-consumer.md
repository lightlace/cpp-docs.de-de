---
title: "Implementieren eines einfachen Consumers"
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
  - "Clients, Erstellen"
  - "OLE DB-Consumer, Implementieren"
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Implementieren eines einfachen Consumers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In den folgenden Themen wird veranschaulicht, wie Sie die mit dem MFC\-Anwendungs\-Assistenten und dem ATL\-OLE DB\-Consumer\-Assistenten erstellten Dateien bearbeiten, um einen einfachen Consumer zu erstellen.  Dieses Beispiel setzt sich aus folgenden Teilen zusammen:  
  
-   "Abrufen von Daten mit dem Consumer" zeigt, wie Sie im Consumer Code implementieren können, der alle Daten aus einer Datenbanktabelle Zeile für Zeile liest.  
  
-   "Hinzufügen von Lesezeichenunterstützung zum Consumer" veranschaulicht, wie Sie dem Consumer Unterstützung für Lesezeichen hinzufügen können.  
  
-   "Hinzufügen von XML\-Unterstützung zum Consumer" zeigt auf, wie Sie den Consumercode so ändern können, dass die abgerufenen Rowsetdaten als XML\-Daten ausgegeben werden.  
  
> [!NOTE]
>  Sie können mithilfe der in diesem Abschnitt beschriebenen Consumeranwendung die Beispielanbieter MyProv und Anbieter testen.  
  
> [!NOTE]
>  Zum Erstellen einer Consumeranwendung zum Testen von **MyProv** \(demselben Anbieter, der unter [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md) beschrieben wird\), müssen Sie Unterstützung für Lesezeichen hinzufügen, wie unter "Hinzufügen von Lesezeichenunterstützung zum Consumer" beschrieben.  
  
> [!NOTE]
>  Wenn Sie eine Consumeranwendung zum Testen von **Anbieter** erstellen möchten, überspringen Sie die unter "Hinzufügen von Lesezeichenunterstützung zum Consumer" beschriebene Lesenzeichenunterstützung und fahren mit "Hinzufügen von XML\-Unterstützung zum Consumer" fort.  
  
## Abrufen von Daten mit dem Consumer  
  
#### So ändern Sie die Konsolenanwendung für die Verwendung des OLE DB\-Consumers  
  
1.  Ändern Sie in **MyCons.cpp** den Hauptcode durch Einfügen des im Folgenden fett formatierten Textes:  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);        // Instantiate rowset    CProducts rs;        hr = rs.OpenAll();    ATLASSERT( SUCCEEDED( hr ) );    hr = rs.MoveFirst();        // Iterate through the rowset    while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )    {       // Print out the column information for each row       printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",              rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );       hr = rs.MoveNext();    }        rs.Close();    rs.ReleaseCommand();        CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## Hinzufügen von Lesezeichenunterstützung zum Consumer  
 Bei einem Lesezeichen handelt es sich um eine Spalte, die Zeilen in der Tabelle eindeutig identifiziert.  In der Regel ist dies die Schlüsselspalte, allerdings nicht in jedem Fall, denn Lesezeichen sind anbieterspezifisch.  In diesem Abschnitt wird aufgezeigt, wie Sie Unterstützung für Lesezeichen hinzufügen.  Zu diesem Zweck gehen Sie in der Benutzerdatensatz\-Klasse folgendermaßen vor:  
  
-   Instanziieren Sie die Lesezeichen.  Diese sind Objekte des Typs [CBookmark](../../data/oledb/cbookmark-class.md).  
  
-   Fordern Sie eine Lesezeichenspalte vom Anbieter an, indem Sie die **DBPROP\_IRowsetLocate**\-Eigenschaft festlegen.  
  
-   Fügen Sie mithilfe des [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md)\-Makros der Spaltenzuordnung einen Lesezeicheneintrag hinzu.  
  
 Durch die oben genannten Schritte fügen Sie Lesezeichenunterstützung hinzu und erhalten ein Lesezeichenobjekt, mit dem Sie arbeiten können.  In diesem Codebeispiel wird ein Lesezeichen durch die Ausführung der folgenden Schritte veranschaulicht:  
  
-   Öffnen einer Datei zum Schreiben.  
  
-   Ausgabe von Rowsetdaten Zeile für Zeile in die Datei.  
  
-   Verschieben des Rowsetcursors zum Lesezeichen durch Aufrufen von [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).  
  
-   Ausgabe der mit dem Lesezeichen versehenen Zeile und Anhängen dieser Zeile am Ende der Datei.  
  
> [!NOTE]
>  Wenn Sie diese Consumeranwendung zum Testen der Beispielanbieteranwendung Anbieter verwenden, überspringen Sie die in diesem Abschnitt beschriebene Lesezeichenunterstützung.  
  
#### So instanziieren Sie das Lesezeichen  
  
1.  Der Accessor muss ein Objekt des Typs [CBookmark](../../data/oledb/cbookmark-class.md) enthalten.  Der `nSize`\-Parameter gibt die Größe des Lesezeichenpuffers in Bytes an \(in der Regel 4 bei 32\-Bit\-Plattformen und 8 bei 64\-Bit\-Plattformen\).  Fügen Sie den Spaltendatenmembern in der Benutzerdatensatz\-Klasse die folgende Deklaration hinzu:  
  
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
  
#### So fordern Sie eine Lesezeichenspalte vom Anbieter an  
  
1.  Fügen Sie den folgenden Code in der `GetRowsetProperties`\-Methode in der Benutzerdatensatz\-Klasse hinzu:  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks    pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### So fügen Sie der Spaltenzuordnung einen Lesezeicheneintrag hinzu  
  
1.  Fügen Sie der Spaltenzuordnung in der Benutzerdatensatz\-Klasse den folgenden Eintrag hinzu:  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### So verwenden Sie ein Lesezeichen im Hauptcode  
  
1.  Ändern Sie in der Datei **MyCons.cpp** der zuvor erstellten Konsolenanwendung den Hauptcode, wie nachfolgend dargestellt.  Damit Lesezeichen verwendet werden können, muss der Hauptcode sein eigenes Lesezeichenobjekt \(`myBookmark`\) instanziieren. Beachten Sie, dass es sich dabei um ein anderes Lesezeichen handelt als das im Accessor \(`m_bookmark`\).  
  
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
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if( nCounter == 5 )  
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
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
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
  
 Weitere Informationen zu Lesezeichen finden Sie unter [Verwenden von Lesezeichen](../../data/oledb/using-bookmarks.md).  Beispiele zu Lesezeichen befinden sich ebenfalls unter [Aktualisieren von Rowsets](../../data/oledb/updating-rowsets.md).  
  
## Hinzufügen von XML\-Unterstützung zum Consumer  
 Wie unter [Zugreifen auf XML\-Daten](../../data/oledb/accessing-xml-data.md) besprochen, können XML\-Daten auf zwei Arten von einer Datenquelle abgerufen werden: mit [CStreamRowset](../../data/oledb/cstreamrowset-class.md) oder mit [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  In diesem Beispiel wird die effizientere `CStreamRowset`\-Lösung verwendet. Hierzu muss jedoch auf dem Computer, auf dem diese Beispielanwendung ausgeführt wird, SQL Server 2000 ausgeführt werden.  
  
#### So ändern Sie die Befehlsklasse, sodass sie von "CStreamRowset" erbt  
  
1.  Ändern Sie in der zuvor erstellten Consumeranwendung die `CCommand`\-Deklaration dahingehend, dass `CStreamRowset` als Rowset\-Klasse festgelegt wird. Geben Sie Folgendes ein:  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### So ändern Sie den Hauptcode zum Abrufen und Ausgeben der XML\-Daten  
  
1.  Ändern Sie in der Datei **MyCons.cpp** der zuvor erstellten Konsolenanwendung den Hauptcode, wie nachfolgend dargestellt:  
  
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
  
## Siehe auch  
 [Erstellen eines OLE DB\-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)