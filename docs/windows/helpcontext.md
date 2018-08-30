---
title: HelpContext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5644f99e15685f8f1784cc40886709b05a9a06bd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221283"
---
# <a name="helpcontext"></a>helpcontext

Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der **Hilfe** Datei.

## <a name="syntax"></a>Syntax

```cpp
[ helpcontext(
   id
) ]
```

### <a name="parameters"></a>Parameter

*ID*  
Die Kontext-ID des Hilfethemas. Finden Sie unter [HTML-Hilfe: kontextbezogene Hilfe für Programme](../mfc/html-help-context-sensitive-help-for-your-programs.md) Weitere Informationen zum Kontext-IDs.

## <a name="remarks"></a>Hinweise

Die **Helpcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpcontext](/windows/desktop/Midl/helpcontext) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Defaultvalue](../windows/defaultvalue.md) ein Beispiel zur Verwendung für **Helpcontext**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, **Typedef**, **Klasse**, Methode, Eigenschaft|
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
[helpfile](../windows/helpfile.md)  
[helpstring](../windows/helpstring.md)  