---
title: No_injected_text | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 055b14c38e3084a7368953cbce4f95373e1a77f3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706318"
---
# <a name="noinjectedtext"></a>no_injected_text

Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.

## <a name="syntax"></a>Syntax

```cpp
[ no_injected_text(
   boolean
) ];
```

### <a name="parameters"></a>Parameter

*Boolescher Wert*  
(Optional) **"true"** ggf. kein Code eingefügt, **"false"** damit Code eingefügt werden kann. **"true"** ist die Standardeinstellung.

## <a name="remarks"></a>Hinweise

Die häufigste Verwendung von der **No_injected_text** C++-Attribut ist, indem die [/FX](../build/reference/fx-merge-injected-code.md) Compileroption, die fügt die **No_injected_text** Attribut in der MRG-Datei.

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

[Compilerattribute](../windows/compiler-attributes.md)  