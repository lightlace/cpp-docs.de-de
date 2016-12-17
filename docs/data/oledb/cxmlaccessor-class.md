---
title: "CXMLAccessor-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL::CXMLAccessor"
  - "CXMLAccessor"
  - "ATL.CXMLAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CXMLAccessor-Klasse"
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CXMLAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht Sie zu den Zugriffsdatenquellen als Zeichenfolgendaten, wenn Sie das Schema des Datenspeichers nicht haben \(die zugrunde liegende Struktur\).  
  
## Syntax  
  
```  
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|Ruft die Spalteninformationen ab.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|Ruft den gesamten Inhalt einer Tabelle mit Zeilen ab.|  
  
## Hinweise  
 `CXMLAccessor` unterscheidet sich jedoch dadurch von `CDynamicStringAccessorW`, dass es alle Daten konvertiert, die vom Datenspeicher als \(markiert\) zugegriffen werden Daten im XML\-Format.  Dies ist für die Ausgabe an XML\-bewussten Webseiten besonders nützlich.  Die gleichen XML\-Tagnamen die Spaltennamen des Datenspeichers angestrebt ab, wie möglich.  
  
 Verwenden Sie `CDynamicAccessor`\-Methoden, um Spalteninformationen zu beziehen.  Sie verwenden diese Spalteninformationen, um einen Accessor zur Laufzeit dynamisch zu erstellen.  
  
 Die Spalteninformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird.  Bringt Spalteninformationen mit [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) ein oder abgerufen Sie Spaltendaten durch Zeilen mithilfe [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md).  
  
## Beispiel  
 [!CODE [NVC_OLEDB_Consumer#14](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#14)]  
  
## Anforderungen  
 **Header**: atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor\-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor\-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA\-Klasse](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW\-Klasse](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)