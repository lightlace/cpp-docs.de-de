---
title: Erstellen eines Consumers ohne Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 843c2d79af8acaff835e8500f1f1d67870c4b63e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339905"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Erstellen eines Consumers ohne Assistent
Im folgende Beispiel wird davon ausgegangen, dass Sie ein vorhandenes Projekt mit ATL-OLE DB-Consumer-Unterstützung hinzufügen. Wenn Sie eine MFC-Anwendung OLE DB-Consumer-Unterstützung hinzufügen möchten, sollten Sie den MFS-Anwendungsassistenten ausführen erstellt alle Unterstützung erforderlich sind, und ruft die MFC-Routinen, die zum Ausführen der Anwendungs erforderlich sind.  
  
 OLE DB-Consumer-Unterstützung hinzufügen, ohne Verwendung der ATL-OLE DB-Consumer-Assistent:  
  
-   Fügen Sie in der Datei "stdafx.h" die folgenden `#include` Anweisungen:  
  
    ```cpp  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 Programmgesteuert, führt ein Consumer in der Regel die folgende Sequenz von Vorgängen:  
  
-   Erstellen Sie eine Benutzerdatensatz-Klasse, die Spalten an lokale Variablen zu binden. In diesem Beispiel `CMyTableNameAccessor` wird die Benutzerdatensatz-Klasse (siehe [Benutzerdatensätze](../../data/oledb/user-records.md)). Diese Klasse enthält die spaltenzuordnung und eine parameterzuordnung. Deklarieren Sie einen Datenmember in die Benutzerdatensatz-Klasse für jedes Feld, die Sie in der spaltenzuordnung angeben. für jede von diesen Datenmembern müssen Sie auch deklarieren Sie einen Datenmember für Status und ein Datenelement für die Länge. Weitere Informationen finden Sie unter [Feldstatus-Datenmember in vom Assistenten generierten Accessoren](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    >  Wenn Sie einen eigenen Consumer schreiben, müssen die Datenvariablen vor den Status- und Längenvariablen stammen.  
  
-   Instanziieren Sie eine Datenquelle und eine Sitzung an. Entscheiden, welcher Typ des Accessors und Rowset verwenden, und klicken Sie dann instanziiert ein Rowset mit [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md):  
  
    ```cpp  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>  
    ```  
  
-   Rufen Sie `CoInitialize` COM-Initialisierung Dies wird in der Regel in der Hauptcode bezeichnet. Zum Beispiel:  
  
    ```cpp  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   Rufen Sie [CDataSource:: Open](../../data/oledb/cdatasource-open.md) oder eine seine Varianten.  
  
-   Öffnen Sie eine Verbindung mit der Datenquelle, öffnen Sie die Sitzung, und öffnen Sie und initialisieren Sie das Rowset (und wenn ein Befehl auch führen Sie aus):  
  
    ```cpp  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   Optional, Set-Rowset-Eigenschaften mit `CDBPropSet::AddProperty` und übergeben sie als Parameter an `rs.Open`. Ein Beispiel dafür, wie dies funktioniert, finden Sie unter GetRowsetProperties im [vom Methoden](../../data/oledb/consumer-wizard-generated-methods.md).  
  
-   Sie können jetzt das Rowset verwenden, zum Abrufen/Bearbeiten der Daten.  
  
-   Wenn Ihre Anwendung abgeschlossen ist, schließen Sie die Verbindung, Sitzung und Rowset aus:  
  
    ```cpp  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     Wenn Sie einen Befehl verwenden, sollten Sie zum Aufrufen `ReleaseCommand` nach `Close`. Das Codebeispiel in [CCommand:: Close](../../data/oledb/ccommand-close.md) zeigt, wie `Close` und `ReleaseCommand`.  
  
-   Rufen Sie `CoUnInitialize` Aufhebung der Initialisierung der COM. Dies wird in der Regel in der Hauptcode bezeichnet.  
  
    ```  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Consumers](../../data/oledb/creating-an-ole-db-consumer.md)