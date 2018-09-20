---
title: ChainInterfaces-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88ddd3dd59000b629f6e72933b1a0b02cc582c89
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409870"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces-Struktur

Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.

## <a name="syntax"></a>Syntax

```cpp
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

### <a name="parameters"></a>Parameter

*I0*<br/>
(Erforderlich) Schnittstellen-ID 0.

*I1*<br/>
(Erforderlich) Schnittstellen-ID 1.

*I2*<br/>
(Optional) Schnittstellen-ID 2.

*I3*<br/>
(Optional) Schnittstellen-ID 3.

*I4*<br/>
(Optional) Schnittstellen-ID 4.

*I5*<br/>
(Optional) Schnittstellen-ID 5.

*I6*<br/>
(Optional) Schnittstellen-ID 6.

*I7*<br/>
(Optional) Schnittstellen-ID 7.

*I8*<br/>
(Optional) Schnittstellen-ID 8.

*I9*<br/>
(Optional) Schnittstellen-ID-9.

*DerivedType*<br/>
Ein abgeleiteter Typ.

*BaseType*<br/>
Der Basistyp eines abgeleiteten Typs.

*hasImplements*<br/>
Ein boolescher Wert, auch wenn **"true"**, bedeutet, dass Sie nicht verwenden eine [MixIn](../windows/mixin-structure.md) Struktur mit einer Klasse, die nicht von abgeleitet ist die [implementiert](../windows/implements-structure.md) abgeschrägten Designs.

## <a name="members"></a>Member

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ChainInterfaces::CanCastTo-Methode](../windows/chaininterfaces-cancastto-method.md)|Gibt an, ob die angegebene Schnittstellen-ID in jede der von definiert spezialisierungen umgewandelt werden kann die **ChainInterface** Vorlagenparameter.|
|[ChainInterfaces::CastToUnknown-Methode](../windows/chaininterfaces-casttounknown-method.md)|Wandelt den Schnittstellenzeiger, der den vom definierten Typ der *I0* Template-Parameter auf einen Zeiger auf `IUnknown`.|
|[ChainInterfaces::FillArrayWithIid-Methode](../windows/chaininterfaces-fillarraywithiid-method.md)|Speichert die Schnittstellen-ID, durch definiert die *I0* Template-Parameter in einer angegebenen Position in einem angegebenen Array von Schnittstellen-IDs.|
|[ChainInterfaces::Verify-Methode](../windows/chaininterfaces-verify-method.md)|Stellt sicher, dass jede Schnittstelle Vorlagenparameter definiert *I0* über *I9* erbt `IUnknown` und/oder `IInspectable`, und dass *I0* erbt von *I1* über *I9*.|

### <a name="protected-constants"></a>Geschützte Konstanten

|name|Beschreibung|
|----------|-----------------|
|[ChainInterfaces::IidCount-Konstante](../windows/chaininterfaces-iidcount-constant.md)|Die Gesamtanzahl der Schnittstellen-IDs enthalten, die in den Schnittstellen, die vom Vorlagenparameter angegeben *I0* über *I9*.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)