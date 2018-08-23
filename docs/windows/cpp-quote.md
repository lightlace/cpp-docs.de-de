---
title: Cpp_quote | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a1b9ba00c8728c86935b7c64105d03bb4f19b10
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610599"
---
# <a name="cppquote"></a>cpp_quote

Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten IDL-Datei aus.

## <a name="syntax"></a>Syntax

```cpp
[ cpp_quote(
   "statement"
) ];
```

### <a name="parameters"></a>Parameter

*statement*  
Eine C#-Anweisung.

## <a name="remarks"></a>Hinweise

Die **Cpp_quote** C++-Attribut ist nützlich, wenn es sich bei eine Präprozessordirektive in einer IDL-Datei aufgenommen werden soll.

Sie können auch **Cpp_quote** und eine h-Datei als Teil der Kompilierung von MIDL generiert werden soll. Z. B. Wenn Sie eine C++-Headerdatei, die C++-IDL-Attribute verwendet, aber verwenden Sie diese Datei kann nicht für eine Aufgabe verfügen, können Sie kompilieren es dann zum Erstellen einer MIDL-generierten h-Datei, die Sie verwenden können sollen.

Die **Cpp_quote** Attribut hat die gleiche Funktionalität wie die [Cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [dual](../windows/dual.md) verwenden Sie ein Beispiel mit **Cpp_quote**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Eigenständige Attribute](../windows/stand-alone-attributes.md)  