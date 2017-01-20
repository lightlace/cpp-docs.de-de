---
title: "CDynamicStringAccessor-Klasse"
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
  - "CDynamicStringAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessor-Klasse"
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht Ihnen, auf eine Datenquelle zuzugreifen, wenn Ihnen das Datenbankschema \(die zugrunde liegende Struktur\).  
  
## Syntax  
  
```  
  
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|Ruft die angegebenen Spaltendaten als Zeichenfolge ab.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|Legt die angegebenen Spaltendaten als Zeichenfolge fest.|  
  
## Hinweise  
 Während [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Daten im systemeigenen Format anfordert, fordert vom Anbieter angegeben, `CDynamicStringAccessor` Anforderungen, dass auf der Anbieterabruf, den alle Daten vom Datenspeicher als Zeichenfolgendaten abruft.  Dies ist besonders hilfreich für einfache Aufgaben, die keine Berechnungen von Werten im Datenspeicher erfordern, z. B. das Anzeigen oder Drucken des Datenspeicherinhalts.  
  
 Der systemeigene Typ der Spaltendaten im Datenspeicher ist nicht wichtig; sofern der Anbieter die Datenkonvertierung unterstützen kann, stellt er die Daten im Zeichenfolgenformat.  Wenn der Anbieter nicht die Konvertierung vom systemeigenen Datentyp in einer Zeichenfolge \(unterstützt die nicht häufig ist\), wird der Aufruf das anfordernde Erfolgswert **DB\_S\_ERRORSOCCURED** zurück, und der Status für die entsprechende Spalte gibt einem Konvertierungsproblem mit **DBSTATUS\_E\_CANTCONVERTVALUE** an.  
  
 Verwenden Sie `CDynamicStringAccessor`\-Methoden, um Spalteninformationen zu beziehen.  Sie verwenden diese Spalteninformationen, um einen Accessor zur Laufzeit dynamisch zu erstellen.  
  
 Die Spalteninformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird.  Rufen Sie Daten aus dem Puffer mithilfe von [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md) ab, oder speichern Sie diesen dem Puffer mithilfe von [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
 Erläuterungen und Beispiele der dynamischen Accessorklassen, finden Sie unter [Verwenden von dynamischen Accessoren](../../data/oledb/using-dynamic-accessors.md).  
  
## Anforderungen  
 **Header**: atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor\-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA\-Klasse](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW\-Klasse](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor\-Klasse](../../data/oledb/cxmlaccessor-class.md)