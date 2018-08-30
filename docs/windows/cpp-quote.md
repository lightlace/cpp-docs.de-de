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
ms.openlocfilehash: da9e378ff75ec67660b0c29a5765be88a2c06496
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205665"
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

Die **Cpp_quote** Attribut hat die gleiche Funktionalität wie die [Cpp_quote](/windows/desktop/Midl/cpp-quote) MIDL-Attribut.

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