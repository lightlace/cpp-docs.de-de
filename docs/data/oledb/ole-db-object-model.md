---
title: "OLE&#160;DB-Objektmodell | Microsoft Docs"
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
  - "OLE DB, Objektmodell"
  - "Rowsets, OLE DB-Objektmodell"
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# OLE&#160;DB-Objektmodell
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das OLE DB\-Objektmodell umfasst die folgenden Objekte oder Komponenten.  Die ersten vier aufgelisteten Objekte oder Komponenten \(Datenquellen, Sitzungen, Befehle und Rowsets\) ermöglichen es Ihnen, eine Verbindung zu einer Datenquelle aufzubauen und sie anzuzeigen.  Beginnend mit den Accessoren beziehen sich die übrigen auf die Arbeit mit bereits auf dem Bildschirm angezeigten Daten.  
  
## Datenquellen  
 Mithilfe von Datenquellenobjekten können Sie eine Verbindung zu einer Datenquelle, z. B. einer Datei oder einem DBMS, aufbauen.  Ein Datenquellenobjekt erstellt und verwaltet die Verbindung. Es enthält auch Berechtigungs\- und Authentifizierungsinformationen \(z. B. den Anmeldenamen und das Kennwort\).  Ein Datenquellenobjekt kann eine oder mehrere Sitzungen erstellen.  
  
## Sitzung  
 Eine Sitzung verwaltet eine spezielle Interaktion mit der Datenquelle, um Daten abzufragen und abzurufen.  Jede Sitzung ist eine einzelne Transaktion.  Eine Transaktion stellt eine unteilbare Arbeitseinheit dar und ist durch den ACID\-Test definiert.  Eine Definition von ACID finden Sie unter [Transaktionen](#vcconoledbcomponents_transactions).  
  
 Sitzungen führen wichtige Aufgaben aus, z. B. das Öffnen von Rowsets und die Rückgabe des Datenquellenobjekts, mit dem sie erstellt wurden.  Sitzungen können auch Metadaten oder Informationen über die Datenquelle \(z. B. Tabelleninformationen\) zurückgeben.  
  
 Eine Sitzung kann einen oder mehrere Befehle erstellen.  
  
## Befehle  
 Befehle führen Textbefehle, beispielsweise eine SQL\-Anweisung, aus.  Wird durch den Textbefehl ein Rowset angegeben, z. B. eine **SELECT**\-Anweisung in SQL, dann erstellt der Befehl den Rowset.  
  
 Ein Befehl ist lediglich ein Container für einen Textbefehl, der eine Zeichenfolge darstellt \(z. B. eine SQL\-Anweisung\), welche von einem Consumer zur Ausführung durch den zugrunde liegenden Datenspeicher des Anbieters an ein Datenquellenobjekt weitergegeben wird.  Gewöhnlich handelt es sich bei dem Textbefehl um eine **SELECT**\-Anweisung in SQL \(da die **SELECT**\-Anweisung in SQL einen Rowset angibt, erstellt der Befehl automatisch einen Rowset\).  
  
## Rowsets  
 Rowsets machen Daten in tabellarischem Format verfügbar.  Ein Index ist ein Sonderfall eines Rowsets.  Sie können Rowsets aus der Sitzung oder dem Befehl heraus erstellen.  
  
### Schemarowsets  
 Schemas enthalten Metadaten \(strukturelle Informationen\) über eine Datenbank.  Schemarowsets sind Rowsets, die Schemainformationen enthalten.  Einige OLE DB\-Anbieter für DBMS unterstützen Schemarowset\-Objekte.  Weitere Informationen über Schemarowsets finden Sie unter [Abrufen von Metadaten mit Schemarowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) und unter [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
### View\-Objekte  
 Ein View\-Objekt definiert eine Teilmenge der Zeilen und Spalten aus einem Rowset.  Es enthält keine eigenen Daten.  View\-Objekte sind nicht in der Lage, Daten aus mehreren Rowsets zu kombinieren.  
  
## Accessoren  
 Nur OLE DB verwendet das Konzept der Accessoren.  Ein Accessor beschreibt, wie Daten in einem Consumer gespeichert werden.  Er enthält einen Satz von Bindungen \(die so genannte Spaltenzuordnung\) zwischen Rowsetfeldern \(Spalten\) und Datenmember, die Sie im Consumer deklarieren.  
  
##  <a name="vcconoledbcomponents_transactions"></a> Transaktionen  
 Transaktionsobjekte werden verwendet, wenn die Übernahme oder das Abbrechen von geschachtelten Transaktionen auf einer anderen als der niedrigsten Ebene vorgenommen wird.  Eine Transaktion stellt eine unteilbare Arbeitseinheit dar und ist durch den ACID\-Test definiert.  ACID steht für:  
  
-   Atomicity \(Unteilbarkeit\): eine Einteilung in kleinere Arbeitseinheiten ist nicht möglich.  
  
-   Concurrency \(Parallelität\): mehrere Transaktionen können gleichzeitig ausgeführt werden.  
  
-   Isolation: eine Transaktion verfügt nur über eingeschränktes Wissen über durch andere Transaktionen herbeigeführte Änderungen.  
  
-   Durability \(Dauerhaftigkeit\): die Transaktion führt zu dauerhaften Änderungen.  
  
## Enumeratoren  
 Enumeratoren suchen nach verfügbaren Datenquellen und anderen Enumeratoren.  Consumers, die über keine Anpassung für eine bestimmte Datenquelle verfügen, suchen mithilfe von Enumeratoren nach einer verwendbaren Datenquelle.  
  
 Ein in Microsoft Data Access SDK enthaltener Basisenumerator durchsucht die Registrierung nach Datenquellen oder anderen Enumeratoren.  Andere Enumeratoren durchsuchen die Registrierung oder führen eine anbieterspezifische Suche durch.  
  
## Fehler  
 Alle Schnittstellen von beliebigen OLE DB\-Objekten können Fehlermeldungen generieren.  Fehlermeldungen enthalten zusätzliche Informationen über einen Fehler, einschließlich eines optionalen benutzerdefinierten Fehlerobjekts.  Diese Informationen sind in einem HRESULT enthalten.  
  
## Benachrichtigungen  
 Benachrichtigungen werden von Gruppen kooperierender Consumer verwendet, die sich einen Rowset teilen \("teilen" bedeutet hier die Annahme, dass die Consumer innerhalb der gleichen Transaktion arbeiten\).  Mithilfe von Benachrichtigungen können sich kooperierende Consumer, die sich einen Rowset teilen, über am Rowset durch Entwicklerkollegen ausgeführte Aktionen informieren.  
  
## Siehe auch  
 [OLE DB\-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB\-Programmierung](../../data/oledb/ole-db-programming-overview.md)