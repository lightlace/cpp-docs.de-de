---
title: strnicmp, wcsnicmp
ms.date: 12/16/2019
api_name:
- wcsnicmp
- strnicmp
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
- wcsnicmp
- strnicmp
helpviewer_keywords:
- strnicmp function
- wcsnicmp function
ms.assetid: 01324ee4-0bd9-43e9-b2a3-53d180270a64
ms.openlocfilehash: 6f52df6d0a75922fefb63ee233250f20b1209f74
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300494"
---
# <a name="strnicmp-wcsnicmp"></a>strnicmp, wcsnicmp

Die Microsoft-spezifischen Funktionsnamen `strnicmp` und `wcsnicmp` sind als veraltet markierte Aliase für die Funktionen [_strnicmp und _wcsnicmp](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) . Standardmäßig generieren Sie eine [Compilerwarnung (Stufe 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Die Namen sind veraltet, da Sie nicht den Standard mäßigen C-Regeln für Implementierungs spezifische Namen folgen. Die Funktionen werden jedoch weiterhin unterstützt.

Es wird empfohlen, stattdessen [_strnicmp und _wcsnicmp zu](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) verwenden. Oder Sie können diese Funktionsnamen weiterhin verwenden und die Warnung deaktivieren. Weitere Informationen finden Sie unter [Deaktivieren der Namen der Warnungs](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) -und [POSIX-Funktionen](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).
