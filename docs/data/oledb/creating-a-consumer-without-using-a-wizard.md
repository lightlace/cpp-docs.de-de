---
title: Erstellen eines Consumers ohne Assistent | Microsoft Docs
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
ms.openlocfilehash: c9f6bbc1ba45ec0b510dac015688fd29801c8449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097691"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Erstellen eines Consumers ohne Assistent
Im folgende Beispiel wird davon ausgegangen, dass Sie ein vorhandenes ATL-Projekt OLE DB-Consumer-Unterstützung hinzufügen. Wenn Sie OLE DB-Consumer-Unterstützung für eine MFC_Anwendung hinzufügen möchten, sollten Sie die MFC-Anwendung-Assistenten ausführen erstellt alle Unterstützung erforderlich sind, und ruft MFC-Routinen, die zum Ausführen der Anwendung.  
  
 OLE DB-Consumer-Unterstützung hinzufügen, ohne dass mit der ATL-OLE DB-Consumer-Assistent:  
  
-   Fügen Sie in der Datei "stdafx.h" die folgenden `#include` Anweisungen:  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 Ein Consumer werden programmgesteuert in der Regel die folgende Abfolge der Vorgänge ausgeführt:  
  
-   Erstellen Sie eine Benutzerdatensatz-Klasse, die Spalten an lokale Variablen zu binden. In diesem Beispiel `CMyTableNameAccessor` wird die Benutzerdatensatz-Klasse (siehe [Benutzerdatensätze](../../data/oledb/user-records.md)). Diese Klasse enthält die spaltenzuordnung und die Parameter zuordnen. Deklarieren Sie einen Datenmember in der Benutzerdatensatz-Klasse für jedes Feld, das Sie in der spaltenzuordnung angeben. für jede von diesen Datenmembern müssen Sie auch deklarieren Sie einen Datenmember für Status und Längendatenmember. Weitere Informationen finden Sie unter [Feldstatus-Datenmember in vom Assistenten generierten Accessoren](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    >  Wenn Sie einen eigenen Consumer schreiben, müssen die Datenvariablen vor den Status- und Längenvariablen liegen.  
  
-   Instanziieren Sie eine Datenquelle und eine Sitzung. Entscheiden, welche Art von Accessor und Rowset verwenden, und klicken Sie dann instanziiert ein Rowset mit [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md):  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>  
    ```  
  
-   Rufen Sie **CoInitialize** COM-Initialisierung Dies wird in der Regel in die Hauptcodedatei bezeichnet. Zum Beispiel:  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   Rufen Sie [CDataSource:: Open](../../data/oledb/cdatasource-open.md) oder eine seiner Variationen.  
  
-   Herstellen einer Verbindung mit der Datenquelle, öffnen Sie die Sitzung öffnen und initialisieren Sie das Rowset (und, wenn ein Befehl auch ausführen):  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   Optional Satz Rowseteigenschaften mit `CDBPropSet::AddProperty` und übergeben sie als Parameter an `rs.Open`. Ein Beispiel dafür, wie dies funktioniert, finden Sie unter GetRowsetProperties im [vom Methoden](../../data/oledb/consumer-wizard-generated-methods.md).  
  
-   Sie können jetzt mithilfe des Rowsets abrufen/Bearbeiten der Daten.  
  
-   Wenn die Anwendung ausgeführt wird, schließen Sie die Verbindung, Sitzung und Rowset:  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     Wenn Sie einen Befehl verwenden, möchten Sie möglicherweise Aufrufen `ReleaseCommand` nach **schließen**. Das Codebeispiel in [CCommand:: Close](../../data/oledb/ccommand-close.md) zeigt, wie **schließen** und `ReleaseCommand`.  
  
-   Rufen Sie **CoUnInitialize** Aufhebung der Initialisierung der COM. Dies wird in der Regel in die Hauptcodedatei bezeichnet.  
  
    ```  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Consumers](../../data/oledb/creating-an-ole-db-consumer.md)