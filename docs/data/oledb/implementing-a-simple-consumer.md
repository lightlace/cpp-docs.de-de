---
title: Implementieren eines einfachen Consumers
ms.date: 10/12/2018
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
ms.openlocfilehash: 9067e8645fac9a06bd85ca5ef18fbaff45d16aae
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033533"
---
# <a name="implementing-a-simple-consumer"></a>Implementieren eines einfachen Consumers

In den folgenden Themen zeigen, wie so bearbeiten Sie die erstellten Dateien die **MFS-Anwendungsassistenten** und **ATL-OLE DB-Consumer-Assistenten** zum Erstellen eines einfachen Consumers. In diesem Beispiel besteht aus folgenden Teilen:

- [Abrufen von Daten mit dem Consumer](#retrieve) wird gezeigt, wie Code im Consumer zu implementieren, die alle Daten zeilenweise aus einer Datenbanktabelle liest.

- [Hinzufügen von Lesezeichen unterstützen, an den Consumer](#bookmark) veranschaulicht das Hinzufügen von lesezeichenunterstützung für den Consumer.

> [!NOTE]
> Sie können in diesem Abschnitt beschriebenen Consumer-Anwendung zum Testen verwenden die `MyProv` und `Provider` Beispiel-Anbieter.

> [!NOTE]
> Erstellen Sie eine Consumeranwendung zum Testen `MyProv` (die gleiche Anbieter, die in beschriebenen [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)), müssen Sie lesezeichenunterstützung einschließen, wie in beschrieben [Hinzufügen von Lesezeichen unterstützen, die Consumer](#bookmark).

## <a name="retrieve" ></a> Abrufen von Daten mit dem Consumer

### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>So ändern Sie die Konsolenanwendung verwendet die OLE DB-consumer

1. In `MyCons.cpp`, ändern Sie den Hauptcode, indem Sie den fett formatierten Text wie folgt einfügen:

    ```cpp
    // MyCons.cpp : Defines the entry point for the console application.
    //
    #include "stdafx.h"
    #include "Products.h"
    ...
    int main(int argc, char* argv[])
    {
       HRESULT hr = CoInitialize(NULL);   // Instantiate rowset
       CProducts rs;
       hr = rs.OpenAll();
       ATLASSERT(SUCCEEDED(hr ) );
       hr = rs.MoveFirst();   // Iterate through the rowset
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row
         printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",
           rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );
         hr = rs.MoveNext();   }
       rs.Close();
       rs.ReleaseCommand();
       CoUninitialize();

       return 0;
    }
    ```

## <a name="bookmark" ></a> Hinzufügen von Lesezeichenunterstützung für den Consumer

Ein Lesezeichen ist eine Spalte, die Zeilen in der Tabelle eindeutig identifiziert. Normalerweise ist die Schlüsselspalte, aber nicht immer; Es ist anbieterspezifisch. In diesem Abschnitt erfahren Sie, wie Sie lesezeichenunterstützung hinzufügen. Zu diesem Zweck müssen Sie in die Benutzerdatensatz-Klasse die folgenden Schritte ausführen:

- Instanziieren Sie die Lesezeichen. Hierbei handelt es sich um Objekte des Typs [CBookmark](../../data/oledb/cbookmark-class.md).

- Eine Lesezeichenspalte vom Anbieter anfordern, indem die `DBPROP_IRowsetLocate` Eigenschaft.

- Einen Lesezeicheneintrag mithilfe der spaltenzuordnung Hinzufügen der [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) Makro.

Die vorherigen Schritten erhalten Sie lesezeichenunterstützung und ein Bookmark-Objekt, mit denen Sie arbeiten. Dieses Codebeispiel veranschaulicht ein Lesezeichen wie folgt aus:

- Öffnen Sie eine Datei zum Schreiben.

- Ausgabe von Rowsetdaten in die Datei Zeile für Zeile.

- Verschieben den Rowset-Cursor auf das Lesezeichen durch Aufrufen von [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).

- Geben Sie den mit Lesezeichen versehenen Zeile, die an das Ende der Datei angefügt.

> [!NOTE]
> Wenn Sie diese Consumeranwendung zum Testen verwenden die `Provider` anbieteranwendung zugreifen können, lassen Sie die lesezeichenunterstützung, die in diesem Abschnitt beschrieben.

### <a name="to-instantiate-the-bookmark"></a>Um das Lesezeichen zu instanziieren.

1. Der Accessor muss ein Objekt des Typs enthalten [CBookmark](../../data/oledb/cbookmark-class.md). Die *nSize* Parameter gibt die Größe des Lesezeichenpuffers in Bytes (in der Regel 4 für 32-Bit-Plattformen) und 8 für 64-Bit-Plattformen. Fügen Sie die folgende Deklaration, um der Spaltenelemente für die Daten in die Benutzerdatensatz-Klasse:

    ```cpp
    //////////////////////////////////////////////////////////////////////
    // Products.h
    class CProductsAccessor
    {
    public:
       CBookmark<4> m_bookmark;   // Add bookmark declaration
       LONG m_ProductID;
       ...
    ```

### <a name="to-request-a-bookmark-column-from-the-provider"></a>Eine Lesezeichenspalte vom Anbieter anfordern

1. Fügen Sie den folgenden Code in die `GetRowsetProperties` -Methode in der die Benutzerdatensatz-Klasse:

    ```cpp
    // Set the DBPROP_IRowsetLocate property.
    void GetRowsetProperties(CDBPropSet* pPropSet)
    {
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);
    }
    ```

### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Einen Lesezeicheneintrag zu der spaltenzuordnung hinzufügen

1. Fügen Sie den folgenden Eintrag, um die spaltenzuordnung in der Benutzerdatensatz-Klasse:

    ```cpp
    // Set a bookmark entry in the column map.
    BEGIN_COLUMN_MAP(CProductsAccessor)
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
    ...
    END_COLUMN_MAP()
    ```

### <a name="to-use-a-bookmark-in-your-main-code"></a>Verwenden Sie ein Lesezeichen in Ihrem Code main

1. In der `MyCons.cpp` Datei der Konsolenanwendung, die Sie zuvor erstellt haben, den Hauptcode ändern, sodass er folgendermaßen. Um Lesezeichen zu verwenden, muss der Hauptcode eigene Bookmark-Objekt zu instanziieren (`myBookmark`); Dies ist ein anderes Lesezeichen in die Zugriffsmethode (`m_bookmark`).

    ```cpp
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
             myBookmark = rs.m_bookmark;
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

Weitere Informationen über Lesezeichen finden Sie unter [mithilfe von Lesezeichen](../../data/oledb/using-bookmarks.md). Beispiele zu Lesezeichen Siehe [Aktualisieren von Rowsets](../../data/oledb/updating-rowsets.md).

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Consumers mit einem Assistenten](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
