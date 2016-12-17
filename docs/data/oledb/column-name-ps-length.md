---
title: "COLUMN_NAME_PS_LENGTH"
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
  - "COLUMN_NAME_PS_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_PS_LENGTH-Makro"
ms.assetid: 415a154b-cb7c-4072-9e7d-8cfa32a15d6e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_NAME_PS_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Bindung im Rowset zur jeweiligen Spalte im Rowset dar.  Wie auch [COLUMN\_NAME](../../data/oledb/column-name.md), außer dass zu diesem Makro nimmt außerdem Genauigkeit, Dezimalstellen und Spaltenlänge.  
  
## Syntax  
  
```  
  
COLUMN_NAME_PS_LENGTH(  
pszName  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length )  
```  
  
#### Parameter  
 `pszName`  
 \[in\] Ein Zeiger auf den Spaltennamen.  Der Name muss eine Unicode\-Zeichenfolge sein.  Sie können dies bewerkstelligen, indem Sie "L" vor dem Namen, zum Beispiel einfügen: `L"MyColumn"`.  
  
 `nPrecision`  
 \[in\] Die maximale Genauigkeit der Spalte, die Sie binden möchten.  
  
 `nScale`  
 \[in\] die Skalierung der Spalte, die Sie binden möchten.  
  
 `data`  
 \[in\] der entsprechenden Datenmember im Benutzerdatensatz.  
  
 *length*  
 \[in\] die Spaltenlänge gebunden werden Variablen.  
  
## Hinweise  
 Siehe [COLUMN\_NAME](../../data/oledb/column-name.md) Informationen zu, der die **COLUMN\_NAME\_\***\-Makros verwendet werden.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_NAME](../../data/oledb/column-name.md)   
 [COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)