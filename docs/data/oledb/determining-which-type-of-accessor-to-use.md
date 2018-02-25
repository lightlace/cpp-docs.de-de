---
title: Bestimmen des geeigneten Accessortyps | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 28173b18e1f2ab6e7c916679d5fa5a27c08caaeb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="determining-which-type-of-accessor-to-use"></a>Bestimmen des geeigneten Zugriffsmethodentyps
Sie können die Datentypen für ein Rowset zur Kompilierzeit oder zur Laufzeit bestimmen.  
  
 Wenn Sie Datentypen, die zum Zeitpunkt der Kompilierung zu ermitteln, verwenden Sie einen statischen Accessor (z. B. `CAccessor`). Sie können die Datentypen manuell oder mithilfe der ATL-OLE DB-Consumer-Assistenten bestimmen.  
  
 Wenn Sie die Datentypen zur Laufzeit bestimmen müssen, verwenden Sie eine dynamische (`CDynamicAccessor` oder seinen untergeordneten Elementen) oder einen manuellen Accessor (`CManualAccessor`). Sie können in diesen Fällen Aufrufen `GetColumnInfo` für das Rowset die Spalteninformationen für die Bindung, zurückgeben, dort können Sie Typen bestimmen.  
  
 Die folgende Tabelle enthält die Typen von Accessoren in die Consumervorlagen bereitgestellt. Jeder Accessor hat vor- und Nachteile. Abhängig von Ihrer Situation sollte eine Accessortyp Ihre Bedürfnisse erfüllen.  
  
|Accessorklasse|Bindung|Parameter|Kommentar|  
|--------------------|-------------|---------------|-------------|  
|`CAccessor`|Erstellen Sie einen Benutzerdatensatz mit `COLUMN_ENTRY` Makros. Die Makros binden einen Datenmember in diesem Datensatz für den Accessor. Wenn das Rowset erstellt wird, können keine Spalten ungebunden sein.|Ja, mithilfe einer **PARAM_MAP** Makro-Eintrag. Nach der Bindung können keine Parameter aufgehoben werden.|Am schnellsten Zugriffsmethode aufgrund von wenig Code.|  
|`CDynamicAccessor`|Automatisch.|Nein.|Nützlich, wenn Sie nicht, dass den Typ der Daten in einem Rowset wissen.|  
|`CDynamicParameterAccessor`|Automatisch, kann jedoch [überschreiben](../../data/oledb/overriding-a-dynamic-accessor.md).|Ja, wenn der Anbieter unterstützt `ICommandWithParameters`. Parameter, die automatisch eingebunden.|Langsamer als `CDynamicAccessor` jedoch zum Aufrufen der generischen gespeicherter Prozeduren hilfreich.|  
|**CDynamicStringAccessor [A, W]**|Automatisch.|Nein.|Ruft Daten aus dem Datenspeicher als Zeichenfolgedaten zugegriffen.|  
|`CManualAccessor`|Manuelle mit `AddBindEntry`.|Manuell über `AddParameterEntry`.|Sehr schnell; Parameter und Spalten werden nur einmal gebunden. Sie bestimmen den Typ des zu verwendenden Daten. (Siehe [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) ein Beispiel für.) Erfordert mehr Code als `CDynamicAccessor` oder `CAccessor`. Es ist eher wie OLE DB direkt aufrufen.|  
|`CXMLAccessor`|Automatisch.|Nein.|Ruft Daten aus dem Datenspeicher als Zeichenfolgedaten zugegriffen ab und formatiert diese Daten als XML-Tags.|  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)