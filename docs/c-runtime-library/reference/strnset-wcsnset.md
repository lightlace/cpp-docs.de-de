---
title: strnset, wcsnset
ms.date: 12/16/2019
api_name:
- strnset
- wcsnset
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcsnset
- strnset
helpviewer_keywords:
- strnset function
- wcsnset function
ms.assetid: e7868ac9-dc34-4606-bd3c-0fb2e7c51631
ms.openlocfilehash: c1f00410dc15a329d6381af893eab44bb938f248
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301092"
---
# <a name="strnset-wcsnset"></a>strnset, wcsnset

Die Microsoft-spezifischen Funktionsnamen `strnset` und `wcsnset` sind als veraltet markierte Aliase für die Funktionen [_strnset und _wcsnset](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md) . Standardmäßig generieren Sie eine [Compilerwarnung (Stufe 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Die Namen sind veraltet, da Sie nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgen. Die Funktionen werden jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_strnset und _wcsnset](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md) bzw. die Funktionen für die Sicherheit mit erweiterter [_strnset_s und _wcsnset_s zu](strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md) verwenden. Oder Sie können diese Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
