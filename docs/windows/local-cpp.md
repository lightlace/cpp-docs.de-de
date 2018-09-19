---
title: lokal (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b910ce2416dc345e2a36c9858f260ef5b42c2cc8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203321"
---
# <a name="local-c"></a>local (C++)

Wenn in der Kopfzeile der Schnittstelle verwendet wird, können Sie Sie den MIDL-Compiler als ein Header-Generator zu verwenden. Bei Verwendung in einer einzelnen Funktion kennzeichnet eine lokale Prozedur, die für die keine Stubs generiert werden.

## <a name="syntax"></a>Syntax

```cpp
[local]
```

## <a name="remarks"></a>Hinweise

Die **lokalen** C++-Attribut hat die gleiche Funktionalität wie die [lokalen](/windows/desktop/Midl/local) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter [Call_as](../windows/call-as.md) ein Beispiel zur Verwendung für **lokalen**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`dispinterface`|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Schnittstellenattribut](../windows/interface-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[call_as](../windows/call-as.md)  