---
title: No_injected_text (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: af4bb4b07439c0a5dacfa0d4956db564d2dccefe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618116"
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