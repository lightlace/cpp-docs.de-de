---
title: Fragen von OLE DB-Architekturdesign | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b080945309732bec06c63eb665bbf6dd5f4acb5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340562"
---
# <a name="ole-db-architectural-design-issues"></a>Fragen zum OLE DB-Architekturdesign
Die folgenden Probleme sollten vor dem Starten der OLE DB-Anwendung:  
  
 **Welche Programmiersprachen Implementierung verwenden Sie die OLE DB-Anwendung zu schreiben?**  
 Microsoft bietet verschiedene Bibliotheken, um dies zu erreichen: ein OLE DB-Vorlagenbibliothek, OLE DB-Attribute und die unformatierten OLE DB-Schnittstellen in der OLE DB-SDK. Darüber hinaus stehen Assistenten zur Verfügung, mit denen Sie Ihr Programm schreiben. Diese Implementierungen werden in beschrieben [OLE DB-Vorlagen, Attribute und andere Implementierungen](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).  
  
 **Möchten Sie Ihren eigenen Anbieter schreiben?**  
 Die meisten Entwickler müssen nicht ihren eigenen Anbieter schreiben. Microsoft bietet verschiedene Anbieter. Jedes Mal, wenn Sie eine Datenverbindung (z. B., wenn Sie Ihr Projekt mithilfe der ATL-OLE DB-Consumer-Assistent einen Consumer hinzufügen), erstellen die **Datenlinkeigenschaften** Dialogfeld listet alle verfügbaren Anbieter in Ihrem System registriert. Wenn einer dieser Anbieter für die Access-Anwendung für Ihre eigenen Daten speichern und Daten geeignet ist, ist die einfachste Möglichkeit verwenden Sie eine der folgenden. Wenn Sie Ihren Datenspeicher nicht mit einer dieser Kategorien passt, müssen Sie jedoch einen eigenen Anbieter erstellen. Weitere Informationen zum Erstellen von Anbietern, finden Sie unter [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
 **Welche Ebene der Unterstützung benötigen Sie für Ihre Consumer?**  
 Einige Kunden können sehr einfach sein; während andere sehr komplex sein können. Die Funktionalität des OLE DB-Objekte wird durch die Eigenschaften angegeben. Wenn Sie die ATL-OLE DB-Consumer-Assistenten verwenden, um einen Consumer oder den Datenbank-Anbieter-Assistent zum Erstellen eines Anbieters zu erstellen, wird die entsprechenden Objekteigenschaften für Sie um einen standardmäßigen Satz von Funktionen zu gewähren. Wenn jedoch die-Assistenten generierte Klassen Consumer- oder Anbietersteuerelement nicht alles unterstützen Sie diese benötigen für Sie tun, Sie müssen zum Verweisen auf die Schnittstellen für diese Klassen werden im der [OLE DB-Vorlagenbibliothek](../../data/oledb/ole-db-templates.md). Diese Schnittstellen umschließen die unformatierten OLE DB-Schnittstellen, eine zusätzliche Implementierung erleichtert ihre Verwendung für Sie.  
  
 Z. B. Wenn Sie Daten in einem Rowset aktualisiert werden soll, aber Sie haben vergessen, dies anzugeben, bei der Erstellung des Consumers mit dem Assistenten, können Sie angeben die Funktionalität nach dem Fakt durch Festlegen der `DBPROP_IRowsetChange` und `DBPROP_UPDATABILITY` Eigenschaften für das Command-Objekt. Klicken Sie dann, wenn das Rowset erstellt wurde, haben sie die `IRowsetChange` Schnittstelle.  
  
 **Haben Sie älteren Code mit einem anderen datenzugriffstechnologie (ADO, ODBC oder DAO)?**  
 Angesichts der möglichen Kombinationen von Technologien (z. B. Verwenden von ADO-Komponenten mit OLE DB-Komponenten, und Migrieren von ODBC-Code zu OLE DB), ist würde den Rahmen der Visual C++-Dokumentation in allen Situationen abdecken. Stehen jedoch zahlreiche Artikel, die für verschiedene Szenarien auf den folgenden Microsoft-Websites:  
  
-   [Microsoft-Hilfe und -Support](http://go.microsoft.com/fwlink/p/?linkid=148218)  
  
-   [Microsoft Data Access – technische Artikel (Übersicht)](http://go.microsoft.com/fwlink/p/?linkid=148217)  
  
-   [Visual Studio Solution Center](http://go.microsoft.com/fwlink/p/?linkid=148215)  
  
-   [Auf Microsoft.com suchen](http://search.microsoft.com/)  
  
 Wenn Sie eine Suche ausführen, geben Sie eine Kombination der Schlüsselwörter, die Ihr Szenario am besten geeignet ist: zum Beispiel: Wenn Sie ADO-Objekte mit einem OLE DB-Anbieter verwendet haben, versuchen Sie es mit eine boolesche Suche mit **ADO und "OLE DB"**. Wenn Sie ältere DAO-Code zu ODBC zu migrieren möchten, wählen Sie "alle Wörter", und geben Sie z. B. Zeichenfolgen **Migrieren von DAO**.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)