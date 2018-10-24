---
title: Fragen von OLE DB-Architekturdesign | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
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
ms.openlocfilehash: a79cc4dfa36170293a8832571ba3348d6e2c8865
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990022"
---
# <a name="ole-db-architectural-design-issues"></a>Fragen zum OLE DB-Architekturdesign

Beachten Sie die folgenden Probleme vor dem Starten der OLE DB-Anwendung:  
  
## <a name="what-programming-implementation-will-you-use-to-write-your-ole-db-application"></a>Welche Programmiersprachen Implementierung verwenden Sie die OLE DB-Anwendung zu schreiben?

Microsoft bietet verschiedene Bibliotheken für diese Aufgabe: eine OLE DB-Vorlagenbibliothek, OLE DB-Attribute und die unformatierten OLE DB-Schnittstellen in der OLE DB-SDK. Darüber hinaus stehen Assistenten zur Verfügung, mit denen Sie Ihr Programm schreiben. Diese Implementierungen werden in beschrieben [OLE DB-Vorlagen, Attribute und andere Implementierungen](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).

## <a name="do-you-need-to-write-your-own-provider"></a>Möchten Sie Ihren eigenen Anbieter schreiben?

Die meisten Entwickler müssen nicht ihren eigenen Anbieter schreiben. Microsoft bietet verschiedene Anbieter. Jedes Mal, wenn Sie eine Datenverbindung erstellen (z. B. beim Hinzufügen eines Consumers zu Ihrem Projekt die **ATL-OLE DB-Consumer-Assistenten**), wird die **Datenlinkeigenschaften** Dialogfeld listet alle verfügbaren Anbieter auf Ihrem System registriert. Wenn einer der Anbieter für die Access-Anwendung für Ihre eigenen Daten speichern und Daten geeignet ist, ist die einfachste Möglichkeit die Verwendung eines der folgenden. Wenn Sie Ihren Datenspeicher mit einer dieser Kategorien passt, müssen Sie jedoch einen eigenen Anbieter erstellen. Weitere Informationen zum Erstellen von Anbietern, finden Sie unter [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md).

## <a name="what-level-of-support-do-you-need-for-your-consumer"></a>Welche Ebene der Unterstützung benötigen Sie für Ihre Consumer?

Einige Kunden können "basic" sein; während andere komplexe sein können. Die Funktionalität des OLE DB-Objekte wird durch die Eigenschaften angegeben. Bei Verwendung der **ATL-OLE DB-Consumer-Assistenten** Erstellen eines Consumers oder **-Datenbank-Anbieter-Assistent** um einen Anbieter zu erstellen, wird für Sie einen Standardsatz von erteilen, können Sie die entsprechenden Objekteigenschaften Funktionen. Wenn jedoch die-Assistenten generierte Klassen Consumer- oder Anbietersteuerelement alles, was nicht unterstützen Sie diese benötigen für Sie tun, Sie müssen zum Verweisen auf die Schnittstellen für diese Klassen werden im der [OLE DB-Vorlagenbibliothek](../../data/oledb/ole-db-templates.md). Diese Schnittstellen umschließen die unformatierten OLE DB-Schnittstellen, eine zusätzliche Implementierung erleichtert ihre Verwendung für Sie.

Z. B. Wenn Sie Daten in einem Rowset aktualisiert werden soll, aber Sie haben vergessen, dies anzugeben, bei der Erstellung des Consumers mit dem Assistenten, können Sie angeben die Funktionalität nach dem Fakt durch Festlegen der `DBPROP_IRowsetChange` und `DBPROP_UPDATABILITY` Eigenschaften für das Command-Objekt. Klicken Sie dann, wenn das Rowset erstellt wurde, haben sie die `IRowsetChange` Schnittstelle.

## <a name="do-you-have-older-code-using-another-data-access-technology-ado-odbc-or-dao"></a>Haben Sie älteren Code mit einem anderen datenzugriffstechnologie (ADO, ODBC oder DAO)?

Angesichts der möglichen Kombinationen von Technologien (z. B. Verwenden von ADO-Komponenten mit OLE DB-Komponenten, und Migrieren von ODBC-Code zu OLE DB), ist würde den Rahmen der Visual C++-Dokumentation in allen Situationen abdecken. Es gibt jedoch zahlreiche Artikel, die für verschiedene Szenarien auf den folgenden Microsoft-Websites zur Verfügung:

- [Microsoft-Hilfe und -Support](https://support.microsoft.com/)

- [Microsoft Data Access – technische Artikel (Übersicht)](https://msdn.microsoft.com/library/ms810811.aspx)

## <a name="see-also"></a>Siehe auch

[OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)<br/>
[Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)
