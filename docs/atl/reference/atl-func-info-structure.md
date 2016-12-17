---
title: "_ATL_FUNC_INFO Structure"
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
  - "_ATL_FUNC_INFO"
  - "ATL::_ATL_FUNC_INFO"
  - "ATL._ATL_FUNC_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_FUNC_INFO structure"
  - "ATL_FUNC_INFO structure"
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_FUNC_INFO Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enthält die Informationen, die verwendet werden, um eine Methode oder eine Eigenschaft für eine Dispatchschnittstelle zu beschreiben.  
  
## Syntax  
  
```  
  
      struct _ATL_FUNC_INFO{  
   CALLCONV cc;  
   VARTYPE vtReturn;  
   SHORT nParams;  
   VARTYPE pVarTypes[_ATL_MAX_VARTYPES];  
};  
```  
  
## Mitglieder  
 **cc**  
 Die Aufrufkonvention.  Bei dieser Struktur mit der [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)\-Klasse verwendet, muss dieser Member **CC\_STDCALL** sein.  `CC_CDECL` ist die einzige Option, die in Windows CE für das `CALLCONV` Feld der `_ATL_FUNC_INFO`\-Struktur unterstützt wird.  Jeder andere Wert somit sein Definition nicht definiertes Verhalten nicht unterstützt.  
  
 **vtReturn**  
 Der Varianttyp des Funktionsrückgabewerts.  
  
 **nParams**  
 Die Anzahl von Funktionsparametern.  
  
 **pVarTypes**  
 Ein Array variante Typen der Funktionsparameter.  
  
## Hinweise  
 Intern verwendet ATL diese Struktur, um Informationen zum Speichern von abgerufenen einer Typbibliothek.  Eventuell müssen Sie diese Struktur direkt bearbeiten, wenn Sie Typinformationen für einen Ereignishandler bereitgestellt, der mit der [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)\-Klasse und DEM [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md)\-Makro verwendet wird.  
  
## Beispiel  
 Eine dispinterface\-Methode angegeben in IDL definiert:  
  
 [!CODE [NVC_ATL_Windowing#139](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#139)]  
  
 Sie können eine `_ATL_FUNC_INFO`\-Struktur definieren:  
  
 [!CODE [NVC_ATL_Windowing#140](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#140)]  
  
## Anforderungen  
 **Header:** möchten  
  
## Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)