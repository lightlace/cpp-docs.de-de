---
title: "Erstellen eines Consumers ohne Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Consumer, Erstellen"
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Erstellen eines Consumers ohne Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel wird davon ausgegangen, dass Sie einem bestehenden ATL\-Projekt OLE DB\-Consumerunterstützung hinzufügen.  Wenn Sie OLE DB\-Consumerunterstützung zu einer MFC\-Anwendung hinzufügen möchten, sollten Sie den MFC\-Anwendungs\-Assistenten ausführen. Er erstellt die benötigte Unterstützung und ruft die zur Ausführung der Anwendung notwendigen MFC\-Routinen auf.  
  
 So fügen Sie OLE DB\-Consumerunterstützung ohne Verwendung des ATL\-OLE DB\-Consumer\-Assistenten hinzu:  
  
-   Fügen Sie in der Datei stdafx.h die folgenden `#include`\-Anweisungen an:  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 Programmtechnisch führt ein Consumer in der Regel die folgende Operationsabfolge aus:  
  
-   Erstellen einer Benutzerdatensatz\-Klasse, die Spalten an lokale Variablen bindet.  In diesem Beispiel ist `CMyTableNameAccessor` die Benutzerdatensatzklasse \(siehe [Benutzerdatensätze](../../data/oledb/user-records.md)\).  Diese Klasse enthält die Spaltenzuordnung und die Parameterzuordnung.  Deklarieren Sie in der Benutzerdatensatz\-Klasse einen Datenmember für jedes in der Spaltenzuordnung festgelegte Feld. Deklarieren Sie außerdem für jeden dieser Datenmember einen Statusdatenmember und einen Längendatenmember.  Weitere Informationen finden Sie unter [Feldstatus\-Datenmember in vom Assistenten generierten Accessoren](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    >  Wenn Sie einen eigenen Consumer schreiben, müssen die Datenvariablen vor den Status\- und Längenvariablen stehen.  
  
-   Instanziieren einer Datenquelle und einer Sitzung.  Entscheiden Sie, welcher Accessor\- und Rowsettyp verwendet wird, und instanziieren Sie dann ein Rowset mit [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md):  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor> >  
    ```  
  
-   Aufrufen von **CoInitialize** zum Initialisieren von COM.  Dies erfolgt üblicherweise im Hauptcode.  Beispiel:  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   Aufrufen von [CDataSource::Open](../../data/oledb/cdatasource-open.md) oder einer Variation davon.  
  
-   Öffnen einer Verbindung zur Datenquelle, Öffnen der Sitzung und Öffnen und Initalisieren des Rowsets \(bei einem Befehl auch Ausführen dieses Befehls\):  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   Optional Festlegen von Rowseteigenschaften mit `CDBPropSet::AddProperty` und Übergeben dieser Eigenschaften als Parameter an `rs.Open`.  Ein Beispiel zur Vorgehensweise finden Sie unter GetRowsetProperties im Thema [Vom Consumer\-Assistenten generierte Methoden](../../data/oledb/consumer-wizard-generated-methods.md).  
  
-   Sie können nun das Rowset zum Abrufen\/Bearbeiten der Daten verwenden.  
  
-   Schließen Sie nach Fertigstellung der Anwendung die Verbindung, die Sitzung und das Rowset:  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     Wenn Sie einen Befehl verwenden, empfiehlt es sich, `ReleaseCommand` nach **Close** aufzurufen.  Im Codebeispiel unter [CCommand::Close](../../data/oledb/ccommand-close.md) wird gezeigt, wie **Close** und `ReleaseCommand` aufgerufen werden.  
  
-   Aufrufen von **CoUnInitialize**, um COM nicht zu initialisieren.  Dies erfolgt üblicherweise im Hauptcode.  
  
    ```  
    CoUninitialize();  
    ```  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Consumers](../../data/oledb/creating-an-ole-db-consumer.md)