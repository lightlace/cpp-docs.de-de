---
title: "ImplementsHelper-Struktur"
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
  - "implements/Microsoft::WRL::Details::ImplementsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ImplementsHelper-Struktur"
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ImplementsHelper-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### Parameter  
 `RuntimeClassFlagsT`  
 Ein Feld von Flags, das einen oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren angibt.  
  
 `ILst`  
 Eine Liste von Schnittstellen\-IDs.  
  
 `IsDelegateToClass`  
 Geben Sie `true` an, wenn die aktuelle Instanz von Werkzeugen eine Basisklasse erste Schnittstellen\-ID in `ILst` ist; andernfalls `false`.  
  
## Hinweise  
 Hilfen implementieren die Struktur unter [Implementiert](../windows/implements-structure.md).  
  
 Diese Vorlage wird eine Liste der Schnittstellen durch und diese als Basisklassen und als Informationen hinzu, die erforderlich sind, QueryInterface zu aktivieren.  
  
## Member  
  
## Vererbungshierarchie  
 `ImplementsHelper`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Reference \(Windows Runtime Library\)](assetId:///00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)