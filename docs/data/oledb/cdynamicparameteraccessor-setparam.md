---
title: "CDynamicParameterAccessor::SetParam"
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
  - "ATL::CDynamicParameterAccessor::SetParam"
  - "ATL::CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor.SetParam"
  - "ATL.CDynamicParameterAccessor.SetParam"
  - "SetParam"
  - "CDynamicParameterAccessor:SetParam"
  - "CDynamicParameterAccessor::SetParam<ctype>"
  - "CDynamicParameterAccessor::SetParam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParam-Methode"
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::SetParam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den Parameterpuffer mit der angegebenen \(NichtZeichenfolgen\) Daten fest.  
  
## Syntax  
  
```  
  
      template < class   
      ctype >  
bool SetParam(  
   DBORDINAL nParam,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
template < class ctype >  
bool SetParam(  
   TCHAR* pParamName,  
   const ctype* pData,  
   DBSTATUS status = DBSTATUS_S_OK  
) throw( );  
```  
  
#### Parameter  
 `ctype`  
 Ein auf Vorlagen basierenden Parameter, der der Datentyp ist.  
  
 `nParam`  
 \[in\] die einen Parameterwert \(Offset von 1\).  Parameter 0 wird für Rückgabewerte reserviert.  In einen Parameterwert ist der Index des Parameters anhand ihrer Reihenfolge im SQL\- oder Prozeduraufruf.  Beispiel:  
  
 [!CODE [NVC_OLEDB_Consumer#8](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#8)]  
  
 `pParamName`  
 \[in\] Der Name des Parameters.  
  
 `pData`  
 \[in\] der Zeiger auf den Speicher, der die in den Puffer zu schreibenden Daten, enthält.  
  
 *status*  
 \[in\] Der `DBSTATUS` Spaltenstatus.  Weitere Informationen über `DBSTATUS`\-Werte, finden Sie unter [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE* DB\-Programmierreferenz, oder indem Sie für `DBSTATUS` in oledb.h.  
  
## Rückgabewert  
 **true** Gibt bei Erfolg oder **false** auf Fehler.  
  
 Verwenden Sie `SetParam`, um nonstring Parameterdaten im Puffer festzulegen.  [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) zu den festgelegten Zeichenfolgenparameterdaten im Puffer.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)