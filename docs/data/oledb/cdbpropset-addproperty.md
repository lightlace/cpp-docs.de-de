---
title: "CDBPropSet::AddProperty"
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
  - "CDBPropSet::AddProperty"
  - "CDBPropSet.AddProperty"
  - "AddProperty"
  - "ATL::CDBPropSet::AddProperty"
  - "ATL.CDBPropSet.AddProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty-Methode"
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet::AddProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt einer Eigenschaft dem Eigenschaftensatz hinzu.  
  
## Syntax  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### Parameter  
 *dwPropertyID*  
 \[in\] Die ID der hinzuzufügenden Eigenschaft.  Wird verwendet, um die **dwPropertyID** der Struktur `DBPROP` initialisiert hat z Eigenschaft hinzu.  
  
 `var`  
 \[in\] hat a\-Variante, die verwendet wurde, um den Eigenschaftswert für die `DBPROP`\-Struktur zu initialisieren, der Eigenschaft hinzu.  
  
 `szValue`  
 \[in\] hat a\-Zeichenfolge, die verwendet wurde, um den Eigenschaftswert für die `DBPROP`\-Struktur zu initialisieren, der Eigenschaft hinzu.  
  
 `bValue`  
 \[in\] hat A **BYTE** oder boolean\-Wert, die verwendet wurden, um den Eigenschaftswert für die `DBPROP`\-Struktur zu initialisieren, der Eigenschaft hinzu.  
  
 `nValue`  
 \[in\] wurde ein ganzzahliger Wert, der verwendet wurde, um den Eigenschaftswert für die `DBPROP`\-Struktur zu initialisieren, der Eigenschaft hinzu.  
  
 *fltValue*  
 \[in\] hat a\-Gleitkommawert, der verwendet wurde, um den Eigenschaftswert für die `DBPROP`\-Struktur zu initialisieren, der Eigenschaft hinzu.  
  
 `dblValue`  
 \[in\] hat a\-Gleitkommawertmit doppelter Genauigkeit, der verwendet wurde, um den Eigenschaftswert für die `DBPROP`\-Struktur zu initialisieren, der Eigenschaft hinzu.  
  
 `cyValue`  
 \[in\] hat Ein CY\-Währungswert, der verwendet wurde, um den Eigenschaftswert für die `DBPROP`\-Struktur zu initialisieren, der Eigenschaft hinzu.  
  
## Rückgabewert  
 **true**, wenn die Eigenschaft hinzugefügt wurde.  Andernfalls **false**.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDBPropSet\-Klasse](../../data/oledb/cdbpropset-class.md)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)