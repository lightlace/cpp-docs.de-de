---
title: "CDataSource-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDataSource"
  - "ATL::CDataSource"
  - "CDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataSource-Klasse"
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDataSource-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Entspricht einem OLE DB\-Datenquellenobjekt, das eine Verbindung durch einen Anbieter zu einer Datenquelle darstellt.  
  
## Syntax  
  
```  
class CDataSource  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Schließen](../../data/oledb/cdatasource-close.md)|Schließt die Verbindung.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|Ruft die Initialisierungszeichenfolge der Datenquelle ab, die gerade geöffnet ist.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|Ruft die Werte von Eigenschaften ab, die derzeit für die damit verbundene Datenquelle festgelegt werden.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|Ruft den Wert einer einzelnen Eigenschaft ab, die derzeit für die damit verbundene Datenquelle festgelegt wird.|  
|[Öffnen](../../data/oledb/cdatasource-open.md)|Erstellt eine Verbindung mit einem Anbieter \(Datenquelle\) entweder mithilfe von **CLSID**, **ProgID** oder eines `CEnumerator` Monikers, die vom Aufrufer bereitgestellt wird.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|Öffnet eine Datenquelle aus einer Datei, die von den vom Benutzer bereitgestellten Dateinamen angegeben ist.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|Öffnet die Datenquelle, die von einer festgelegten Initialisierungszeichenfolge angegeben wird.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|Ermöglicht es dem Benutzer, eine zuvor erstellte Datenverknüpfungsdatei auszuwählen, um die entsprechende Datenquelle zu öffnen.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|Öffnet ein Datenquellenobjekt mithilfe des Datenverknüpfungsdialogfelds.|  
  
## Hinweise  
 Eine oder mehrere Datenbanksitzungen können für eine einzelne Verbindung erstellt werden.  Diese Sitzungen werden durch `CSession` dargestellt.  Sie müssen [CDataSource::Open](../../data/oledb/cdatasource-open.md) aufrufen, um die Verbindung zu öffnen, bevor Sie eine Sitzung mit `CSession::Open` erstellen.  
  
 Ein Beispiel, wie `CDataSource`, finden Sie das Beispiel [CatDB](../../top/visual-cpp-samples.md) verwendet.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)