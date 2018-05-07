---
title: OLE DB-Objektmodell | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ba9fd9b7ba5503f6ed5e1837147524f5abc7c31b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-object-model"></a>OLE DB-Objektmodell
Der OLE DB-Objektmodell besteht aus den folgenden Objekten oder Komponenten. Die ersten vier Objekte oder aufgelisteten Komponenten (Datenquellen, Sitzungen, Befehle und Rowsets) ermöglichen Ihnen, eine Verbindung mit einer Datenquelle herstellen und Sie ansehen. Der Rest, beginnend mit den Accessoren beziehen sich auf das Arbeiten mit den Daten, wenn er angezeigt wird.  
  
## <a name="data-sources"></a>Datenquellen  
 Datenquellenobjekte können Sie für die Verbindung mit einer Datenquelle, z. B. einer Datei oder eines DBMS. Ein Datenquellenobjekt erstellt und verwaltet die Verbindung und enthält Informationen zu Berechtigungen und zum Authentifizierungen (z. B. Benutzername und Kennwort). Ein Datenquellenobjekt kann eine oder mehrere Sitzungen erstellen.  
  
## <a name="sessions"></a>Sitzungen  
 Eine Sitzung verwaltet eine spezielle Interaktion mit der Datenquelle zum Abfragen und Abrufen von Daten. Jede Sitzung ist eine einzelne Transaktion. Eine Transaktion ist eine unteilbare Arbeitseinheit, die vom Test ACID-Eigenschaften definiert. Eine Definition der ACID-Eigenschaften, finden Sie unter [Transaktionen](#vcconoledbcomponents_transactions).  
  
 Sitzungen die wichtige Aufgaben wie Rowsets öffnen und die Rückgabe des Datenquellenobjekt, die sie erstellt haben. Sitzungen können auch Metadaten oder Informationen zu der Datenquelle selbst (z. B. Tabelleninformationen) zurückgeben.  
  
 Eine Sitzung kann einem oder mehreren Befehlen erstellen.  
  
## <a name="commands"></a>Befehle  
 Befehle ausführen, z. B. eine SQL-Anweisung einen Textbefehl. Der Textbefehl ein Rowset, z. B. eine SQL angegeben **wählen** -Anweisung, dem Befehl wird das Rowset erstellt.  
  
 Ein Befehl ist lediglich ein Container für einen Textbefehl, d. h. eine Zeichenfolge (z. B. eine SQL-Anweisung) von einem Consumer für die Ausführung von zugrunde liegenden Datenspeicher des Anbieters an ein Datenquellenobjekt übergeben. Der Textbefehl ist normalerweise eine SQL **wählen** Anweisung (in diesem Fall, da SQL **wählen** gibt ein Rowset erstellt der Befehl automatisch ein Rowset).  
  
## <a name="rowsets"></a>Rowsets  
 Rowsets machen Daten in tabellarischer Form an. Ein Index ist ein Sonderfall eines Rowsets. Sie können Rowsets aus der Sitzung oder den Befehl erstellen.  
  
### <a name="schema-rowsets"></a>Schemarowsets  
 Schemas enthalten Metadaten (Strukturinformationen) zu einer Datenbank. Schemarowsets sind Rowsets, die Schemainformationen enthält. Einige OLE DB-Anbieter für DBMS unterstützen Schemarowset-Objekte. Weitere Informationen zu Schemarowsets finden Sie unter [Abrufen von Metadaten mit Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) und [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
### <a name="view-objects"></a>Anzeigen von Objekten  
 Ein Objekt definiert eine Teilmenge der Zeilen und Spalten aus einem Rowset. Es enthält keine eigenen Daten. Anzeigen von Objekten können nicht auf Daten aus mehreren Rowsets kombinieren.  
  
## <a name="accessors"></a>Accessoren  
 Nur OLE DB verwendet das Konzept der Accessoren. Ein Accessor wird beschrieben, wie Daten in einem Consumer gespeichert werden. Sie enthält einen Satz von Bindungen (eine spaltenzuordnung bezeichnet) zwischen Rowset-Feldern (Spalten) und Datenmember, dass Sie in der Consumer nicht deklariert werden.  
  
##  <a name="vcconoledbcomponents_transactions"></a> Transaktionen  
 Transaktionsobjekte werden verwendet, wenn ein Commit oder Abbruch geschachtelte Transaktionen auf als der untersten. Eine Transaktion ist eine unteilbare Arbeitseinheit, die vom Test ACID-Eigenschaften definiert. ACID steht für:  
  
-   Unteilbarkeit: kann nicht in kleinere Arbeitseinheiten unterteilt werden.  
  
-   Parallelität: mehr als eine Transaktion kann zu einem Zeitpunkt auftreten.  
  
-   Isolation: eine Transaktion verfügt über wissen zu Änderungen durch eine andere beschränkt.  
  
-   Dauerhaftigkeit: die Transaktion werden permanente Änderungen.  
  
## <a name="enumerators"></a>Enumeratoren  
 Enumeratoren Suchen nach verfügbaren Datenquellen und andere Enumeratoren. Consumer, die nicht für eine bestimmte Datenquelle angepasst werden verwenden Enumeratoren für eine Datenquelle zur Suche.  
  
 Ein Stammenumerator, der im Lieferumfang von Microsoft Data Access SDK durchsucht die Registrierung nach Datenquellen und andere Enumeratoren. Andere Enumeratoren Durchsuchen der Registrierung oder die Suche in einer anbieterspezifischen Weise.  
  
## <a name="errors"></a>Fehler  
 Eine Schnittstelle für ein OLE DB-Objekt kann Fehler verursachen. Fehler enthalten zusätzliche Informationen zu einem Fehler, z. B. eine optionale benutzerdefinierte Error-Objekt. Diese Informationen sind in ein HRESULT enthalten.  
  
## <a name="notifications"></a>Benachrichtigungen  
 Benachrichtigungen werden von kooperierender Verbrauchergruppen Freigabe eines Rowsets verwendet (bedeutet freigeben, dass der Consumer wird angenommen, dass innerhalb der gleichen Transaktion ausgeführt werden). Aktivieren Benachrichtigungen kooperierende Consumern Freigabe eines Rowsets, die über die Aktionen für das Rowset, das von ihren Peers ausgeführten informiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)