---
title: "WeakReference::SetUnknown-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::SetUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetUnknown-Methode"
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# WeakReference::SetUnknown-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `unk`  
 Ein Zeiger auf die `IUnknown` Schnittstelle für ein Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Legt die starke Referenz des aktuellen `WeakReference` Objekt, das den angegebenen Schnittstellenzeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch
[WeakReference-Klasse](../windows/weakreference-class1.md)  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)