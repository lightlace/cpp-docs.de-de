---
title: Norm-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs:
- C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
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
ms.openlocfilehash: 6f6477f37a94a0c2a093fd3a63fa8e87463a5a7b
ms.lasthandoff: 03/17/2017

---
# <a name="norm-class"></a>norm-Klasse
Darstellen Sie eine Zahl für die Norm. Jedes Element ist ein Gleitkommatyp Gleitkommazahl im Bereich [-1. 0f, 1. 0f].  
  
## <a name="syntax"></a>Syntax  
  
```  
class norm;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Norm-Konstruktor](#ctor)|Überladen. Standardkonstruktor 0, 0F initialisieren.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|Norm::Operator-||  
|Norm::Operator--||  
|Norm::Operator float|Operator für die Konvertierung. Konvertiert die Norm Zahl in eine Gleitkommazahl doppelter Wert.|  
|Norm::Operator * =||  
|Norm::Operator / =||  
|Norm::Operator ++||  
|Norm::Operator +=||  
|Norm::Operator =||  
|Norm::Operator =||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `norm`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="ctor"></a>Norm 

 Standardkonstruktor 0, 0F initialisieren.  
  
```  
norm(
    void) restrict(amp,
    cpu);

 
explicit norm(
    float _V) restrict(amp,
    cpu);

 
explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit norm(
    int _V) restrict(amp,
    cpu);

 
explicit norm(
    double _V) restrict(amp,
    cpu);

 
norm(
    const norm& _Other) restrict(amp,
    cpu);

 
norm(
    const unorm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_V`  
 Der Wert, der zum Initialisieren verwendet wird.  
  
 `_Other`  
 Das Objekt, das zum Initialisieren verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

