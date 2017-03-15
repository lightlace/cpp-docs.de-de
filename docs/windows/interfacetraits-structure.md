---
title: "InterfaceTraits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceTraits-Struktur"
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
  
template<  
   typename CloakedType  
>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### Parameter  
 `I0`  
 Der Name einer Schnittstelle.  
  
 `CloakedType`  
 Für RuntimeClass, implementieren und ChainInterfaces eine Schnittstelle, die nicht in der Liste der unterstützten Schnittstellen\-IDs ist.  
  
## Hinweise  
 Implementiert allgemeine Eigenschaften einer Schnittstelle.  
  
 Die zweite Vorlage ist eine Spezialisierung verdeckte für Schnittstellen.  Die dritte Vorlage ist eine Spezialisierung für Nullparameter.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Base`|Ein Vorlagenparameter Synonym für den `I0`.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[InterfaceTraits::CanCastTo\-Methode](../windows/interfacetraits-cancastto-method.md)|Gibt an, ob der angegebene Zeiger auf Zeiger zu `Base` umgewandelt werden kann.|  
|[InterfaceTraits::CastToBase\-Methode](../windows/interfacetraits-casttobase-method.md)|Wandelt den angegebenen Zeiger auf Zeiger in `Base` um.|  
|[InterfaceTraits::CastToUnknown\-Methode](../windows/interfacetraits-casttounknown-method.md)|Wandelt den angegebenen Zeiger auf einen Zeiger auf IUnknown um.|  
|[InterfaceTraits::FillArrayWithIid\-Methode](../windows/interfacetraits-fillarraywithiid-method.md)|Weist die Schnittstellen\-ID von `Base` z Arrayelement zu, das vom Indexargument angegeben wird.|  
|[InterfaceTraits::Verify\-Methode](../windows/interfacetraits-verify-method.md)|Überprüft, dass ordnungsgemäß Basis abgeleitet ist.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[InterfaceTraits::IidCount\-Konstant](../windows/interfacetraits-iidcount-constant.md)|Hält die Anzahl der Schnittstellen\-IDs an, die dem aktuellen InterfaceTraits\-Objekt zugeordnet werden.|  
  
## Vererbungshierarchie  
 `InterfaceTraits`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)