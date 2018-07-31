---
title: Erstellen eines aktualisierbaren Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e9ee36d2300ed1e86c1f867012ed54c85692f5bd
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340637"
---
# <a name="creating-an-updatable-provider"></a>Erstellen eines aktualisierbaren Anbieters

Visual C++ unterstützt aktualisierbare Anbieter oder Anbieter, die aktualisiert werden können (Schreiben) dem Datenspeicher. In diesem Thema wird erläutert, wie aktualisierbare Anbieter, die mithilfe von OLE DB-Vorlagen erstellt werden.  
  
 In diesem Thema wird davon ausgegangen, dass Sie mit einem praktikable Anbieter starten. Es gibt zwei Schritte zum Erstellen eines aktualisierbaren Anbieters. Zunächst müssen Sie entscheiden, wie der Anbieter Änderungen an den Datenspeicher vereinfachen; insbesondere gibt an, ob Änderungen werden sofort erfolgen oder verzögert, bis ein Updatebefehl ausgegeben wird. Im Abschnitt "[aktualisierbare Anbieter machen](#vchowmakingprovidersupdatable)" beschreibt die Änderungen und die Einstellungen, die Sie in den Anbietercode tun müssen.  
  
 Als Nächstes müssen Sie sicherstellen, dass Ihr Anbieter enthält die gesamte Funktionalität zur Unterstützung der Consumer des anfordern kann. Wenn der Consumer den Datenspeicher zu aktualisieren möchte, muss der Anbieter Code enthalten, die Daten im Datenspeicher beibehalten. Beispielsweise können Sie der C-Laufzeitbibliothek oder die MFC-verwenden, um die Vorgänge an der Datenquelle auszuführen. Im Abschnitt "[Schreiben in die Datenquelle](#vchowwritingtothedatasource)" beschreibt, wie Sie mit der Datenquelle zu schreiben, befassen sich mit NULL-und Standardwerten und Spaltenflags festlegen.  
  
> [!NOTE]
>  UpdatePV ist ein Beispiel eines aktualisierbaren Anbieters. UpdatePV ist identisch, wie MyProv, jedoch mit aktualisierbaren Unterstützung.  
  
##  <a name="vchowmakingprovidersupdatable"></a> Machen Anbieter aktualisiert  

 Einen Anbieter aktualisierbare entscheidend besteht im ermitteln welche Vorgänge Sie möchten Ihren Anbieter, führen Sie auf den Datenspeicher und wie der Anbieter diese Vorgänge ausführen soll. Insbesondere das wesentliche Problem ist, ob Updates für den Datenspeicher sind sofort ausgeführt oder verzögert werden soll (Batchverarbeitung) bis ein Update-Befehl ausgegeben wird.  
  
 Zunächst müssen Sie entscheiden, ob die von erben `IRowsetChangeImpl` oder `IRowsetUpdateImpl` in der Rowsetklasse. Je nachdem, welche dieser Sie implementieren, die Funktionalität von drei Methoden sind betroffen: `SetData`, `InsertRows`, und `DeleteRows`.  
  
- Wenn das erben [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), ändert sich den Datenspeicher diese drei Methoden direkt aufzurufen.  
  
- Wenn das erben [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), die Methoden Änderungen an den Datenspeicher verzögern, bis zum Aufruf von `Update`, `GetOriginalData`, oder `Undo`. Wenn das Update mehrere Änderungen betrifft, werden sie ausgeführt, im Modus "Batch" (Beachten Sie, dass die Batchverarbeitung von Änderungen viel Speicher-Overhead hinzufügen kann).  
  
 Beachten Sie, dass `IRowsetUpdateImpl` leitet sich von `IRowsetChangeImpl`. Daher `IRowsetUpdateImpl` erhalten Sie die Funktion und der Batch-Funktion ändern.  
  
#### <a name="to-support-updatability-in-your-provider"></a>Zur Unterstützung von aktualisierbarkeit im Anbieter  
  
1. In der Rowsetklasse erben `IRowsetChangeImpl` oder `IRowsetUpdateImpl`. Diese Klassen bieten die entsprechende Schnittstellen für das Ändern des Datenspeichers:  
  
     **Hinzufügen von IRowsetChange**  
  
     Hinzufügen `IRowsetChangeImpl` der Vererbungskette, die mit dieser Form:  
  
    ```cpp  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Auch hinzufügen, `COM_INTERFACE_ENTRY(IRowsetChange)` auf die `BEGIN_COM_MAP` Abschnitt in der Rowsetklasse.  
  
     **IRowsetUpdate hinzufügen**  
  
     Hinzufügen `IRowsetUpdate` der Vererbungskette, die mit dieser Form:  
  
    ```cpp  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Entfernen Sie die `IRowsetChangeImpl` Zeile aus der Vererbungskette. Diese Ausnahme von der zuvor erwähnten Direktive muss den Code für enthalten `IRowsetChangeImpl`.  
  
