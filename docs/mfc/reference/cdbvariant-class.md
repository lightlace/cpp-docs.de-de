---
title: "CDBVariant Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CDBVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBVariant-Klasse"
  - "Variant-Datentypen, ODBC"
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CDBVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen varianten Datentyp für die MFC\-ODBC\-Klassen dar.  
  
## Syntax  
  
```  
class CDBVariant  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](../Topic/CDBVariant::CDBVariant.md)|Erstellt ein `CDBVariant`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDBVariant::Clear](../Topic/CDBVariant::Clear.md)|Löscht das `CDBVariant`\-Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDBVariant::m\_dwType](../Topic/CDBVariant::m_dwType.md)|Enthält den Datentyp des derzeit gespeicherten Werts.  Geben Sie `DWORD` ein.|  
  
### Öffentliche Unionmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDBVariant::m\_boolVal](../Topic/CDBVariant::m_boolVal.md)|Enthält einen Wert des Typs **BOOL**.|  
|[CDBVariant::m\_chVal](../Topic/CDBVariant::m_chVal.md)|Enthält einen Wert des Typs `unsigned char`.|  
|[CDBVariant::m\_dblVal](../Topic/CDBVariant::m_dblVal.md)|Enthält einen Wert des Typs **double**.|  
|[CDBVariant::m\_fltVal](../Topic/CDBVariant::m_fltVal.md)|Enthält einen Wert des Typs **float**.|  
|[CDBVariant::m\_iVal](../Topic/CDBVariant::m_iVal.md)|Enthält einen Wert des Typs **short**.|  
|[CDBVariant::m\_lVal](../Topic/CDBVariant::m_lVal.md)|Enthält einen Wert des Typs **long**.|  
|[CDBVariant::m\_pbinary](../Topic/CDBVariant::m_pbinary.md)|Enthält einen Zeiger auf ein Objekt des Typs `CLongBinary`.|  
|[CDBVariant::m\_pdate](../Topic/CDBVariant::m_pdate.md)|Enthält einen Zeiger auf ein Objekt des Typs **TIMESTAMP\_STRUCT**.|  
|[CDBVariant::m\_pstring](../Topic/CDBVariant::m_pstring.md)|Enthält einen Zeiger auf ein Objekt des Typs `CString`.|  
|[CDBVariant::m\_pstringA](../Topic/CDBVariant::m_pstringA.md)|Speichert einen Zeiger auf ein Objekt ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md).|  
|[CDBVariant::m\_pstringW](../Topic/CDBVariant::m_pstringW.md)|Speichert einen Zeiger auf einen großen [CString](../../atl-mfc-shared/reference/cstringt-class.md)\-Objekt.|  
  
## Hinweise  
 `CDBVariant` hat keine Basisklasse.  
  
 `CDBVariant` ist zu [COleVariant](../../mfc/reference/colevariant-class.md) ähnlich; verwendet jedoch nicht `CDBVariant` OLE.  `CDBVariant` ermöglicht es Ihnen, einen Wert zu speichern, ohne den Datentyp des Werts verloren gehen.  `CDBVariant` verfolgt den Datentyp des aktuellen Werts, der in einer Union gespeichert wird.  
  
 \- Klasse [CRecordset](../../mfc/reference/crecordset-class.md) verwendet `CDBVariant`\-Objekte in den dreiköpfigen Funktionen: `GetFieldValue`, `GetBookmark` und `SetBookmark`.  Beispielsweise können Sie `GetFieldValue` dynamisch zu den abgerufen werden in einer Spalte.  Da der Datentyp der Spalte möglicherweise nicht zur Laufzeit bekannt ist, verwendet `GetFieldValue` ein `CDBVariant`\-Objekt, um die Daten der Spalte zu speichern.  
  
## Vererbungshierarchie  
 `CDBVariant`  
  
## Anforderungen  
 **Header:**  afxdb.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)   
 [CRecordset::GetBookmark](../Topic/CRecordset::GetBookmark.md)   
 [CRecordset::SetBookmark](../Topic/CRecordset::SetBookmark.md)