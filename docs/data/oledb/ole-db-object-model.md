---
title: OLE DB-Objektmodell
ms.date: 10/22/2018
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
ms.openlocfilehash: 303ad4166f0f1126182956fae9c19f513be7cfb3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039155"
---
# <a name="ole-db-object-model"></a>OLE DB-Objektmodell

Der OLE DB-Objektmodell besteht aus den folgenden Objekten oder Komponenten. Die ersten vier Objekte oder aufgeführten Komponenten (Datenquellen, Sitzungen, Befehle und Rowsets) können Sie mit einer Datenquelle verbinden und anzeigen. Die Rest-, beginnend mit den Accessoren beziehen sich auf arbeiten mit den Daten, wenn er angezeigt wird.

## <a name="data-sources"></a>Datenquellen

Datenquellenobjekte können Sie für die Verbindung mit einer Datenquelle, z. B. eine Datei oder DBMS. Ein Datenquellenobjekt erstellt und verwaltet die Verbindung und Berechtigungen und Authentifizierungen Informationen (z. B. Anmeldenamen und Kennwort) enthält. Ein Datenquellenobjekt kann eine oder mehrere Sitzungen erstellen.

## <a name="sessions"></a>Sitzungen

Eine Sitzung verwaltet eine spezielle Interaktion mit der Datenquelle zum Abfragen und Abrufen von Daten. Jede Sitzung ist eine einzelne Transaktion. Eine Transaktion ist eine unteilbare Arbeitseinheit, die von der Lackmustest definiert. Eine Definition von ACID verfügen, finden Sie unter [Transaktionen](#vcconoledbcomponents_transactions).

Sitzungen werden wichtige Aufgaben wie das Öffnen des Rowsets und die Rückgabe des Datenquellenobjekt, das sie erstellt haben. Sitzungen können auch Metadaten oder Informationen zu der Datenquelle selbst (z. B. Tabelleninformationen) zurückgeben.

Eine Sitzung kann einem oder mehreren Befehlen erstellen.

## <a name="commands"></a>Befehle

Befehle ausführen, einen Textbefehl, z. B. eine SQL­Anweisung. Der Textbefehl ein Rowset, z. B. eine SQL angegeben **wählen** -Anweisung, dem Befehl wird das Rowset erstellt.

Ein Befehl ist lediglich ein Container für einen Textbefehl, der eine Zeichenfolge (z. B. eine SQL-Anweisung) von einem Consumer auf ein Datenquellenobjekt für die Ausführung durch den Anbieter des zugrunde liegenden Datenspeicher gespeichert ist. In der Regel der Textbefehl ist eine SQL **wählen** Anweisung (in diesem Fall ist, da SQL **wählen** gibt ein Rowset, erstellt der Befehl automatisch ein Rowset).

## <a name="rowsets"></a>Rowsets

Rowsets werden Daten im Tabellenformat angezeigt. Ein Index ist ein Sonderfall eines Rowsets. Sie können die Rowsets aus der Sitzung oder den Befehl erstellen.

### <a name="schema-rowsets"></a>Schemarowsets

Schemas sind Metadaten (Strukturinformationen) zu einer Datenbank. Schemarowsets sind Rowsets, die Schemainformationen zu haben. Einige OLE DB-Anbieter für DBMS unterstützen Schemarowset-Objekte. Weitere Informationen zu Schemarowsets finden Sie unter [Abrufen von Metadaten mit Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) und [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).

### <a name="view-objects"></a>Objekte anzeigen

Ein Objekt definiert eine Teilmenge der Zeilen und Spalten aus einem Rowset. Es verfügt über keine eigenen Daten. Objekte können nicht auf Daten aus mehreren Rowsets kombinieren.

## <a name="accessors"></a>Zugriffsmethoden

Nur OLE DB verwendet das Konzept der Accessoren. Ein Accessor wird beschrieben, wie Daten in einem Consumer gespeichert werden. Er besitzt einen Satz von Bindungen (eine spaltenzuordnung bezeichnet), zwischen Rowset-Feldern (Spalten) und Datenelemente, die Sie in der Consumer nicht deklarieren.

##  <a name="vcconoledbcomponents_transactions"></a> Transaktionen

Transaktionsobjekte werden verwendet, wenn durch Commit oder Abbruch von geschachtelten Transaktionen auf als der untersten Ebene. Eine Transaktion ist eine unteilbare Arbeitseinheit, die von der Lackmustest definiert. ACID steht für:

- Unteilbarkeit, kann nicht in kleinere Arbeitseinheiten unterteilt werden

- Parallelität kann mehr als eine Transaktion zu einem Zeitpunkt ausgeführt.

- Isolation, eine Transaktion verfügt über Kenntnisse über Änderungen, die von einem anderen beschränkt.

- Dauerhaftigkeit, nimmt die Transaktion permanente Änderungen

## <a name="enumerators"></a>Enumeratoren

Enumeratoren suchen Sie nach verfügbaren Datenquellen und anderen Enumeratoren. Kunden, die für eine bestimmte Datenquelle angepasst werden nicht verwenden Enumeratoren, um für eine Datenquelle zu verwenden, zu suchen.

Ein Stammenumerator, der im Lieferumfang von Microsoft Data Access SDK, durchläuft die Registrierung von Datenquellen und anderen Enumeratoren nach. Andere Enumeratoren Durchlaufen der Registrierung oder die Suche in einer anbieterspezifischen Weise.

## <a name="errors"></a>Fehler

Jede Schnittstelle auf jedem OLE DB-Objekt kann Fehler verursachen. Weitere Informationen zu einem Fehler, einschließlich eine optionale benutzerdefinierte Fehlerobjekt auch Fehler sein. Diese Informationen werden in ein HRESULT gespeichert.

## <a name="notifications"></a>Benachrichtigungen

Benachrichtigungen werden von miteinander kommunizierenden consumergruppen, die Freigabe eines Rowsets verwendet (, in denen bedeutet freigeben, dass Consumer davon ausgegangen, dass werden innerhalb derselben Transaktion arbeiten). Aktivieren Benachrichtigungen miteinander kommunizierenden Consumer Freigabe eines Rowsets über Aktionen für das Rowset, das von ihren Kollegen ausgeführten informiert werden.

## <a name="see-also"></a>Siehe auch

[OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)<br/>
[Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)