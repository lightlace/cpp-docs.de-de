---
title: HelpFile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37309f9170a1fe78c7db802ca13cc81112be9cbb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607376"
---
# <a name="helpfile"></a>helpfile

Legt den Namen der Hilfedatei für die Typbibliothek.

## <a name="syntax"></a>Syntax

```cpp
[ helpfile(
   "filename"
) ]
```

### <a name="parameters"></a>Parameter

*filename*  
Der Name der Datei, die die Hilfethemen enthält.

## <a name="remarks"></a>Hinweise

Die **Helpfile** C++-Attribut hat die gleiche Funktionalität wie die [Helpfile](http://msdn.microsoft.com/library/windows/desktop/aa366853) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Modul](../windows/module-cpp.md) ein Beispiel zur Verwendung für **Helpfile**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, **Typedef**, **Klasse**, Methode **Eigenschaft**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Schnittstellenattribut](../windows/interface-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[helpcontext](../windows/helpcontext.md)  
[helpstring](../windows/helpstring.md)  