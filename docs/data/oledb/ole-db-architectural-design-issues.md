---
title: OLE DB-Architekturdesign | Microsoft Docs
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
ms.openlocfilehash: 75d996416e92ded920f45d3352c6478dd8c67a86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109780"
---
# <a name="ole-db-architectural-design-issues"></a>Fragen zum OLE DB-Architekturdesign
Vor dem Starten der OLE DB-Anwendung sollten Sie Folgendes berücksichtigen:  
  
 **Welche Implementierung programmieren verwenden Sie zum Schreiben der OLE DB-Anwendung?**  
 Microsoft bietet mehrere Bibliotheken, um dies zu erreichen: ein OLE DB-Vorlagenbibliothek, OLE DB-Attribute und die unformatierten OLE DB-Schnittstellen in der OLE DB-SDK. Darüber hinaus stehen Assistenten, mit deren Hilfe Sie das Programm schreiben. Diese Implementierungen werden in beschrieben [OLE DB-Vorlagen, Attribute und andere Implementierungen](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).  
  
 **Müssen Sie einen eigenen Anbieter schreiben?**  
 Die meisten Entwickler müssen nicht ihre eigenen Anbieter schreiben. Microsoft bietet verschiedene Anbieter. Wenn Sie eine Datenverbindung (z. B., wenn Sie Ihr Projekt mithilfe der ATL-OLE DB-Consumer-Assistenten einen Consumer hinzufügen), erstellen die **Datenlinkeigenschaften** Dialogfeld listet alle verfügbaren Anbieter, die auf Ihrem System registriert. Wenn Sie einen dieser Anbieter für die Anwendung der Zugriff für Ihre eigenen Daten speichern und Daten geeignet ist, ist die einfachste Vorgehensweise verwenden Sie eines der folgenden an. Wenn der Datenspeicher nicht mit einer dieser Kategorien passt, müssen Sie jedoch einen eigenen Anbieter erstellen. Informationen zum Erstellen von Anbietern finden Sie unter [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
 **Welche Ebene der Unterstützung für den Consumer müssen?**  
 Einige Consumer können sehr einfach sein. während andere sehr komplex sein können. Die Funktionalität des OLE DB-Objekte wird durch die Eigenschaften angegeben. Wenn Sie ATL-OLE DB-Consumer-Assistenten zum Erstellen eines Consumers oder die Datenbank-Anbieter-Assistenten zum Erstellen eines Anbieters verwenden, wird die entsprechende Objekteigenschaften für Sie, um einen standardmäßigen Satz von Funktionen zu erteilen. Jedoch, wenn die-Assistenten generierte Klassen Consumer oder Anbieter nicht alles Sie sie unterstützen benötigen möchten, müssen Sie zum Verweisen auf die Schnittstellen für diese Klassen in der [OLE DB-Vorlagenbibliothek](../../data/oledb/ole-db-templates.md). Diese Schnittstellen umschließen die unformatierten OLE DB-Schnittstellen, zusätzliche Implementierung einfacher deren Verwendung für Sie bereitstellen.  
  
 Z. B. Wenn Sie Daten in einem Rowset aktualisieren möchten, aber vergessen, die dies angeben, wenn Sie den Consumer mit dem Assistenten erstellt haben, können Sie angeben die Funktionalität nach Abschluss der Aktivitäten durch Festlegen der **DBPROP_IRowsetChange** und  **DBPROP_UPDATABILITY** Eigenschaften für das Command-Objekt. Klicken Sie dann, wenn das Rowset erstellt wird, kann die `IRowsetChange` Schnittstelle.  
  
 **Haben Sie älterem Code mit einem anderen datenzugriffstechnologie (ADO, ODBC- oder DAO)?**  
 Angesichts der möglichen Kombinationen von Technologien (z. B. Verwenden von ADO-Komponenten mit OLE DB-Komponenten, und Migrieren von ODBC-Code von OLE DB), ist in allen Situationen abdecken, Gegenstand des Visual C++-Dokumentation. Allerdings stehen viele verschiedene Szenarien abdecken Artikel auf den folgenden Microsoft-Websites:  
  
-   [Microsoft-Hilfe und -Support](http://go.microsoft.com/fwlink/p/?linkid=148218)  
  
-   [Microsoft Data Access – technische Artikel (Übersicht)](http://go.microsoft.com/fwlink/p/?linkid=148217)  
  
-   [Visual Studio-Lösungscenter](http://go.microsoft.com/fwlink/p/?linkid=148215)  
  
-   [Suchen Sie "Microsoft.com"](http://search.microsoft.com/)  
  
 Wenn Sie eine Suche ausführen, geben Sie eine Kombination von Schlüsselwörtern, die Ihr Szenario am besten geeignet ist. zum Beispiel: Wenn Sie ADO-Objekten mit einem OLE DB-Anbieter verwendet haben, versuchen Sie eine boolesche Suche mit **ADO und "OLE DB"**. Wenn Sie ältere DAO-Code zu ODBC zu migrieren möchten, wählen Sie "alle Wörter", und geben Sie z. B. Zeichenfolgen **Migrieren von DAO**.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)