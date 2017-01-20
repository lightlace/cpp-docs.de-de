---
title: "SET_PARAM_TYPE"
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
  - "SET_PARAM_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SET_PARAM_TYPE-Makro"
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# SET_PARAM_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt `COLUMN_ENTRY`\-Makros an, die der `SET_PARAM_TYPE`\-Makroeingabe\-, \-ausgabe\- oder \-ein\-\/\-ausgabe folgen.  
  
## Syntax  
  
```  
  
SET_PARAM_TYPE(  
type  
 )  
  
```  
  
#### Parameter  
 `type`  
 \[in\] Der für den Parameter festzulegende Typ.  
  
## Hinweise  
 Anbieter unterstützen nur Parametereingabe\-\/\-ausgabetypen, die von der zugrunde liegenden Datenquelle unterstützt werden. Der Typ ist eine Kombination aus einem oder mehreren **DBPARAMIO**\-Werten \(siehe [DBBINDING\-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE DB\-Programmierreferenz*\):  
  
-   **DBPARAMIO\_NOTPARAM** Der Accessor hat keine Parameter. In der Regel legen Sie **eParamIO** auf diesen Wert in Zeilenaccessoren fest, um den Benutzer daran zu erinnern, dass Parameter ignoriert werden.  
  
-   **DBPARAMIO\_INPUT** Ein Eingabeparameter.  
  
-   **DBPARAMIO\_OUTPUT** Ein Ausgabeparameter.  
  
-   **DBPARAMIO\_INPUT &#124; DBPARAMIO\_OUTPUT** Der Parameter ist sowohl Eingabe\- als auch Ausgabeparameter.  
  
## Beispiel  
 [!CODE [NVC_OLEDB_Consumer#18](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#18)]  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)