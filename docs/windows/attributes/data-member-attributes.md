---
title: Datenmemberattribute (C++-COM-) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5019503bed9dd0012d8aafc1ade4abd3107335ac
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791318"
---
# <a name="data-member-attributes"></a>Datenmemberattribute

Die folgenden Attribute gelten für Datenmember einer Klasse, Co-Klasse oder Schnittstelle.

|Attribut|Beschreibung|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|Gruppen `db_column` Attribute, die Teilnahme an `IAccessor`-basierten Bindung.|
|[db_column](db-column.md)|Bindet eine angegebene Spalte auf das Rowset an.|
|[db_command](db-command.md)|Erstellt einen OLE DB-Befehl.|
|[db_param](db-param.md)|Ordnet die angegebenen Member-Variable mit einem Eingabe- oder ausgabeadapter-Parameter und Variablen begrenzt.|
|[db_source](db-source.md)|Erstellt eine Verbindung mit einer Datenquelle.|
|[db_table](db-table.md)|Öffnet eine OLE DB-Tabelle.|
|[defaultbind](defaultbind.md)|Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.|
|[displaybind](displaybind.md)|Gibt eine Eigenschaft, die dem Benutzer als bindungsfähig angezeigt werden soll.|
|[ID](id.md)|Gibt eine DISPID für eine Memberfunktion (eine Eigenschaft oder eine Methode, in eine Schnittstelle oder Disp-Schnittstelle).|
|[range](range-cpp.md)|Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.|
|[rdx](rdx.md)|Erstellt einen Registrierungsschlüssel oder ändert einen vorhandenen Registrierungsschlüssel.|
|[readonly](readonly-cpp.md)|Verhindert die Zuweisung zu einem Datenelement|
|[requestedit](requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die `OnRequestEdit` Benachrichtigung.|

## <a name="see-also"></a>Siehe auch

[Attribute nach Verwendung](attributes-by-usage.md)