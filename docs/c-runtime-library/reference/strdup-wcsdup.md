---
title: strdup, wcsdup
ms.date: 12/16/2019
api_name:
- wcsdup
- strdup
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
- wcsdup
- strdup
helpviewer_keywords:
- wcsdup function
- strdup function
ms.assetid: c9ac0935-b525-4e95-8a64-396fc7e34ee9
ms.openlocfilehash: e381a1933a6b657108a66053bad1c7ff795c1a29
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300520"
---
# <a name="strdup-wcsdup"></a>strdup, wcsdup

Die von Microsoft implementierten POSIX-Funktionsnamen `strdup` und `wcsdup` sind veraltete Aliase für die Funktionen [_strdup und _wcsdup](strdup-wcsdup-mbsdup.md) . Standardmäßig generieren Sie eine [Compilerwarnung (Stufe 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Die Namen sind veraltet, da Sie nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgen. Die Funktionen werden jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_strdup und _wcsdup zu](strdup-wcsdup-mbsdup.md) verwenden. Oder Sie können diese Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
