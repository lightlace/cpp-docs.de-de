---
title: No_injected_text (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 354643020e704a87daa2e56e923b6a0a704bf0b5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038368"
---
# <a name="noinjectedtext"></a>no_injected_text

Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.

## <a name="syntax"></a>Syntax

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Parameter

*boolean*<br/>
(Optional) **"true"** ggf. kein Code eingefügt, **"false"** damit Code eingefügt werden kann. **"true"** ist die Standardeinstellung.

## <a name="remarks"></a>Hinweise

Die häufigste Verwendung von der **No_injected_text** C++ Attribut ist, indem die [/FX](../../build/reference/fx-merge-injected-code.md) Compileroption, die fügt die **No_injected_text** Attribut in der MRG-Datei.

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