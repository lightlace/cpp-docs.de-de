---
title: "CDynamicParameterAccessor::GetParamString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor.GetParamString"
  - "GetParamString"
  - "CDynamicParameterAccessor::GetParamString"
  - "ATL.CDynamicParameterAccessor.GetParamString"
  - "ATL::CDynamicParameterAccessor::GetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamString-Methode"
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicParameterAccessor::GetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Zeichenfolgendaten des angegebenen Parameters ab, der im Puffer gespeichert wird.  
  
## Syntax  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### Parameter  
 `nParam`  
 \[in\] die einen Parameterwert \(Offset von 1\).  Parameter 0 wird für Rückgabewerte reserviert.  In einen Parameterwert ist der Index des Parameters anhand ihrer Reihenfolge im SQL\- oder Prozeduraufruf.  Ein Beispiel finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `strOutput`  
 \[out\] die Zeichenfolgendaten der ANSI \(**CSimpleStringA**\) oder von Unicode \(**CSimpleStringW**\) des angegebenen Parameters.  Sie sollten einen Parameter des Typs `CString` übergeben, beispielsweise:  
  
 [!CODE [NVC_OLEDB_Consumer#9](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#9)]  
  
 `pBuffer`  
 \[out\] Ein Zeiger in ANSI \(**CHAR**\) oder Zeichenfolgendaten des Unicode \(**WCHAR**\) des angegebenen Parameters.  
  
 `pMaxLen`  
 \[out\] Ein Zeiger auf die Größe des Puffers gezeigt auf von `pBuffer` \(in Zeichen, einschließlich das abschließende NULL\-Zeichen\).  
  
## Hinweise  
 **true** Gibt bei Erfolg oder **false** auf Fehler.  
  
 Wenn `pBuffer` NULL ist, legt diese Methode die erforderliche Puffergröße im Arbeitsspeicher fest, auf den durch `pMaxLen` und geben **true** zurück, ohne die Daten kopieren gezeigt wird.  
  
 Diese Methode schlägt fehl, wenn der Puffer `pBuffer` nicht ausreicht, um die gesamte Zeichenfolge enthalten.  
  
 Verwenden Sie `GetParamString`, Zeichenfolgenparameterdaten aus dem Puffer abrufen.  Verwenden Sie [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md), um nonstring Parameterdaten aus dem Puffer abrufen.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)