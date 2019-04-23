---
title: Erstellen eines Consumers ohne Assistent
ms.date: 10/12/2018
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
ms.openlocfilehash: 029fe6866df81d366cc3bc15096f638791faa413
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030419"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Erstellen eines Consumers ohne Assistent

Im folgende Beispiel wird davon ausgegangen, dass Sie ein vorhandenes Projekt mit ATL-OLE DB-Consumer-Unterstützung hinzufügen. Wenn Sie eine MFC-Anwendung OLE DB-Consumer-Unterstützung hinzufügen möchten, sollten Sie Ausführen den **MFS-Anwendungsassistenten**, die erstellt alle Unterstützung erforderlich sind, und ruft von MFC-Routinen, die zum Ausführen der Anwendungs erforderlich sind.

Hinzufügen von OLE DB-Consumer-Unterstützung ohne Verwendung der **ATL-OLE DB-Consumer-Assistenten**:

- Fügen Sie in der Datei "PCH.h" Folgendes `#include` Anweisungen:

    ```cpp
    #include <atlbase.h>
    #include <atldbcli.h>
    #include <atldbsch.h> // if you are using schema templates
    ```

Programmgesteuert, führt ein Consumer in der Regel die folgende Sequenz von Vorgängen:

1. Erstellen Sie eine Benutzerdatensatz-Klasse, die Spalten an lokale Variablen zu binden. In diesem Beispiel `CMyTableNameAccessor` wird die Benutzerdatensatz-Klasse (siehe [Benutzerdatensätze](../../data/oledb/user-records.md)). Diese Klasse enthält die spaltenzuordnung und eine parameterzuordnung. Deklarieren Sie einen Datenmember in die Benutzerdatensatz-Klasse für jedes Feld, die Sie in der spaltenzuordnung angeben. für jede von diesen Datenmembern müssen Sie auch deklarieren Sie einen Datenmember für Status und ein Datenelement für die Länge. Weitere Informationen finden Sie unter [Feldstatus-Datenmember in vom Assistenten generierten Accessoren](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

    > [!NOTE]
    > Wenn Sie einen eigenen Consumer schreiben, müssen die Datenvariablen vor den Status- und Längenvariablen stammen.

- Instanziieren Sie eine Datenquelle und eine Sitzung an. Entscheiden, welcher Typ des Accessors und Rowset verwenden, und klicken Sie dann instanziiert ein Rowset mit [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md):

    ```cpp
    CDataSource ds;
    CSession ss;
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>
    ```

- Rufen Sie `CoInitialize` COM-Initialisierung Dies wird in der Hauptcode bezeichnet. Zum Beispiel:

    ```cpp
    HRESULT hr = CoInitialize(NULL);
    ```

- Rufen Sie [CDataSource:: Open](../../data/oledb/cdatasource-open.md) oder eine seine Varianten.

- Öffnen Sie eine Verbindung mit der Datenquelle, öffnen Sie die Sitzung, und öffnen Sie und initialisieren Sie das Rowset (und wenn ein Befehl auch führen Sie aus):

    ```cpp
    hr = ds.Open();
    hr = ss.Open(ds);
    hr = rs.Open();            // (Open also executes the command)
    ```

- Optional, Set-Rowset-Eigenschaften mit `CDBPropSet::AddProperty` und übergeben sie als Parameter an `rs.Open`. Ein Beispiel dafür, wie dies funktioniert, finden Sie unter `GetRowsetProperties` in [vom Methoden](../../data/oledb/consumer-wizard-generated-methods.md).

- Sie können jetzt das Rowset verwenden, zum Abrufen/Bearbeiten der Daten.

- Wenn Ihre Anwendung abgeschlossen ist, schließen Sie die Verbindung, Sitzung und Rowset aus:

    ```cpp
    rs.Close();
    ss.Close();
    ds.Close();
    ```

   Wenn Sie einen Befehl verwenden, sollten Sie zum Aufrufen `ReleaseCommand` nach `Close`. Das Codebeispiel in [CCommand:: Close](../../data/oledb/ccommand-close.md) zeigt, wie `Close` und `ReleaseCommand`.

- Rufen Sie `CoUnInitialize` Aufhebung der Initialisierung der COM. Dies wird in der Hauptcode bezeichnet.

    ```cpp
    CoUninitialize();
    ```

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Consumers](../../data/oledb/creating-an-ole-db-consumer.md)