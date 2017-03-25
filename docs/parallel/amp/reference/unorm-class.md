---
title: Unorm-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 6817568b7dc111776033e935fd2ba3ad5dc4a69a
ms.lasthandoff: 03/17/2017

---
# <a name="unorm-class"></a>unorm-Klasse
Darstellen Sie eine Zahl Unorm. Jedes Element ist ein Gleitkommatyp Gleitkommazahl im Bereich von [0, 0F, 1. 0f].  
  
## <a name="syntax"></a>Syntax  
  
```  
class unorm;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Unorm-Konstruktor](#ctor)|Überladen. Standardkonstruktor 0, 0F initialisieren.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|unorm::Operator--||  
|unorm::Operator float|Operator für die Konvertierung. Konvertiert die Unorm Zahl in eine Gleitkommazahl doppelter Wert.|  
|unorm::Operator * =||  
|unorm::Operator / =||  
|unorm::Operator ++||  
|unorm::Operator +=||  
|unorm::Operator =||  
|unorm::Operator =||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `unorm`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="ctor"></a>"unorm" 

 Standardkonstruktor 0, 0F initialisieren.  
  
```  
unorm(
    void) restrict(amp,
    cpu);

 
explicit unorm(
    float _V) restrict(amp,
    cpu);

 
explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit unorm(
    int _V) restrict(amp,
    cpu);

 
explicit unorm(
    double _V) restrict(amp,
    cpu);

 
unorm(
    const unorm& _Other) restrict(amp,
    cpu);

 
inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_V`  
 Der Wert, der zum Initialisieren verwendet wird.  
  
 `_Other`  
 Die Norm-Objekt, das zum Initialisieren verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

