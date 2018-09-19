---
title: OLE DB-Objektmodell | Microsoft-Dokumentation
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
ms.openlocfilehash: c0bd4c8f18addf50dfcee525dea255f75b2fdf75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101477"
---
# <a name="ole-db-object-model"></a>OLE DB-Objektmodell

Der OLE DB-Objektmodell besteht aus den folgenden Objekten oder Komponenten. Die ersten vier Objekte oder aufgeführten Komponenten (Datenquellen, Sitzungen, Befehle und Rowsets) können Sie mit einer Datenquelle verbinden und anzeigen. Die Rest-, beginnend mit den Accessoren beziehen sich auf arbeiten mit den Daten, wenn er angezeigt wird.  
  
## <a name="data-sources"></a>Datenquellen  

Datenquellenobjekte können Sie für die Verbindung mit einer Datenquelle, z. B. eine Datei oder DBMS. Ein Datenquellenobjekt erstellt und verwaltet die Verbindung und Berechtigungen und Authentifizierungen Informationen (z. B. Anmeldenamen und Kennwort) enthält. Ein Datenquellenobjekt kann eine oder mehrere Sitzungen erstellen.  
  
## <a name="sessions"></a>Sitzungen  

Eine Sitzung verwaltet eine spezielle Interaktion mit der Datenquelle zum Abfragen und Abrufen von Daten. Jede Sitzung ist eine einzelne Transaktion. Eine Transaktion ist eine unteilbare Arbeitseinheit, die von der Lackmustest definiert. Eine Definition von ACID verfügen, finden Sie unter [Transaktionen](#vcconoledbcomponents_transactions).  
  
Sitzungen führen Sie wichtige Aufgaben wie das Öffnen des Rowsets und die Rückgabe des Datenquellenobjekt, das sie erstellt haben. Sitzungen können auch Metadaten oder Informationen zu der Datenquelle selbst (z. B. Tabelleninformationen) zurückgeben.  
  
Eine Sitzung kann einem oder mehreren Befehlen erstellen.  
  
## <a name="commands"></a>Befehle  

Befehle ausführen, einen Textbefehl, z. B. eine SQL­Anweisung. Der Textbefehl ein Rowset, z. B. eine SQL angegeben **wählen** -Anweisung, dem Befehl wird das Rowset erstellt.  
  
Ein Befehl ist lediglich ein Container für einen Textbefehl, der eine Zeichenfolge (z. B. eine SQL-Anweisung) von einem Consumer auf ein Datenquellenobjekt für die Ausführung durch den Anbieter des zugrunde liegenden Datenspeicher gespeichert ist. In der Regel der Textbefehl ist eine SQL **wählen** Anweisung (in diesem Fall ist, da SQL **wählen** gibt ein Rowset, erstellt der Befehl automatisch ein Rowset).  
  
## <a name="rowsets"></a>Rowsets  

Rowsets verfügbar machen, Daten im Tabellenformat. Ein Index ist ein Sonderfall eines Rowsets. Sie können die Rowsets aus der Sitzung oder den Befehl erstellen.  
  
### <a name="schema-rowsets"></a>Schemarowsets  

Schemas enthalten Metadaten (Strukturinformationen) zu einer Datenbank. Schemarowsets sind Rowsets, die Schemainformationen enthalten. Einige OLE DB-Anbieter für DBMS unterstützen Schemarowset-Objekte. Weitere Informationen zu Schemarowsets finden Sie unter [Abrufen von Metadaten mit Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) und [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
### <a name="view-objects"></a>Objekte anzeigen  

Ein Objekt definiert eine Teilmenge der Zeilen und Spalten aus einem Rowset. Sie enthält keine eigenen Daten. Objekte können nicht auf Daten aus mehreren Rowsets kombinieren.  
  
## <a name="accessors"></a>Zugriffsmethoden  

Nur OLE DB verwendet das Konzept der Accessoren. Ein Accessor wird beschrieben, wie Daten in einem Consumer gespeichert werden. Sie enthält einen Satz von Bindungen (eine spaltenzuordnung bezeichnet) zwischen Rowset-Feldern (Spalten) und Datenelemente, die Sie in der Consumer nicht deklarieren.  
  
##  <a name="vcconoledbcomponents_transactions"></a> Transaktionen  

Transaktionsobjekte werden verwendet, wenn durch Commit oder Abbruch von geschachtelten Transaktionen auf als der untersten Ebene. Eine Transaktion ist eine unteilbare Arbeitseinheit, die von der Lackmustest definiert. ACID steht für:  
  
- Unteilbarkeit: kann nicht in kleinere Arbeitseinheiten unterteilt werden.  
  
- Parallelität: Es kann mehr als eine Transaktion zu einem Zeitpunkt auftreten.  
  
- Isolation: eine Transaktion verfügt über Kenntnisse zu Änderungen, die von einem anderen beschränkt.  
  
- Dauerhaftigkeit: die Transaktion werden permanente Änderungen.  
  
## <a name="enumerators"></a>Enumeratoren  

Enumeratoren suchen Sie nach verfügbaren Datenquellen und anderen Enumeratoren. Kunden, die nicht für eine bestimmte Datenquelle angepasst werden verwenden Enumeratoren, um für eine Datenquelle zu verwenden, zu suchen.  
  
Ein Stammenumerator, der im Lieferumfang von Microsoft Data Access SDK, durchläuft die Registrierung von Datenquellen und anderen Enumeratoren nach. Andere Enumeratoren Durchlaufen der Registrierung oder die Suche in einer anbieterspezifischen Weise.  
  
## <a name="errors"></a>Fehler  

Jede Schnittstelle auf jedem OLE DB-Objekt kann Fehler verursachen. Fehler enthalten zusätzliche Informationen zu einem Fehler, einschließlich eine optionale benutzerdefinierte Error-Objekt. Diese Informationen sind in ein HRESULT enthalten.  
  
## <a name="notifications"></a>Benachrichtigungen  

Benachrichtigungen werden von miteinander kommunizierenden consumergruppen, die Freigabe eines Rowsets verwendet (, in denen bedeutet freigeben, dass Consumer davon ausgegangen, dass werden innerhalb derselben Transaktion arbeiten). Aktivieren Benachrichtigungen miteinander kommunizierenden Consumer Freigabe eines Rowsets über Aktionen für das Rowset, das von ihren Kollegen ausgeführten informiert werden.  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)<br/>
[Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)