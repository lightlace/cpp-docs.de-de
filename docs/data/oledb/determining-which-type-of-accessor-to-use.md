---
title: "Bestimmen des geeigneten Accessortyps | Microsoft Docs"
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
  - "Accessoren [C++], Typen"
  - "Rowsets [C++], Datentypen"
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Bestimmen des geeigneten Accessortyps
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es ist möglich, die Datentypen eines Rowsets zur Kompilierungs\- oder zur Laufzeit zu bestimmen.  
  
 Wenn Sie die Datentypen zur Kompilierungszeit bestimmen müssen, verwenden Sie hierfür einen statischen Accessor \(z. B. `CAccessor`\).  Sie können die Datentypen manuell oder mithilfe des ATL\-OLE DB\-Consumer\-Assistenten bestimmen.  
  
 Wenn Sie die Datentypen zur Laufzeit bestimmen müssen, verwenden Sie hierfür einen dynamischen Accessor \(`CDynamicAccessor` oder einen untergeordneten Accessor\) oder einen manuellen Accessor \(`CManualAccessor`\).  In diesen Fällen können Sie für das Rowset `GetColumnInfo` aufrufen, damit Informationen zur Spaltenbindung zurückgegeben werden, anhand derer Sie Typen bestimmen können.  
  
 In der folgenden Tabelle sind die Accessortypen der Consumervorlagen aufgeführt.  Jeder Accessor besitzt Vor\- und Nachteile.  Je nach Situation sollte jedoch einer der Accessortypen Ihren Bedürfnissen gerecht werden.  
  
|Accessorklassen|Bindung|Parameter|Kommentar|  
|---------------------|-------------|---------------|---------------|  
|`CAccessor`|Erstellt einen Benutzerdatensatz mit `COLUMN_ENTRY`\-Makros.  Die Makros binden ein Datenmember in diesem Datensatz an den Accessor.  Wenn das Rowset erstellt ist, kann die Bindung von Spalten nicht mehr aufgehoben werden.|Ja, mithilfe eines **PARAM\_MAP**\-Makroeintrags.  Nach erfolgter Bindung kann die Bindung von Parametern nicht wieder aufgehoben werden.|Schnellster Accessor, da nur eine geringe Codemenge verwendet wird.|  
|`CDynamicAccessor`|Automatisch.|Anzahl|Sinnvoll, wenn der Datentyp in einem Rowset unbekannt ist.|  
|`CDynamicParameterAccessor`|Automatisch, kann jedoch [überschrieben](../../data/oledb/overriding-a-dynamic-accessor.md) werden.|Ja, wenn der Anbieter `ICommandWithParameters` unterstützt.  Parameterbindung erfolgt automatisch.|Langsamer als `CDynamicAccessor`, aber geeignet zum Aufrufen generischer gespeicherter Prozeduren.|  
|**CDynamicStringAccessor\[A,W\]**|Automatisch.|Anzahl|Ruft Daten, auf die vom Datenspeicher aus zugegriffen wurde, als Zeichenfolgedaten ab.|  
|`CManualAccessor`|Manuell mithilfe von `AddBindEntry`.|Manuell mithilfe von `AddParameterEntry`.|Sehr schnell; Parameter und Spalten werden nur einmal gebunden.  Sie bestimmen den zu verwendenden Datentyp. \(Ein Beispiel finden Sie unter [DBVIEWER](assetId:///07620f99-c347-4d09-9ebc-2459e8049832).\) Benötigt mehr Code als `CDynamicAccessor` und `CAccessor`.  Entspricht eher dem direkten Aufrufen von OLE DB.|  
|`CXMLAccessor`|Automatisch.|Anzahl|Ruft Daten, auf die vom Datenspeicher aus zugegriffen wurde, als Zeichenfolgedaten ab und formatiert diese als Daten mit XML\-Tags.|  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)