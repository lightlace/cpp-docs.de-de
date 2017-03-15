---
title: "Implements-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Implements-Struktur"
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implements-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implementiert QueryInterface und GetIid für die angegebenen Schnittstellen.  
  
## Syntax  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;  
template <  
   int flags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;  
```  
  
#### Parameter  
 `I0`  
 Die nullte Schnittstellen\-ID. \(Erforderlich\)  
  
 `I1`  
 Die erste Schnittstellen\-ID. \(Optional\)  
  
 `I2`  
 Die zweite Schnittstellen\-ID. \(Optional\)  
  
 `I3`  
 Die dritte Schnittstellen\-ID. \(Optional\)  
  
 `I4`  
 Die vierte Schnittstellen\-ID. \(Optional\)  
  
 `I5`  
 Die fünfte Schnittstellen\-ID. \(Optional\)  
  
 `I6`  
 Die sechste Schnittstellen\-ID. \(Optional\)  
  
 `I7`  
 Die siebte Schnittstellen\-ID. \(Optional\)  
  
 `I8`  
 Die achte Schnittstellen\-ID. \(Optional\)  
  
 `I9`  
 Die neunte Schnittstellen\-ID. \(Optional\)  
  
 `flags`  
 Konfigurationsflags für die Klasse.  Eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)\-Enumerationen, die Struktur in einer [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) angegeben werden.  
  
## Hinweise  
 Ist von der Liste der angegebenen Schnittstellen und implementiert Hilfevorlagen für QueryInterface und GetIid.  
  
 Jedes `I0` durch `I9`\-Schnittstellenparameter muss von IUnknown, IInspectable oder der Vorlage entweder [ChainInterfaces](../windows/chaininterfaces-structure.md) ableiten.  Der Parameter `flags` bestimmt, ob Unterstützung für IUnknown oder IInspectable generiert wird.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`ClassFlags`|Ein Synonym für `RuntimeClassFlags<WinRt>`.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Implements::CanCastTo\-Methode](../windows/implements-cancastto-method.md)|Ruft einen Zeiger auf die angegebene Schnittstelle.|  
|[Implements::CastToUnknown\-Methode](../windows/implements-casttounknown-method.md)|Ruft einen Zeiger zur zugrunde liegenden IUnknown\-Schnittstelle.|  
|[Implements::FillArrayWithIid\-Methode](../windows/implements-fillarraywithiid-method.md)|Fügt die Schnittstellen\-ID ein, die durch den aktuellen zeroth Vorlagenparameter in das angegebene Arrayelement angegeben wird.|  
  
### Geschützte Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Implements::IidCount\-Konstante](../windows/implements-iidcount-constant.md)|Hält die Anzahl von implementierten Schnittstellen\-IDs an.|  
  
## Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `ImplementsBase`  
  
 `ImplementsHelper`  
  
 `Implements`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)