---
title: Norm-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs: C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 785c214ed904d1591c5d532ec9f09d42c93dc2ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="norm-class"></a>norm-Klasse
Darstellen Sie eine Zahl Norm. Jedes Element ist ein Gleitkommatyp Gleitkommazahl im Bereich [-1. 0f, 1. 0f].  
  
## <a name="syntax"></a>Syntax  
  
```  
class norm;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Norm-Konstruktor](#ctor)|Überladen. Standardkonstruktor Mit 0, 0F initialisiert werden.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|Norm::Operator-||  
|Norm::Operator--||  
|Norm::Operator "float"|Konvertierungsoperator. Konvertieren von der Norm Zahl in eine Gleitkommazahl Datenpunktwert.|  
|Norm::Operator * =||  
|Norm::Operator Operator / =||  
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

 Standardkonstruktor Mit 0, 0F initialisiert werden.  
  
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
