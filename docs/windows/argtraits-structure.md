---
title: "ArgTraits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::ArgTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraits-Struktur"
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ArgTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   typename TMemberFunction  
>  
struct ArgTraits;  
template<  
   typename TDelegateInterface  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
#### Parameter  
 `TMemberFunction`  
 Typnamenparameter für eine ArgTraits\-Struktur, die keine Aufrufsmethodensignatur entsprechen kann.  
  
 `TDelegateInterface`  
 Eine Delegatschnittstelle.  
  
 `TArg1`  
 Der Typ des ersten Arguments der Aufrufmethode.  
  
 `TArg2`  
 Der Typ des zweiten Arguments der Aufrufmethode.  
  
 `TArg3`  
 Der Typ des dritten Arguments der Aufrufmethode.  
  
 `TArg4`  
 Der vierte Typ des Arguments der Aufrufmethode.  
  
 `TArg5`  
 Der Typ des fünften Arguments der Aufrufmethode.  
  
 `TArg6`  
 Der Typ des 6. Arguments der Aufrufmethode.  
  
 `TArg7`  
 Der Typ des 7. Arguments der Aufrufmethode.  
  
 `TArg8`  
 Der Typ des Arguments beobachten der Aufrufmethode.  
  
 `TArg9`  
 Der Typ des 9. Arguments der Aufrufmethode.  
  
## Hinweise  
 Die `ArgTraits`\-Struktur deklariert eine angegebene Delegatschnittstelle und anonyme Memberfunktion, die eine angegebene Anzahl Parameter verfügt.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Arg1Type`|Die Typdefinition für TArg1.|  
|`Arg2Type`|Die Typdefinition für TArg2.|  
|`Arg3Type`|Die Typdefinition für TArg3.|  
|`Arg4Type`|Die Typdefinition für TArg4.|  
|`Arg5Type`|Die Typdefinition für TArg5.|  
|`Arg6Type`|Die Typdefinition für TArg6.|  
|`Arg7Type`|Die Typdefinition für TArg7.|  
|`Arg8Type`|Die Typdefinition für TArg8.|  
|`Arg9Type`|Die Typdefinition für TArg9.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ArgTraits::args\-Konstante](../windows/argtraits-args-constant.md)|Hält die Anzahl der Parameter auf der Aufrufmethode einer Delegatschnittstelle.|  
  
## Vererbungshierarchie  
 `ArgTraits`  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)