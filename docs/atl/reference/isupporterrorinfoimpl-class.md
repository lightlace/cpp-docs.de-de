---
title: "ISupportErrorInfoImpl Class"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::ISupportErrorInfoImpl<piid>"
  - "ATL::ISupportErrorInfoImpl"
  - "ISupportErrorInfoImpl"
  - "ATL.ISupportErrorInfoImpl<piid>"
  - "ATL.ISupportErrorInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error information, ATL"
  - "ISupportErrorInfo ATL implementation"
  - "ISupportErrorInfoImpl class"
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# ISupportErrorInfoImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Standardimplementierung [ISupportErrorInfo Interface](assetId:///42d33066-36b4-4a5b-aa5d-46682e560f32) und kann verwendet werden, wenn nur eine einzelne Schnittstelle Fehler auf einem Objekt generiert.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template<  
const IID* piid   
>  
class ATL_NO_VTABLE ISupportErrorInfoImpl :  
public ISupportErrorInfo  
```  
  
#### Parameter  
 `piid`  
 Ein Zeiger auf IID einer Schnittstelle, die [IErrorInfo](assetId:///4dda6909-2d9a-4727-ae0c-b5f90dcfa447) unterstützt.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](../Topic/ISupportErrorInfoImpl::InterfaceSupportsErrorInfo.md)|Gibt an, ob die Schnittstelle, die von `riid` identifiziert wird, die [IErrorInfo](assetId:///4dda6909-2d9a-4727-ae0c-b5f90dcfa447)\-Schnittstelle unterstützt.|  
  
## Hinweise  
 [ISupportErrorInfo Interface](assetId:///42d33066-36b4-4a5b-aa5d-46682e560f32) wird sichergestellt, dass Fehlerinformationen an den Client zurückgegeben werden können.  Objekte, die **IErrorInfo** verwenden, müssen **ISupportErrorInfo** implementieren.  
  
 \- Klasse `ISupportErrorInfoImpl` stellt eine Standardimplementierung von **ISupportErrorInfo** und kann verwendet werden, wenn nur eine einzelne Schnittstelle Fehler auf einem Objekt generiert.  Beispiel:  
  
 [!CODE [NVC_ATL_COM#48](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#48)]  
  
## Vererbungshierarchie  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)