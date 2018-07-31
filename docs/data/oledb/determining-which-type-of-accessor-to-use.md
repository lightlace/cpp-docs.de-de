---
title: Bestimmen des geeigneten Zugriffsmethodentyps | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f21a4545bb24b0a4a9e19efa2a6ff9738272cc9f
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340442"
---
# <a name="determining-which-type-of-accessor-to-use"></a>Bestimmen des geeigneten Zugriffsmethodentyps
Sie können die Datentypen für ein Rowset zum Zeitpunkt der Kompilierung oder zur Laufzeit bestimmen.  
  
 Wenn Sie Datentypen zum Zeitpunkt der Kompilierung ermitteln müssen, verwenden Sie einen statischen Accessor (z. B. `CAccessor`). Sie können die Datentypen manuell oder mithilfe der ATL-OLE DB-Consumer-Assistent bestimmen.  
  
 Wenn Sie die Datentypen zur Laufzeit bestimmen müssen, verwenden Sie eine dynamische (`CDynamicAccessor` oder seine untergeordneten Elemente) oder einen manuellen Accessor (`CManualAccessor`). Sie können in diesen Fällen Aufrufen `GetColumnInfo` für das Rowset die Spalteninformationen für die Bindung, zurückgeben, von dem Sie können Typen bestimmen.  
  
 Die folgende Tabelle enthält die Typen der Accessoren in die Consumervorlagen bereitgestellt. Jeder Accessor hat vor- und Nachteile. Je nach Situation sollte eine Accessortyp Ihre Bedürfnisse erfüllen.  
  
|Accessor-Klasse|Bindung|Parameter|Kommentar|  
|--------------------|-------------|---------------|-------------|  
|`CAccessor`|Erstellen Sie einen Benutzerdatensatz mit COLUMN_ENTRY-Makros. Die Makros, die einen Datenmember in diesen Datensatz binden, auf den Accessor verwendet wird. Wenn das Rowset erstellt wird, können keine Spalten aufgehoben werden.|Ja, mit der eine PARAM_MAP Makro-Eintrag. Nach der Bindung können nicht Parametern aufgehoben werden.|Am schnellsten Zugriffsmethode aufgrund von wenig Code.|  
|`CDynamicAccessor`|Automatisch.|Nein.|Nützlich, wenn Sie nicht, dass den Typ der Daten in einem Rowset wissen.|  
|`CDynamicParameterAccessor`|Automatische, kann jedoch [überschreiben](../../data/oledb/overriding-a-dynamic-accessor.md).|Ja, wenn der Anbieter unterstützt `ICommandWithParameters`. Parameter, die automatisch eingebunden werden.|Langsamer als `CDynamicAccessor` aber hilfreich zum Aufrufen der generischer gespeicherter Prozeduren.|  
|`CDynamicStringAccessor[A,W]`|Automatisch.|Nein.|Ruft Daten aus dem Datenspeicher als Zeichenfolgendaten ab.|  
|`CManualAccessor`|Mithilfe von manuellen `AddBindEntry`.|Manuell über `AddParameterEntry`.|Sehr schnell; Parameter und Spalten werden nur einmal gebunden. Sie bestimmen den Typ des zu verwendenden Daten. (Finden Sie unter [DBVIEWER](http://msdn.microsoft.com/07620f99-c347-4d09-9ebc-2459e8049832) ein Beispiel für.) Benötigt mehr Code als `CDynamicAccessor` oder `CAccessor`. Es ist eher wie OLE DB nicht direkt aufrufen.|  
|`CXMLAccessor`|Automatisch.|Nein.|Ruft Daten aus dem Datenspeicher als Zeichenfolgedaten zugegriffen, und formatiert die Ausgabe als XML-Tags Daten.|  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)