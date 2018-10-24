---
title: OLE DB-Consumervorlagen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- databases [C++], OLE DB templates
- OLE DB consumers [C++], data access
- OLE DB consumer templates [C++]
- databases [C++], consumers
ms.assetid: d3e42612-0bc0-4d65-9c32-0e8a7b219e82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9983b9347fb0c39333bba33f1c7b1d9237b407ce
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990138"
---
# <a name="ole-db-consumer-templates-c"></a>OLE DB-Consumervorlagen (C++)

Die OLE DB-Consumervorlagen unterstützen die Spezifikation der OLE DB Version 2.6. (Die OLE DB-Consumervorlagen werden mit OLE DB 2.6 getestet aber nicht jede Schnittstelle in der Spezifikation unterstützen.) Die Consumervorlagen minimieren die Menge an Code, den Sie schreiben müssen, um einen OLE DB-Consumer zu implementieren. Die Vorlagen bieten Folgendes:  
  
- Einfacher Zugriff auf OLE DB-Features und einfache Integration mit ATL und MFC.  
  
- Ein einfaches Bindungsmodell für Datenbankparameter und Spalten.  
  
- Systemeigene C/C++-Datentypen für die OLE DB-Programmierung.  
  
Sie sollten mit C++-Vorlagen, COM und den OLE DB-Schnittstellen vertraut sein, um OLE DB-Vorlagen verwenden zu können. Wenn Sie nicht mit OLE DB vertraut sind, finden Sie unter [OLE DB-Programmierreferenz](/previous-versions/windows/desktop/ms718124).  
  
Die OLE DB-Vorlagen unterstützen eher das vorhandene OLE DB-Objektmodell als das Hinzufügen eines neuen Objektmodells. Die Klassen der obersten Ebene in den OLE DB-Consumervorlagen gleichen den in der der OLE DB-Spezifikation definierten Komponenten. Das Design der OLE DB-Consumervorlagen umfasst erweiterte Features, z. B. mehrere Accessoren für ein Rowset. Durch die Verwendung von Vorlagen und der mehrfachen Vererbung ergibt sich eine kleine und flexible Bibliothek.  
  
## <a name="how-ole-db-consumers-access-data"></a>Zugriff auf Daten durch OLE DB-Consumer  

Consumer verwenden verschiedene Arten von Objekten, die in den folgenden Themen beschrieben werden:  
  
- [Datenquellen und Sitzungen](../../data/oledb/data-sources-and-sessions.md)  
  
- [Accessoren und Rowsets](../../data/oledb/accessors-and-rowsets.md)  
  
- [Befehle und Tabellen](../../data/oledb/commands-and-tables.md)  
  
- [Benutzerdatensätze](../../data/oledb/user-records.md)  
  
Bevor der Consumer aktiv wird, wählen Sie zunächst einen OLE DB-Anbieter aus, der für den Datenbanktyp geeignet ist, auf den Sie zugreifen müssen (z. B. SQL, Oracle, ODBC und MSDS). Zu diesem Zweck verwenden Sie in der Regel einen Enumerator (siehe [CEnumerator](../../data/oledb/cenumerator-class.md) wie unter [Datenquellen und Sitzungen](../../data/oledb/data-sources-and-sessions.md)angegeben).  
  
Das [Datenquellenobjekt](../../data/oledb/data-sources-and-sessions.md) bietet die zum Herstellen der Verbindung mit der ausgewählten Datenquelle erforderlichen Verbindungsinformationen. Das Datenquellenobjekt enthält auch Authentifizierungsinformationen (z. B. Anmeldenamen und Kennwörter), über die Benutzer die Berechtigung zum Zugriff auf die Datenquelle erhalten. Das Datenquellenobjekt stellt eine Verbindung mit der Datenbank her und erstellt dann mindestens ein Sitzungsobjekt. Jede [Sitzungsobjekt](../../data/oledb/data-sources-and-sessions.md) verwaltet seine eigenen Interaktionen mit der Datenbank (d h. Abfragen und Abrufen von Daten) und führt diese Transaktionen unabhängig von anderen vorhandenen Sitzungen durch.  
  
Die Sitzung erstellt die Rowset- und Befehlsobjekte. Das [Befehlsobjekt](../../data/oledb/commands-and-tables.md) ermöglicht Benutzern die Interaktion mit der Datenbank, z. B. über SQL-Befehle. Das [Rowsetobjekt](../../data/oledb/accessors-and-rowsets.md) besteht aus einem Satz von Daten, über den Sie navigieren können. Zudem können Sie darin [Zeilen aktualisieren, löschen und einfügen](../../data/oledb/updating-rowsets.md).  
  
Ein OLE DB-Consumer bindet Spalten in den Datenbanktabellen an die lokalen Variablen. Zu diesem Zweck verwendet er einen [Accessor](../../data/oledb/accessors-and-rowsets.md), der eine Übersicht darüber enthält, wie Daten im Consumer gespeichert werden. Die Übersicht besteht aus einem Satz von Bindungen zwischen Tabellenspalten und lokalen Puffern (Variablen) in der Consumeranwendung.  
  
Ein wichtiges Konzept bei der Arbeit mit Consumern ist, dass Sie in einem Consumer zwei Klassen deklarieren: [Befehlsklasse (oder Tabellenklasse)](../../data/oledb/commands-and-tables.md) und [Benutzerdatensatzklasse](../../data/oledb/user-records.md). Der Zugriff auf das Rowset erfolgt über die Befehlsklasse (oder Tabellenklasse), die sowohl von einer Accessor- als auch von einer Rowsetklasse erbt. Die Benutzerdatensatzklasse enthält die zuvor beschriebene Bindungsübersicht für das Rowset.  
  
Weitere Informationen finden Sie unter den folgenden Themen:  
  
- [Erstellen eines OLE DB-Consumers](../../data/oledb/creating-an-ole-db-consumer.md)  
  
- [Allgemeine Szenarien für OLE DB-Consumer (Beispiele)](../../data/oledb/working-with-ole-db-consumer-templates.md)  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)<br/>
[Datenzugriff](../data-access-in-cpp.md)<br/>
[OLE DB-SDK-Dokumentation](/previous-versions/windows/desktop/ms722784)<br/>
[OLE DB-Programmierreferenz](/previous-versions/windows/desktop/ms713643)