---
title: "CDynamicAccessor-Klasse"
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
  - "ATL.CDynamicAccessor"
  - "ATL::CDynamicAccessor"
  - "CDynamicAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicAccessor-Klasse"
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht Ihnen, auf eine Datenquelle zuzugreifen, wenn Ihnen das Datenbankschema \(die zugrunde liegende Struktur\).  
  
## Syntax  
  
```  
class CDynamicAccessor : public CAccessorBase  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|Fügt einem Bindungseintrag den Ausgabespalten hinzu, wenn, den Standardaccessor Überschreiben.|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|Instanziiert und initialisiert das `CDynamicAccessor`\-Objekt.|  
|[Schließen](../../data/oledb/cdynamicaccessor-close.md)|Befreit alle Spalten, gibt den reservierten Speicher frei und gibt die [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) von Schnittstellenzeigern in der Klasse frei.|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|Ruft das Lesezeichen für die aktuelle Zeile ab.|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|Ruft den BLOBbehandlungswert für die aktuelle Zeile ab.|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|Ruft die maximale BLOBgröße in Bytes ab.|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|Ruft die Anzahl der Spalten im Rowset ab.|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|Ruft die Spalteneigenschaften ab.|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|Ruft die Spaltenmetadaten ab.|  
|[GetColumnName](../../data/oledb/cdynamicaccessor-getcolumnname.md)|Ruft den Namen einer bestimmten Spalte ab.|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|Ruft den Datentyp einer bestimmten Spalte ab.|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|Ruft die maximale beliebige Länge einer Spalte in Bytes ab.|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|Ruft den Spaltenindex ab, der einen Spaltennamen zugewiesen wird.|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|Ruft den Status einer bestimmten Spalte ab.|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|Ruft die Daten aus dem Puffer ab.|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|Legt den BLOBbehandlungswert für die aktuelle Zeile fest.|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|Legt die maximale BLOBgröße in Bytes fest.|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|Gibt die Länge der Spalte in Bytes fest.|  
|[SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)|Legt den Status einer bestimmten Spalte fest.|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|Speichert die Daten in den Puffer.|  
  
## Hinweise  
 Verwenden Sie `CDynamicAccessor`\-Methoden, um Spalteninformationen wie Spaltennamen, Spaltenanzahl, Datentyp usw. abzurufen.  Sie verwenden diese Spalteninformationen, um einen Accessor zur Laufzeit dynamisch zu erstellen.  
  
 Die Spalteninformation wird in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird.  Rufen Sie Daten aus dem Puffer mithilfe von [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
 Erläuterungen und Beispiele der dynamischen Accessorklassen, finden Sie unter [Verwenden von dynamischen Accessoren](../../data/oledb/using-dynamic-accessors.md).  
  
## Anforderungen  
 **Header**: atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor\-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)