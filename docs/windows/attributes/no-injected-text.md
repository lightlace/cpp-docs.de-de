---
title: No_injected_text (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 3169c58d192b80400bada8c403f8a769cfb11f55
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069983"
---
# <a name="noinjectedtext"></a>no_injected_text

Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.

## <a name="syntax"></a>Syntax

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Parameter

*Boolescher Wert*<br/>
(Optional) **"true"** ggf. kein Code eingefügt, **"false"** damit Code eingefügt werden kann. **"true"** ist die Standardeinstellung.

## <a name="remarks"></a>Hinweise

Die häufigste Verwendung von der **No_injected_text** C++-Attribut ist, indem die [/FX](../../build/reference/fx-merge-injected-code.md) Compileroption, die fügt die **No_injected_text** Attribut in der MRG-Datei.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)