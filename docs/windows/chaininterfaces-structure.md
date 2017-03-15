---
title: "ChainInterfaces-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChainInterfaces-Struktur"
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ChainInterfaces-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt Aktivierungsrand\- und Initialisierungsfunktionen an, die zu einem Satz Schnittstellen\-IDs angewendet werden können.  
  
## Syntax  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### Parameter  
 `I0`  
 \(Erforderlich\) Schnittstellen\-ID 0.  
  
 `I1`  
 \(Erforderlich\) Schnittstellen\-ID 1.  
  
 `I2`  
 \(Optional\) Schnittstellen\-ID. 2.  
  
 `I3`  
 \(Optional\) Schnittstellen\-ID. 3.  
  
 `I4`  
 \(Optional\) Schnittstellen\-ID. 4.  
  
 `I5`  
 \(Optional\) Schnittstellen\-ID. 5.  
  
 `I6`  
 \(Optional\) Schnittstellen\-ID. 6.  
  
 `I7`  
 \(Optional\) Schnittstellen\-ID. 7.  
  
 `I8`  
 \(Optional\) Schnittstellen\-ID. 8.  
  
 `I9`  
 \(Optional\) Schnittstellen\-ID. 9.  
  
 `DerivedType`  
 Ein abgeleiteter Typ.  
  
 `BaseType`  
 Der Basistyp eines abgeleiteten Typs.  
  
 `hasImplements`  
 Ein boolescher Wert, wenn der `true`, dass Sie [MixIn](../windows/mixin-structure.md) eine Struktur mit einer Klasse nicht verwenden kann, die nicht von der Struktur [Implementiert](../windows/implements-structure.md) abgeleitet.  
  
## Member  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ChainInterfaces::CanCastTo\-Methode](../windows/chaininterfaces-cancastto-method.md)|Gibt an, ob die angegebene Schnittstellen\-ID zu jeder der Normalisierungsformen Spezialisierungen umgewandelt werden kann, die durch die ChainInterface\-Vorlagenparameter definiert werden.|  
|[ChainInterfaces::CastToUnknown\-Methode](../windows/chaininterfaces-casttounknown-method.md)|Wandelt den Schnittstellenzeiger vom Typ um, der vom `I0` Vorlagenparameter zu einem Zeiger auf IUnknown definiert wird.|  
|[ChainInterfaces::FillArrayWithIid\-Methode](../windows/chaininterfaces-fillarraywithiid-method.md)|Speichert die Schnittstellen\-ID, die von den `I0` Vorlagenparameter an die angegebene Position in einem angegebenen Array Schnittstellen\-IDs definiert wird.|  
|[ChainInterfaces::Verify\-Methode](../windows/chaininterfaces-verify-method.md)|Überprüft, ob jede Schnittstelle, der Vorlagenparameter `I0` mit `I9` definiert wird, von IUnknown und\/oder von IInspectable erbt und `I0` von `I1` durch `I9` erbt.|  
  
### Geschützte Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ChainInterfaces::IidCount\-Konstante](../windows/chaininterfaces-iidcount-constant.md)|Die Gesamtanzahl von Schnittstellen\-IDs enthalten in Schnittstellen angegeben durch Vorlagenparameter `I0` durch `I9`.|  
  
## Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)