2.  Fügen Sie Folgendes der COM-Zuordnung (`BEGIN_COM_MAP ... END_COM_MAP`):  
  
    |Wenn Sie implementieren|COM-Zuordnung hinzufügen|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  Fügen Sie in zunutze, Folgendes ein, um die Zuordnung des Set (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):  
  
    |Wenn Sie implementieren|Fügen Sie zum Festlegen der eigenschaftenzuordnung|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  In der Zuordnung des Eigenschaftensets sollten Sie auch alle der folgenden Einstellungen hinzufügen wie sie unten angezeigt werden:  
  
    ```cpp  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     Sie finden die Werte in diesen anhand Atldb.h für die Eigenschaft-IDs und Werte (wenn die Onlinedokumentation Atldb.h unterscheidet, Atldb.h Vorrang vor der Dokumentation).  
  
    > [!NOTE]
    >  Viele der `VARIANT_FALSE` und `VARIANT_TRUE` Einstellungen sind erforderlich, durch die OLE DB-Vorlagen, die OLE DB-Spezifikation sagt, können sie Lese-/Schreibzugriff sein, aber die OLE DB-Vorlagen unterstützt nur einen Wert.  
  
     **Wenn Sie IRowsetChangeImpl implementieren**  
  
     Wenn Sie implementieren `IRowsetChangeImpl`, Sie müssen die folgenden Eigenschaften festlegen, für den Anbieter. Diese Eigenschaften werden in erster Linie verwendet, um die Schnittstellen durch anzufordern `ICommandProperties::SetProperties`.  
  
    - `DBPROP_IRowsetChange`: Automatisches Festlegen von diesem legt `DBPROP_IRowsetChange`.  
  
    - `DBPROP_UPDATABILITY`: Eine Bitmaske, die unterstützten Methoden für `IRowsetChange`: `SetData`, `DeleteRows`, oder `InsertRow`.  
  
    - `DBPROP_CHANGEINSERTEDROWS`: Der Consumer kann Aufrufen `IRowsetChange::DeleteRows` oder `SetData` für neu eingefügte Zeilen.  
  
    - `DBPROP_IMMOBILEROWS`: Rowset nicht eingefügte oder aktualisierte Zeilen neu angeordnet.  
  
     **Wenn Sie IRowsetUpdateImpl implementieren**  
  
     Wenn Sie implementieren `IRowsetUpdateImpl`, müssen Sie die folgenden Eigenschaften festlegen für den Anbieter darüber hinaus mit dem Festlegen aller Eigenschaften für `IRowsetChangeImpl` oben aufgeführt:  
  
    - `DBPROP_IRowsetUpdate`  
  
    - `DBPROP_OWNINSERT`: READ_ONLY und auf VARIANT_TRUE festgelegt muss werden.  
  
    - `DBPROP_OWNUPDATEDELETE`: READ_ONLY und auf VARIANT_TRUE festgelegt muss werden.  
  
    - `DBPROP_OTHERINSERT`: READ_ONLY und auf VARIANT_TRUE festgelegt muss werden.  
  
    - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY und auf VARIANT_TRUE festgelegt muss werden.  
  
    - `DBPROP_REMOVEDELETED`: READ_ONLY und auf VARIANT_TRUE festgelegt muss werden.  
  
    - `DBPROP_MAXPENDINGROWS`  
  
        > [!NOTE]
        >  Wenn Sie Benachrichtigungen unterstützen, müssen Sie auch einige andere Eigenschaften sowie möglicherweise; finden Sie im Abschnitt `IRowsetNotifyCP` für diese Liste.  
  
##  <a name="vchowwritingtothedatasource"></a> Das Schreiben in die Datenquelle  
 Um Daten aus der Datenquelle zu lesen, rufen Sie die `Execute` Funktion. Rufen Sie zum Schreiben an die Datenquelle die `FlushData` Funktion. (In einem allgemeinen Sinn, leeren Sie die Möglichkeit, Änderungen zu speichern, die Sie an einer Tabelle oder eines Indexes auf dem Datenträger.)  

