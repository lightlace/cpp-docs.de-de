---
title: Unorm-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 131a928c5943ab9bf4dcc327b044d76e5646ede7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377382"
---
# <a name="unorm-class"></a>unorm-Klasse

Darstellen Sie eine Zahl Unorm. Jedes Element ist ein Gleitkommatyp Zahl im Bereich [0, 0F, 1. 0f] zeigen.

## <a name="syntax"></a>Syntax

```
class unorm;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Unorm-Konstruktor](#ctor)|Überladen. Standardkonstruktor Mit 0, 0F initialisiert werden.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|unorm::Operator:||
|unorm::Operator "float"|Konvertierungsoperator. Konvertieren Sie die Unorm-Zahl in eine Gleitkommazahl Wert.|
|unorm::Operator * =||
|unorm::Operator Operator / =||
|unorm::Operator ++||
|unorm::Operator +=||
|unorm::Operator =||
|unorm::Operator =||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`unorm`

## <a name="requirements"></a>Anforderungen

**Header:** amp_short_vectors.h

**Namespace:** Concurrency:: Graphics

##  <a name="ctor"></a> unorm

Standardkonstruktor Mit 0, 0F initialisiert werden.

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

*_V*<br/>
Der Wert, der zum Initialisieren verwendet wird.

*_Sonstige*<br/>
Die Norm-Objekt, das zum Initialisieren verwendet.

## <a name="see-also"></a>Siehe auch

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
