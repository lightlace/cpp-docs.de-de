---
title: Norm-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs:
- C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71e9baa101eb87ac10171722fa76fc462a154ad2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087478"
---
# <a name="norm-class"></a>norm-Klasse
Darstellen Sie eine Zahl für die Norm. Jedes Element ist ein Gleitkommatyp zeigen Sie die Zahl im Bereich [-1. 0f, 1. 0f].  
  
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
|Norm::Operator:||  
|Norm::Operator "float"|Konvertierungsoperator. Die Anzahl der Norm auf einen Gleitkommatyp konvertieren Wert.|  
|Norm::Operator * =||  
|Norm::Operator Operator / =||  
|Norm::Operator ++||  
|Norm::Operator +=||  
|norm::operator=||  
|Norm::Operator =||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `norm`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_short_vectors.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="ctor"></a> Norm 

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
*_V*<br/>
Der Wert, der zum Initialisieren verwendet wird.  
  
*_Sonstige*<br/>
Das Objekt, das zum Initialisieren verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
