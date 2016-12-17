---
title: "RuntimeClass-Klasse"
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
  - "implements/Microsoft::WRL::RuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClass-Klasse"
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine instanziierte Klasse dar, die die angegebene Anzahl von Schnittstellen erbt, und gewährt Unterstützung für die angegebene [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], klassisches COM und schwache Verweise.  
  
 Sie leiten die WRL\-Typen in der Regel aus der `RuntimeClass` ab, da diese Klasse `AddRef`, `Release` und `QueryInterface` implementiert und bei der Verwaltung des Gesamtverweiszählers des Moduls hilft.  
  
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
class RuntimeClass : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT, RuntimeClassFlags<WinRt>>;  
  
template <  
   unsigned int classFlags,  
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
class RuntimeClass<RuntimeClassFlags<classFlags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT, RuntimeClassFlags<classFlags> >;  
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
  
 `classFlags`  
 Eine Kombination aus einem oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)\-Enumerationswerten.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[RuntimeClass::RuntimeClass\-Konstruktor](../windows/runtimeclass-runtimeclass-constructor.md)|Initialisiert die aktuelle Instanz der RuntimeClass\-Klasse.|  
|[RuntimeClass::~RuntimeClass\-Destruktor](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der RuntimeClass\-Klasse auf.|  
  
## Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `RuntimeClass`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)